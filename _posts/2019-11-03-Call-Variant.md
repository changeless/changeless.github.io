---
title: Call Variant
categories: 
- code
tags: 
- bioinformatics
---

## GATK HaplotypeCaller
Generate `.vcf` File
先为每个样本生成一个GVCF，然后再用GenotypeGVCFs对这些GVCF进行joint calling

    gatk --java-options "-Xmx8G" HaplotypeCaller -R ref.fa -I sorted.bam -O raw.vcf'
    
### Difference between `.vcf` and `.gvcf`
1. `.gvcf` is used for group's Joint Calling<br>
2. `.gvcf` is a standardization process including quality control on fq files, alignment, sort, remove duplicate, BQSR, HaplotypeCaller gVCF, etc.<br>
3. `.gvcf` will record all sites' situation including mutation, while `.vcf` only record the situation on mutation sites.<br>

### Difference between `-erc gvcf` and `-erc bp_resolution`
1. 前一种gvcf文件记录非突变位点的时候，以块的形式来记录，而后一种gvcf文件则是对非突变和突变位点一视同仁

### BQSR
1. 没有known变异集就不用使用

## GATK VQSR
Quality control on `.vcf` files. Using the overlap of its own data and known variant sites, a classifier is modeled by the GMM model to score the variance data to assess the feasibility of each site, in order to reject the false positive results and maintain the correct data.

### Requirement
1. Known variation set (`Hapmap`, `OMNI`, `1001G`, and `dbsnp`)<br>
2. There must be enough mutation sites in the new test results.<br>
3. Hard-filtering: If the above two conditions are not met, manual filtering should be considered. (tools used: `gatk SelectVariants`, `VariantFiltration`, and `MergeVcfs`)

### Indicator threshold
1. QualByDepth（QD）<br>
2. FisherStrand (FS)<br>
3. StrandOddsRatio (SOR)<br>
4. RMSMappingQuality (MQ)<br>
5. MappingQualityRankSumTest (MQRankSum)<br>
6. ReadPosRankSumTest (ReadPosRankSum)

### SNP calling

### INDEL calling

## ANNOVAR

<span style="color:red">*need to update*</span> <br>

## Reference
1. [GATK4.0和全基因组数据分析实践(上）](https://mp.weixin.qq.com/s?__biz=MzAxOTUxOTM0Nw==&mid=2649798425&idx=1&sn=ae355ed362848578e5c853413f23dfd7&chksm=83c1d505b4b65c13124c9acd210356c4364ec9f5498bbd16fa4475be29811213abb64ea9720f&scene=21#wechat_redirect)[（下）](https://zhuanlan.zhihu.com/p/34878471): More suitable for human genome analysis
2. [GATK4全基因组数据分析最佳实践](https://zhuanlan.zhihu.com/p/36745259):Give more infromation on `.gvcf` files.
3. [GATK4.0和全基因组数据分析实践](https://www.plob.org/article/11630.html)
