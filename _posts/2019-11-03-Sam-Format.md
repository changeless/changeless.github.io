---
title: Sam-format
categories: 
- code
tags: 
- bioinformatics
---

SAM（The Sequence Alignment / Map format）, you can find full description [here](http://samtools.github.io/hts-specs/SAMv1.pdf)

## Head
Begin with '@'. Give information: SAM format version, reference sequence, software used for aligning

### @HD VN:1.0 SO:unsorted
VN:格式版本
SO: unknown(default), unsorted, queryname, or coordinate
**Note: samtools can't update the SO value after sorting, but picard can.**

### @SQ SN:contig1 LN:9401
SN: reference name
LN: reference length
Example: `@SQ SN:NC_000067.6 LN:195471971`

### @RG ID:sample01
One sample has one Read Group
One sample has multiply library
RG can be added by `bwa mem -R`
Example: `@RG ID:ZX1_ID SM:ZX1(sample name) LB:PE400 PU:Illumina PL:Miseq(sequencing platform)`
**Note: `SM` and `LB` matters**

### @PG ID:bowtie2 PN:bowtie2 VN:2.0.0-beta7
Software used in alignment

## Body
### QNAME: read name `M04650:84:000000000-B837R:1:1101:22699:1759`

1. If the read is aligned to multiple sequences or compared to multiple locations in the sequence, the same name will appear multiple times.
2. If there is a paired read, same name for the sequence will appear twice. - if we use pair-end sequence, the read id will appear at least twice.

### FLAG: alignment type - paring, strand, mate strand `99`

[Detailed description about p-value](https://broadinstitute.github.io/picard/explain-flags.html)

    1（1）该read是成对的paired reads中的一个
    2（10）paired reads中每个都正确比对到参考序列上
    4（100）该read没比对到参考序列上
    8（1000）与该read成对的matepair read没有比对到参考序列上
    16（10000）该read其反向互补序列能够比对到参考序列
    32（100000）与该read成对的matepair read其反向互补序列能够比对到参考序列
    64（1000000）在paired reads中，该read是与参考序列比对的第一条
    128（10000000）在paired reads中，该read是与参考序列比对的第二条
    256（100000000）该read是次优的比对结果
    512（1000000000）该read没有通过质量控制
    1024（10000000000）由于PCR或测序错误产生的重复reads
    2048（100000000000）补充匹配的read

### RENAME: reference name ` NC_000075.6`

### POS: The leftmost position on the 1-Based alignment `124057649`
If the read can completely match the sequence (CIGAR string is M) then this position is the position of the first title alignment of the read. If the reverse complementary sequence of the read is aligned to the sequence, then the position is Is the position of the first bit alignment of the reverse complementary sequence of the read

### MAPQ: quality `60`
1. It equals -10log10, rounded to the nearest integer
2. A value 255 indicates that the mapping quality is not available.
3. 0: unmapped read
4. 60: max mapping value


### CIGAR
CIGAR string

    1. M：alignment match (can be a sequence match or mismatch)
    2. I：insertion to the reference
    3. D：deletion from the reference
    4. N：skipped region from the reference
    5. P：padding (silent deletion from padded reference)
    6. S：soft clipping (clipped sequences present in SEQ)
    7. H：hard clipping (clipped sequences NOT present in SEQ)
    

clipped均表示一条read的序列被分开，之所以被分开，是因为read的一部分序列能匹配到第三列的RNAME序列上，而被分开的那部分不能匹配到RNAME序列上。
    "="表示正确匹配到序列上
    "X"表示错误匹配到序列上
1. 而H只出现在一条read的前端或末端，但不会出现在中间，S一般会和H成对出现，当有H出现时，一定会有一个与之对应的S出现
2. S可以单独出现，而H必须有与之对应的S出现时才可能出现，不可在相同第一列的情况下单独出现

    149M102S
    149H102M
    
**M/I/S/=/X：这些数值的加和等于第10列SEQ的长度**

### MRNM

### MPOS

### ISIZE

### SEQ

### QUAL (Optional)

Reference:
1. [sam格式文件解读](https://blog.csdn.net/genome_denovo/article/details/78712972)
