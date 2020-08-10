---
title: Mapping the epigenetic modification of DNA and RNA
categories: 
- biology
tags: 
- DNA/RNA regulation
---
Modification: not interfere with Watson-Crick pairing but affect the DNA-protein interaction while in the major groove of the double helix.

# Epigenomics
## 5mC: 5th carbon of cytosine (5-methylcytosine) or fifth base - most predominant

### BS-Seq (Bisulfite sequencing) - gold standard for 5mC detection
#### Based on the differential reactivity of bisulfite between methylated C (5mC and 5hmC) and unmethylated C, in which DNA is treated with bisulfite that leads to the deamination of unmethylated C to Uracil (U) while methylated C is resistant to deamination. In the subsequent PCR amplification, methylated C remains C while unmethylated C can be readout as T. 
#### Whole-genome bisulfite sequencing (WGBS), as a whole genome method of BS-Seq, has been widely utilized in DNA methylation profiling, as it can provide single-base resolution with full genome coverage.
#### Cannot distinguish between 5mC and 5hmC

### TET-assisted pyridine borane sequencing (TAPS): bisulfite-free whole-genome base-resultion DNA methylation sequencing methods
#### Can detect 5mC and 5hmC; oxidized by TET to 5caC and then reduced to dihydrouracil (DHU) using pyridine borane with around 98% conversion efficiency, and subsequently readout as T after PCR amplification.

###The Enzyme-based method Enzymatic Methyl-seq (EM-Seq) first utilizes TET2 and betaGT to oxidize and glucosylate 5mC and 5hmC to 5gmC - another bisulfite-free methods

## 5hmC: 5-hydroxymethycytosine or sixth base

### Oxidative bisulfite sequencing (oxBS-Seq)
#### Based on the selective and quantitative chemical oxidation of 5hmC using potassium perruthenate (KRuO4) to produce 5fC that subsequently converted to U by bisulfite treatment with an overall 5hmC-to-U conversion rate of 94.5%

### TET-assisted bisulfite sequencing (TAB-Seq) is an approach in which 5hmC is firstly modified using betaGT, and then 5mC is subsequently oxidized to 5caC by TET1
### Chemical-assistant C-to-T conversion of 5hmC sequencing (hmCCATCH) is a bisulfite-free method to map 5hmC - bisulfite-free approach
#### Especially beneficial for those biological and clinical samples with limited amounts.

### APOBEC-coupled epigenetic sequencing (ACE-Seq) has been developed as a bisulfite-free and enzymatic method for base resolution of sequencing of 5hmC

## 5fC

### Bisulfite base
#### 5fC chemically assisted bisulfite sequencing (fCAB-Seq) was the first quantitative method to sequence 5fC at single-base resolution
##### 5fC is modified with )-ethylhydroxylamine (EtONH2) to form a derivative which can not be converted to U during the following BS-Seq. Therefore, the precise genomic locations of 5fC at single-base level can be identified, through comparison of EtONH2-treated BS-Seq and conventional BS-Seq of the same sample.

#### Termed reduced BS-Seq (redBS-Seq): another bisulfite based method - quantitatively detect 5fC in genomic DNA at single-base resolution, which is based on a selective reduction of 5fC to 5hmC by sodium borohydride (NaBH4) followed by BS-Seq.
#### Termed methylase-assisted bisulfite sequencing (MAB-Seq): another bisulfite-dependent genome-wide method - can quantitatively detect 5fC and 5caC simultaneously at single-base resolution.

### Bisulfite free
#### fC-CET (5fC cyclization-enable C-to-T transition), an aside derivative of 1,3-indandione (AI) was used to achieve selectively labelling of 5fC
#### CLEVER-Seq: the first single-cell 5fC sequencing method termed chemical-labelling-enabled C-to-T conversion sequencing was introduced based on malononitrile labelling of 5fC.

## 5caC
CAB-Seq: Chemical modification-assisted bisulfite sequencing - sequence 5caC at base-resolution at base-resolation.

## Antibody- or immunoprecipitation (IP)- based mapping methods for modified DNA
### MeDIP (Methylated DNA immunoprecipitation) used a 5mC-specific antibody to recognize and pull-down the DNA fragment with 5mC modification
### Similar to MeDIP, 5hmC/5fC/5acC can be recognized with specific antibodies
### hmC-seal: antibody-independent method on the basis of selective chemical labeling and the extremely specific and tight biotin-strepatavidin interaction - selectivity pull-down

## 6mA (N6-methyladenine)
LC-MS/MS mass spectrometry can quantify the proportion of 6mA/A with a high sensitivity and is able to detect 6mA with very low abundance


# Epitranscriptomics
## m6A: N6-methyladenosine - most prevalent

### primarily catalyzed by a methyltransfease complex (termed “writer”) consisting of METTL3 and METTL14 as well as additional protein subunits.

### Play a role in mRNA splicing, polyadenylation, export, translation, stability, structure
Pertunrbation of m6A writers, erasers, or readers has effects on splicing.

### Most of the high-throughout sequencing methods of m6A rely on an m6A-specific antibody
#### Could be influenced by the intrinsic bias of the antibody and binding to particular RNA sequence or other modification.

### Endoribonuclease-based strategies to detect m6A (MAZTER-Seq and m6A-REF-Seq) have been developed, providing examples of antibody-independent m6A sequencing methods.
#### Do not pre-enrich m6A sites, have motif preference and thus detect only part of m6A sites

### DART-seq, another antibody-free m6A sequencing method, utilizes fused APOBEC1-YTH protein to induce C-to-U editing at site adjacent to m6A, thus identifying m6A sites
#### Labelling efficiency are needed to be improved.

### FTO: the first RNA demethylase identified both in vivo and in vitro to erase m6A, binds to exon and intron regions of pre-mRNA.
#### FTO-mediated demethylation of m6A has regulatory roles in alternative splicing and translation
#### FTO dynamically regulates m6A RNA in response to heat shock stress, DNA UV damage and virus infection.
#### FTO-mediated m6A demethylation affects cell growth and plays an oncogenic role in cancer cells.


## m6Am: N6,2’-O-dimethyladenosine 
### All current m6Am sequencing technologies still rely on anti-m6A antibody, so it is needed to develop an unbiased and specific m6Am detection methods.
### The presence of m6Am was originally suggested to alter mRNA stability.


## m1A: N1-methyladenosine
### m1A is an isomer of m6A, with the methyl group attached to the N1 instead of N6 position.
### Presented in tRNA, rRNA, and mRNA
### Both m1A and m6A are dynamic and reversible modification


## m5C: 5-methylcytosine
### formed by methylation at C5 position of cytosine which is present in tRNA, rRNA, and mRNA.
### m5C in RNA can be detected by a modified bisulfite treatment to achieve single-base resolution (potentially quantitative)

### hm5C: 5-hydroxymethylcytosine
### ac4C: N4-acetylcytidine

## Pseudouridine ()
### fifth nucleotide of RNA, the most abundant modification in RNA and widely present in tRNA, rRNA, snRNA, and mRNA.

## m7G: N7-methyladenosine 
### well-known mRNA cap modification

# Long-Read Sequence for DNA and RNA modification
## Next-generation sequencing - limited by short sequencing length
## Third generation sequence methods including PacBio Single-Molecule Real Time (SMRT) sequencing and Oxford Nanopore sequencing
### SMRT sequencing, based on the differentiation of nucleases in DNA through the fluorescent labelled nucleotide being incorporated into DNA by polymerases, can also detect base modification using on polymerase kinetics, such as 5mC, 5hmC, and 6mA.
### Combining SMRT sequencing and RT is possible to detect m6A in RNA and secondary structure of RNA.
### Nanopore sequencing can directly detect DNA or RNA without PCR amplification or cDNA conversion in real time.
### Shortage: high error rate and ummatured base-calling prevent the practical application at present.
##The combination of certain sequencing methods with third generation could provide highly accurate long-read epigenetic sequencing, such as IrTAPS
