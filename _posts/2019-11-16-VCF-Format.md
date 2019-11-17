---
title: VCF Format
categories: 
- code
tags: 
- bioinformatics
---

[Variant Call Format](http://gatkforums.broadinstitute.org/discussion/1268/how-should-i-interpret-vcf-files-produced-by-the-gatk): Used to record variants (SNP/InDel)

<span style="color:red">*need update*</span>

## Annotation
Begin with `#` <br>
主要包括vcf文件版本、FORMAT、INFO、参考基因组以及执行程序等信息


## Body
1. CHROM (chromosome): reference name `chrM`
2. POS: the left-most variant ((1-base position) `150`
3. ID: variant's ID. Can be found in `dbSNP` or use `.` if it cannot be foundb (noval variant).
4. REF: allele in ref `T` (if it is `N`, it means unsure amino acid)
5. ALT: allele in variant `A` .  <br>
`<NON_REF>`: provides us with a way to represent the possibility of having a non-reference allele at this site, and to indicate our confidence either way.

6. QUAL: quality of vairant, Phred. Low value means higher possibility of variant `7766.77` <br>
`10` means the posibility of the variant is 90%

7. FILTER: `Pass` means this site can be considered as a variant <br>
使用上一个QUAL值来进行过滤的话，是不够的。GATK能使用其它的方法来进行过滤，过滤结果中通过则该值为”PASS”;若variant不可靠，则该项不为”PASS”或”.”。

8. INFO `AC=2;AF=1.00;AN=2;DP=199;ExcessHet=3.0103;FS=0.000;MLEAC=2;MLEAF=1.00;MQ=49.78;QD=32.91;SOR=0.904`
   
   **a.`AC`, `AF`, and `AN`**
   
        `AC`: Allele Count - the number of the alleles have the same genetype of variant
        `AF`: Allele Frequency - `AF = AC / AN`
        `AN`: Allele Number
        Example: 对2个sample的双倍体进行测序，则AN值为4。若REF上位点碱基为A，而2个sample在该位点分别为A/T和T/G，则AC值为2，1；AF值为0.50，0.25。
        
    **b. `DP`: reads coverage after filtering**
    
    **c. `QD`: Variant call confidence normalized by depth of sample reads supporting a variant
    
    **d. `MQ`: 表示覆盖序列质量的均方值RMS Mapping Quality
    
    **e. `FQ`：phred值关于所有样本相似的可能性
    
    **f. `AC`，`AF` 和 `AN`：AC(Allele Count) 表示该Allele的数目；AF(Allele Frequency) 表示Allele的频率； AN(Allele Number) 表示Allele的总数目。<br>
     对于1个diploid sample而言：则基因型 0/1 表示sample为杂合子，Allele数为1(双倍体的sample在该位点只有1个等位基因发生了突变)，Allele的频率为0.5(双倍体的sample在该位点只有50%的等位基因发生了突变)，总的Allele为2； 基因型 1/1 则表示sample为纯合的，Allele数为2，Allele的频率为1，总的Allele为2。
     
     **g. `MLEAC`：Maximum likelihood expectation (MLE) for the allele counts (not necessarily the same as the AC), for each ALT allele, in the same order as listed
     
     **h.  `MLEAF`：Maximum likelihood expectation (MLE) for the allele frequency (not necessarily the same as the AF), for each ALT allele, in the same order as listed
     
     **i. `BaseQRankSum`: 比较支持变异的碱基和支持参考基因组的碱基的质量，负值表示支持变异的碱基质量值不及支持参考基因组的, 正值则相反，支持变异的质量值好于参考基因组的。0表示两者无明显差异。
    
    **j. `FS`: FisherStrand**<br>
        1. The p-value of the Fhred format obtained by Fisher's exact test to detect chain skew.<br>
        2. The smaller, the better.<br>
        3. The larger, the more serious strand bias<br>
        4. 使用F检验来检验测序是否存在链偏好性。链偏好性可能会导致变异等位基因检测出现错误。输出值Phred-scaled p-value，值越大越可能出现链偏好性。<br>
        **5. Filter: suggest to keep sites with FS < 10~20 (can be done by GATK)**
        
    **k. ReadPosRandSum**<br>
        1. Z-score from Wilcoxon rank sum test of Alt vs. Ref read position bias<br>
        2. When variant apprear near the ends of the sequence, it's less accurate.<br>
        3. Positive value: the allele is in the middle of the reads<br>
        4. Negative value: near the ends<br>
        **5. Filter: suggest to keep sites with ReadPosRankSum > -1.65~-3.0**<br>
    
    **l. `ReadPosRankSum`: 检测变异位点是否有位置偏好性（是否存在于序列末端，此时往往容易出错）。最佳值为0，表示变异与其在序列上的位置无关。负值表示变异位点更容易在末端出现，正值表示参考基因组中的等位基因更容易在末端出现。
    
    **m.  `xcessHet`: 检测这些样本的相关性，与InbreedingCoeff相似，值越大越可能是错误。
        
    **n. MQRankSum**<br>
        1. measure the mapping quality between reads of alternative allele and reference allele.<br>
        2. Negative: alternative allele's reads mapping quality is lower than reference allele's.<br>
        **3. Filter: suggest to keep sites with MQRankSum > -1.65~-3.0**

9. FORMAT `GT:AD:DP:GQ:PL`

    **a. `GT`: genotype**
        `0`: sample has the allele from ref
        `1`: one variant
        `2`: two variants

        0/0 Homozygous locus, ref/ref
        0/1 Heterozygous mutation, ref/alt
        1/1 Homozygous mutation, alt/alt
        1/2 Heterozygous mutation, alt1/alt2
        
    **b. `AD`/`DP`: Allele Depth/ depth**
        `DP` value equals to the sum of `AD`
        
        1/1:0,175:175—GT:AD(REF),AD(ALT):DP
        0/1:79,96:175
        
    **c. `GC`: Genotype Quality `Phred_scaled`**
        High value equals to the high possibility of the genotype
        Maxium: `99`
        
    **d. `PL`: likelihood genotypes**
        provieds the likelihoods of the given genotypes(0/0, 0/1, 1/0)
        Higher means the possibility of this type is lower (和之前不一致，该值越大，表明为该种基因型的可能性越小。 Phred值 = -10 * log (p) p为基因型存在的概率。)
        `0` = the most possibility
        
        1/1:580,54,0
        1/2:3365,1522,1357,1842,0,1706
    **e. `SP`：phred的p值误差线
        
10. SAMPLES: determined by `SM` of `@RG` 

## Reference
1. [vcf格式文件解读](https://blog.csdn.net/genome_denovo/article/details/78697679)
2. [VCF文件格式解析](https://www.jianshu.com/p/13f162636164)
3. [VCF格式的学习及对VCF文件的统计](https://www.jianshu.com/p/38f734ae47f5)
4. [NON_REF in gvcf](https://gatkforums.broadinstitute.org/gatk/discussion/4216/non-ref-in-gvcf)
5. [基于GATK检测基因组SNP和indel](https://www.jianshu.com/p/38f734ae47f5)

