---
title: RNA-seq Library
categories: 
- biology
tags: 
- bioinformatics
- biology
---

RNA-seq Library

# RNA-seq基本流程

![Preparing an RNA-seq Library](../../../../../assets/images/2020-09-14/7027828-45453f771c5c26b5.webp)

## 反转录
1. 用反转录酶 reverse transcriptase (RT) 将RNA作为模板合成DNA
2. oligo-dT作为RT引物：mRN——dT可以和polyA tail结合，但RT不是一个高度持续性的聚合酶，可能让转录提前发生终止，造成的结果就是3’端要比5'端reads富集，这样就会使得后续定量分析带来bias。
3. 随机引物：可以结合ncRNA等没有A尾巴的RNA，且不会存在明显的3’端偏差。但很多研究也发现，所谓的随机引物根本就不随机，这也是测序结果中，通常前6个碱基的GC含量分布特别不均匀的原因。几个碱基GC含量均匀很可能不是接头或者barcode那些东西，其实是Illumina 测序RT这一步的random hexamer priming 造成的bias。

## 第二条DNA链
用DNA聚合酶，以刚才合成的第一条链作为模板

## 加接头

![](../../../../../assets/images/2020-09-14/7027828-c4c0cdff216f261f.webp)

1. 为了让机器可以识别这些序列，把这些序列固定
2. 为了让多个样品可以同时上机，平摊每个样品的测序价格
3. 因为很多时候read的长度要短于insert，为了增加覆盖度于是就想出了从insert两端同时测序的办法。使得测序深度增加的同时也能够用来判断isoform方向。

## 测序
1. 对于illumina数据，有一条5-3的universal adaptor；还有一条是3-5的indexed adatpor，这条引物含有特意的barcode
2. 在双端测序中，如果insert 不是足够长，那么R1可能就会测到R2的引物，同时R2可能会测到R1引物的反向互补序列。

![](../../../../../assets/images/2020-09-14/7027828-85339f737fa4f8d2.webp)

![](../../../../../assets/images/2020-09-14/7027828-965d0ab5f0825244.webp)


1. 测序：识别四种碱基发出的不同颜色的荧光
(如果一大片点都是同种荧光，会降低机器效率（主要发生在序列前几个碱基）)

# 链特异性测序
1. 普通建库：传统建库方式通过两个接头的ligation把RNA变成DNA，最后文库被测序的链分为正义链（sense strand）和反义链
2. 链特异性测序：dUTP测序方式的名字是fr-firstrand（也是RF）——首先利用随机引物合成RNA的一条cDNA链，在合成第二条链的时候用dUTP代替dTTP，加adaptor后用UDGase处理，将有U的第二条cDNA降解掉 - 这样最后的insert DNA fragment都是来自于第一条cDNA
a. tophat的参数应该为 `–library-type fr-firststrand`
b. 这里的first-strand cDNA可不是RNA strand，在使用htseq-count 时，真正的正义链应该是使用参数 `-s reverse` 得到的结果。

![](../../../../../assets/images/2020-09-14/7027828-b29d8480fabe8dcc.webp)

## 链名
1. 正链 forward: 可以同时有sense strand 和 antisense strand。因为这完全是两个不同的概念。
2. 反链 reverse
3. 正义链 sense strand = 编码链 coding strand = 非模板链
4. 反义链 antisense strand

## dUTP
dUTP方式测序R1文件中read1的方向和基因的方向（正义链）是相反的，而R2文件中的read2方向和基因的方向是相同的

# 常用软件
1. STAR mapping
a. If you have stranded RNA-seq data, you do not need to use any specific STAR options
b. Instead, you need to run Cufflinks with the library option --library-type options. For example, `cufflinks…` `--library-type fr-firststrand` should be used for the standard dUTP protocol, including Illumina’s stranded Tru-Seq.

2. Hisat2  --rna-strandness RF
a. For single-end reads, use F or R. 'F' means a read corresponds to a transcript. 'R' means a read corresponds to the reverse complemented counterpart of a transcript.
b. For paired-end reads, use either FR or RF. 
c. With this option being used, every read alignment will have an XS attribute tag: '+' means a read belongs to a transcript on '+' strand of genome. '-' means a read belongs to a transcript on '-' strand of genome.

3. tophat --library-type option fr-firststrand

4. htseq-count -s reverse/yes(看反义链)

5. RSEM --forward-prob 0（正义链）1（看反义链）

6. sXpress --rf-stranded / —fr-stranded(看反义链)

7. trinity --SSlibtype RF
(后面关于生信的内容没看懂就没有整理了）

# mRNA提取 
## mRNA纯度 - rRNA占提取的总RNA量的95%以上
![](https://pic2.zhimg.com/80/v2-372e79f49b3c043d133a194efc37279b_1440w.png)
![](https://pic2.zhimg.com/80/v2-fbef0c6560a177aaca3f7f7c3b8866fb_1440w.png)
![](https://picb.zhimg.com/80/v2-48a8a418a83f89b9ba7e3945d4046194_1440w.png)

## rRNA去除以及建库
![](https://pic1.zhimg.com/80/v2-f525fb83c22a548cca7adf8b2a0037b9_1440w.png)

1. 利用高等生物mRNA都带有Poly(A)尾巴的特点，用带Poly(T)的探针磁珠与总RNA进行杂交，吸附其中的带Poly(A)尾巴的mRNA。
2. 接下来进行磁珠的回收，然后把这些Poly(A)的mRNA从磁珠上洗脱下来。
3. 然后在把洗脱下来的mRNA用镁离子溶液进行处理（镁离子溶液会把mRNA打断）
4. 紧接着，被打断的mRNA片段再用随机引物（dNTP）进行逆转录。逆转录成cDNA（第一条链）后再合成第二条链。这样mRNA就变成了双链的cDNA。
5. 最后，在双链cDNA的两端接上"Y"型的接头，经过PCR扩增，就成为了可以上机测序的文库。我们就可以去Hi Sqe测序仪上进行RNA测序。

# 结果分析
## 火山图
作为一种针对全转录组的分析，我们希望看到的是一个整体样本的基因表达差异变化，而不仅仅是看少数几个基因的表达差异。

![](https://pic1.zhimg.com/80/v2-f19b46021cf8abacdcee4802e7a08c00_1440w.png)

这个图表达的是两个样本之间的表达差异（比如正常组织和癌变组织）横轴表达某个基因是上升了还是下降了，纵轴表述这种差异的置信程度

## RNA聚类分析

![](https://pic1.zhimg.com/80/v2-f4e1e02ae3193329975f2079f132c9e3_1440w.png)

横轴表示样本，纵轴表示基因。在这个群体中，样本被分成了3个群体。每个群体的内部都有相似的表达特征，同时，我们也可以看到，基因的表达是成簇的。

## GO分析（Gene Ontology分析）
GO主要描述基因的三个属性：1、基因参与的生物学过程2、基因的产物的功能3、基因产物在细胞内的空间定位。
![](https://pic1.zhimg.com/80/v2-bdae6034e6fa798e71f0189471209d85_1440w.png)
![](https://pic4.zhimg.com/80/v2-52951d7c8931ccdcdcb68b9167668f7c_1440w.png)
![](https://pic3.zhimg.com/80/v2-e8af4529951f588772da149c6b07523f_1440w.png)

## KEGG通路分析
1. 通路分析：通路是指在系统水平上完成生物的某一功能的基本单位或者局部子网络。
2. KEGG是目前公认的、最权威的基因功能数据库。其中的通路分析是KEGG的核心内容。目前对于通路的分析、注释，大多数是基于KEGG通路来做的。

![](https://pic1.zhimg.com/80/v2-73f5b28d8b9b2aad6711e459cb9d5935_1440w.png)
![](https://pic4.zhimg.com/80/v2-f29a6becfce474f32def205202e0ff58_1440w.png)
![](https://pic1.zhimg.com/80/v2-f1236a6d1e8f3c9c126b14292a555ad7_1440w.png)

点的面积越大，则富集的基因鼠就越多。富集因子越大，则表示富集的程度越大。qvalue是校正之后的pvalue，其值越接近0表示富集程度越显著。



# Reference
1. [链特异建库那点事](https://www.jianshu.com/p/a63595a41bed)
2. [看这里，你所需要的RNA-seq建库方法以及数据分析](https://zhuanlan.zhihu.com/p/141330526)

