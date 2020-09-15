---
title: Detection of low-frequency allelic variants via Molecular Barcoding
categories: 
- biology
tags: 
- Barcode
---

# 什么是NGS（next gene sequencing)

# 如何在NGS前富集靶标区域？
1. 使用靶标特异性探针从测序文库中进行杂交捕获 - 将DNA片段在溶液中基因组中靶标区域对应的序列特异性捕获探针进行杂交（杂交捕获技术：Agilent SureSelect, NimbleGenSeqCap, Illumia TruSeq)
2. 利用靶标特异性引物直接用样品DNA进行PCR扩增 - 选定的外显子引物通过PCR富集靶标基因（Ion Torrent AmpliSeq, RainDance ThunderBolts, Illumina TruSeq扩增子等仅基于PCR的方法，以及Agilent HaloPlex等杂交和延伸方法）

# NGS中潜在的错误来源
PCR和测序方法的系统误差 - 0.05%～1%

# 什么是分子条形码：为同一样品的每个原始DNA片段连接上一段独一无二的序列编码 - 可用于计量高覆盖率NGS数据中的测序误差和PCR误差
1. 完全随机的核苷酸链（如NNNNNNN）
2. 部分简并核苷酸链（如NNNRNYN）
3. 指定核苷酸链（模板分子有限时）

# 分子条形码和样品条形码有何不同
1. 分子条形码 - 减少假阳性结果
2. 样品条形码（标签接头）- 常用于多数当前的NGS流程中，允许在测序前对样品进行混合 - 起标签的作用，以确定读出序列来源于哪个样品，因此可以在一次运行中检测多个样品

# 为什么要用分子条形码？
1. 将DNA片段接上一段独特的序列条形码
2. 具有不同分子条形码的读出序列代表不同的原始DNA分子
3. 具有相同条形码的读出序列是相同原始分子经过PCR复制的产生
4. 使用分子条形码还能将PCR假阳性与原始分子中的真正变异区分开来，从而在变异等位基因频率（VAF）极低时进行编译检测。

# 分子条形码能否使杂交捕获方法受益？

# 分子条形码的使用
利用限制性内切酶识别、杂交和DNA连接的特异性从待测序靶标区域捕获分子。在引物载体上添加一个分子条形码。

# 需要多高的覆盖率才能达到所需的灵敏度？
1. 如果需要4个读出序列以显示替换等位基因并以0.1%的灵敏度可靠地测定变异，则应在删除重复后达到4000X的深度覆盖（4个读出序列/0.001）
2. 从理论上来说，我们需要至少4000个单倍体基因拷贝、2000个细胞或12ngDNA

# 如何分析分子条形码：五个步骤
1. 在文库制备阶段利用分子条形码对单个DNA分子进行标记
2. 读出序列对齐时忽略分子条形码
3. 将与相同基因组坐标对齐的读出序列对根据分子条形码进行分组
4. 将分子条形码对应的碱基序列合并为每个分子一个读出序列
5. 去除PCR重复

# 可用Agilent SureCell软件分析HaloPlex分子条形码
舍弃1个或者4个以下的读出序列可筛选可分析的数据

# 也可使用AGeNT（基于Java的软件模块）处理测序后生成的靶向高通量测序数据的读出序列。
1. 可从末端切除低质量碱基，去除接头序列并掩盖酶处理印记。
2. 在对齐前以这种方式正确制备读出序列，可有效提高对齐效率并降低假阳性变异识别的比例
3. 还可以处理数据在对齐后的分子条形码（MBC）信息，其中将读出序列对标记在BAM/SAM文件中
4. 还可从该BAM/SAM文件中标记或去除MBC重复

# Reference
1. 分子条形码 — 常见问题解答 利用 HaloPlexHS 检测低频等位基因变异
2. Peng et al. Reducing amplification artifacts in high multiplex amplicon sequencing by using molecular barcodes. BMC Genomics. 2015 Aug 7;16:589. 
3. Gnirke et al. Solution hybrid selection with ultra-long oligonucleotides for massively parallel targeted sequencing. Nat Biotechnol. 2009 Feb;27(2):182-9. 
4. Taylor et al. Ultradeep bisulfite sequencing analysis of DNA methylation patterns in multiple gene promoters by 454 sequencing. Cancer Res. 2007 Sep 15;67(18):8511-8. 
5. Bodi et al. Comparison of commercially available target enrichment methods for next generation sequencing. J. Biomol. Tech. 2013 Jul;24(2):73-86. 
6. Chang et al. Clinical application of amplicon-based next generation sequencing in cancer. Cancer Genet. 2013 Dec;206(12):413-9. 
7. Kinde et al. Detection and quantification of rare mutations with massively parallel sequencing. Proc Natl Acad Sci U S A. 2011 Jun 7;108(23):9530-5. 
8. Poptsova et al. Non-random DNA fragmentation in next-generation sequencing. Sci Rep. 2014; 4: 4532. 
9. Schmitt et al. Detection of ultrarare mutations by next-generation sequencing. Proc Natl Acad Sci U S A. 2012 Sep 4;109(36):14508-13. 
10. Hiatt et al. Single molecule molecular inversion probes for targeted, highaccuracy detection of low-frequency variation. Genome Res. 2013 May;23(5):843-54. 
11. Kou et al. Benefits and challenges with applying unique molecular identifiers in next generation sequencing to detect low frequency mutations. PLoS One. 2016 Jan 11;11(1):e0146638. 
12. https://cofactorgenomics.com/ heterogenous-dna-sequencinglower-limits-minor-allele-frequencysensitivity/ 
13. de Kock et al. High-sensitivity sequencing reveals multi-organ somatic mosaicism causing DICER1 syndrome. J. Med. Genet. 2016; 53:43-52.
