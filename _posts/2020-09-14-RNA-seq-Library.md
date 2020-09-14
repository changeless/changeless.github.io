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

[Preparing an RNA-seq Library](https://upload-images.jianshu.io/upload_images/7027828-45453f771c5c26b5)

## 反转录
1. 用反转录酶 reverse transcriptase (RT) 将RNA作为模板合成DNA
2. oligo-dT作为RT引物：mRN——dT可以和polyA tail结合，但RT不是一个高度持续性的聚合酶，可能让转录提前发生终止，造成的结果就是3’端要比5'端reads富集，这样就会使得后续定量分析带来bias。
3. 随机引物：可以结合ncRNA等没有A尾巴的RNA，且不会存在明显的3’端偏差。但很多研究也发现，所谓的随机引物根本就不随机，这也是测序结果中，通常前6个碱基的GC含量分布特别不均匀的原因。几个碱基GC含量均匀很可能不是接头或者barcode那些东西，其实是Illumina 测序RT这一步的random hexamer priming 造成的bias。

## 第二条DNA链
用DNA聚合酶，以刚才合成的第一条链作为模板

## 加接头

[photo](https://upload-images.jianshu.io/upload_images/7027828-c4c0cdff216f261f?imageMogr2/auto-orient/strip|imageView2/2/w/923/format/webp)

1. 为了让机器可以识别这些序列，把这些序列固定
2. 为了让多个样品可以同时上机，平摊每个样品的测序价格
3. 因为很多时候read的长度要短于insert，为了增加覆盖度于是就想出了从insert两端同时测序的办法。使得测序深度增加的同时也能够用来判断isoform方向。

## 测序
1. 对于illumina数据，有一条5-3的universal adaptor；还有一条是3-5的indexed adatpor，这条引物含有特意的barcode
2. 在双端测序中，如果insert 不是足够长，那么R1可能就会测到R2的引物，同时R2可能会测到R1引物的反向互补序列。

[photo](https://upload-images.jianshu.io/upload_images/7027828-85339f737fa4f8d2?imageMogr2/auto-orient/strip|imageView2/2/w/1158/format/webp)

[photo](https://upload-images.jianshu.io/upload_images/7027828-965d0ab5f0825244?imageMogr2/auto-orie)nt/strip|imageView2/2/w/1101/format/webp)


1. 测序：识别四种碱基发出的不同颜色的荧光
(如果一大片点都是同种荧光，会降低机器效率（主要发生在序列前几个碱基）)

# 链特异性测序
1. 普通建库：传统建库方式通过两个接头的ligation把RNA变成DNA，最后文库被测序的链分为正义链（sense strand）和反义链
2. 链特异性测序：dUTP测序方式的名字是fr-firstrand（也是RF）——首先利用随机引物合成RNA的一条cDNA链，在合成第二条链的时候用dUTP代替dTTP，加adaptor后用UDGase处理，将有U的第二条cDNA降解掉 - 这样最后的insert DNA fragment都是来自于第一条cDNA
a. tophat的参数应该为 `–library-type fr-firststrand`
b. 这里的first-strand cDNA可不是RNA strand，在使用htseq-count 时，真正的正义链应该是使用参数 `-s reverse` 得到的结果。

[photo](https://upload-images.jianshu.io/upload_images/7027828-b29d8480fabe8dcc?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)

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

# Reference
1. [链特异建库那点事](https://www.jianshu.com/p/a63595a41bed)


