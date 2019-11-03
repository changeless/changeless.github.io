---
title: VCF-format
categories: 
- code
tags: 
- bioinformatics
---

<span style="color:red">*need update*</span>

[Variant Call Format](http://gatkforums.broadinstitute.org/discussion/1268/how-should-i-interpret-vcf-files-produced-by-the-gatk): Used to record variants (SNP/InDel)

## Annotation
Begin with `#`

## Body
1. CHROM: reference name `chrM`
2. POS: the left-most variant ((1-base position) `150`
3. ID: variant's ID. Can be found in `dbSNP` or use `.` if it cannot be found.
4. REF: allele in ref `T`
5. ALT: allele in variant `A`
6. QUAL: quality of vairant, Phred. Low value means higher possibility of variant `7766.77`
7. FILTER: `Pass` means this site can be considered as a variant
8. INFO `AC=2;AF=1.00;AN=2;DP=199;ExcessHet=3.0103;FS=0.000;MLEAC=2;MLEAF=1.00;MQ=49.78;QD=32.91;SOR=0.904`
   
   **a.`AC`, `AF`, and `AN`**
   
        `AC`: Allele Count - the number of the alleles have the same genetype of variant
        `AF`: Allele Frequency - `AF = AC / AN`
        `AN`: Allele Number
        Example: 对2个sample的双倍体进行测序，则AN值为4。若REF上位点碱基为A，而2个sample在该位点分别为A/T和T/G，则AC值为2，1；AF值为0.50，0.25。
        
    **b. `DP`: reads coverage after filtering**
    
    **c. `FS`: FisherStrand**<br>
        1. The p-value of the Fhred format obtained by Fisher's exact test to detect chain skew.<br>
        2. The smaller, the better.<br>
        3. The larger, the more serious strand bias<br>
        **4. Filter: suggest to keep sites with FS < 10~20 (can be done by GATK)**
        
    **d. ReadPosRandSum**<br>
        1. Z-score from Wilcoxon rank sum test of Alt vs. Ref read position bias<br>
        2. When variant apprear near the ends of the sequence, it's less accurate.<br>
        3. Positive value: the allele is in the middle of the reads<br>
        4. Negative value: near the ends<br>
        **5. Filter: suggest to keep sites with ReadPosRankSum > -1.65~-3.0**
        
    **e. MQRankSum**<br>
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
        Higher means the possibility of this type is lower
        `0` = the most possibility
        
        1/1:580,54,0
        1/2:3365,1522,1357,1842,0,1706
        
10. SAMPLES: determined by `SM` of `@RG` 

## Reference
1. [vcf格式文件解读](https://blog.csdn.net/genome_denovo/article/details/78697679)
