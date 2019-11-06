---
title: CRISPR/CAS9 Gene Editing
categories: 
- biology
tags: 
- CRISPR
---

[Molecular biology at the cutting edge: A review on CRISPR/CAS9 gene editing for undergraduates](https://www.ncbi.nlm.nih.gov/pubmed/29381252)

# CRISPR: A Bacterial and Archeal Immune System Adapted for Eukaryotic Gene Editing

## Adaptive Immunity in Bacteria and Archea
![CRISPR/Cas9 mediated acquired immunity in prokaryotes](https://wol-prod-cdn.literatumonline.com/cms/attachment/1e47445c-4cfe-456b-8528-13609e98958d/bmb21108-fig-0001-m.jpg)
**Figure 1: CRISPR/Cas9 mediated acquired immunity in prokaryotes.** 
During the acquisition phase (A), cellular invaders such as phage virus inject nucleic acid sequences into the host cell. After infection, novel DNA sequences from the cellular invaders are incorporated into the host CRIPSPR locus as spacers (colored circles) flanked by repeat sequences (gray diamonds). As a result, when the CRISPR locus is transcribed, the pre‐CRISPR RNAs (crRNAs) encode the newly acquired protospacer sequences. The pre‐crRNA is cleaved to produce individual crRNAs that will associate with Cas proteins. The Cas protein utilizes the crRNAs as guides to silence foreign DNA that matches the crRNA sequence (B, interference phase). As a result, the second time a bacteria encounters the same foreign DNA, the crRNA/Cas9 complex is able to identify and silence the DNA.

1. CRISPR: Clustered Regulatory Interspaced Short Palindromic Repeats - a defense mechanism in an adaptive immune system (along with the CRISPR‐associated Proteins or Cas proteins)
2. By integrating DNA sequences that are identical to past invaders into their genome, bacteria and archea generate a cellular memory of past invaders. 
3. These acquired sequences allow the bacteria or archea to recognize viral or plasmid invaders as non‐self, resulting in the degradation of the invading sequence and functioning as an adaptive immune system for prokaryotes.
4. pre-crRNA/crRNA: CRISPR RNA
5. tracrRNA: trans‐activating CRISPR RNA
6. Double strand RNA = pre-crRNA + tracrRNA, cleaved by RNaseIII and then generate crRNA:tracrRNA complex containing just one spacer sequence - This RNA complex then associates with a single Cas9 protein, creating an active ribonucleoprotein (RNP) complex
5. Three different types of CRISPR–Cas systems have been identified in bacteria and archea: Type I, Type II, and Type III - Each system utilizes a different mechanism to generate crRNA and Cas proteins that catalyze the nucleic acid cleavage
6. Type II CRISPR system: most commonly adapted for genome editing due to its simplicity requiring just one Cas protein, Cas9, and two RNA components
7. PAMs: Proto‐spacer Adjacent Motifs
8. Cas9 nuclease domains used for cleavage: HNH (complementary DNA strand) and RuvC‐like (not complementary)
9. NHEJ: non‐homologous end joining
10. HDR: homology‐directed repair

![Figure 2](https://wol-prod-cdn.literatumonline.com/cms/attachment/58766ca1-e833-48b6-96bb-ed6c3d56a40d/bmb21108-fig-0002-m.jpg)
**Figure 2: Cas9 induced double‐strand breaks can be repaired by both nonhomologous end‐joining (NHEJ) or homology‐directed repair (HDR).**
(A) sequence of a targeted genomic locus in relation to the PAM (5′‐NGG‐3′) site. 
(B) Cartoon representation of crRNA, tracrRNA, and Cas9 protein assembly. 
(C) NHEJ results in random insertions, deletions, and indels. 
(D) HDR results in precise researcher‐designed edits. To achieve HDR, the researcher also introduces a repair template that contains the desired edit in which the HDR repair machinery of the cell uses to repair the induced double strand break.
  
![Figure 3](https://wol-prod-cdn.literatumonline.com/cms/attachment/76f2db09-8247-4a14-a94d-a3c7c2a23a0f/bmb21108-fig-0003-m.jpg)
**Figure 3: Cas9 has two nuclease domains each cutting a different strand of DNA.**
(A) Wildtype Cas9 contains two nuclease domains, RuvC and HNH which each cut a different strand of the DNA. When the RuvC nuclease domain is mutated, Cas9 will act as a nickase and produce a nicked DNA product (B).

## The Power of Making Programmed Double‐Strand Breaks for Genome Editing in Eukaryotes

1. C-NHEJ: canonical NHEJ - ligates or essentially “glues” the broken ends back together
2. alt‐NHEJ: alternative end joining pathway - one strand of the DNA on either side of the break is resected to repair the lesion
3. C-NHEJ and alt-NHEJ: both are error‐prone
4. crRNA and tracrRNA could be combined into a single guide RNA (sgRNA)

# How Do Researchers Exploit CRISPR for Genome Editing?
## Target and Guide Selection
1. guide RNA design - the 20‐nucleotide target region of the guide RNA must be adjacent to a PAM site
2. [CRISPR design tools](http://crispor.tefor.net/): scan the specificity of a target sequence to minimize off‐target effects.

## Generation and Delivery of Components
1. Cas9 and sgRNAs can be introduced using three different strategies after designing guide RNA: The sgRNA or crRNA and tracrRNA and Cas9 can be expressed as DNA, RNA, or RNA/protein complexes

![Figure 4](https://wol-prod-cdn.literatumonline.com/cms/attachment/18b92fa3-4b31-4b69-94c5-027ce17f189f/bmb21108-fig-0004-m.jpg)
**Figure 4: Different methods to introduce CRISPR/Cas9 components.**
CRISPR guides and the Cas9 protein required for genome editing can be introduced into organisms or cells both as DNA plasmids (A), both as RNA molecules (B), or RNA and Protein complexes (RNPs) (C).

### DNA
1. two plasmids: one encoding the sgRNA and one encoding the Cas9 protein
2. untranslated regions (UTR): efficient translation of Cas9 mRNA to protein
3. Promoter: a sequence directly upstream of the transcription start site of the gene and recruits RNA polymerase to initiate transcription - for transcribe the encoded protein (Cas9 plasmid); sgRNA must also be expressed from an appropriate promoter.
4. the sgRNA is transcribed by RNA polymerase III - ultimate product is RNA

### RNA and RNA/Protein (RNP) Complexes
1. most efficient and cost‐effective way to generate a desired edit-no need to optimize species‐specific promoters and UTRs
2. drawback: purifying the Cas9 protein and ordering RNA is costlier

## Identification of Desired Mutation (bottleneck)
Two different genetic strategies can be used to identify desired mutants: screens and selections.

### Genetic screen
1. associated phenotype (e.g., GFP is inserted utilizing HDR to tag a protein of interest)
2. molecular lesion generated by the genome edit - especially useful when NHEJ results in a small insertion or deletion (e.g., restriction fragment length polymorphisms (RFLP) analysis - cut by restriction endonuclease and then visualized by gel electrophoresis)

### Genetic selection
1. Utilize lethal mutations so that only the individuals of interest survive a particular condition
2. E.g., utilizes a specialized template for repair, which introduces a gene for drug resistance into the animal or cell

## Generation of CRISPR/Cas9 Mutation in C. elegans: A Case Study
1. microinjection into the gonads of young adult hermaphrodites - an effective way to introduce exogenous DNA, RNA, and/or protein
2. Need to ensure Cas9 is expressed as the correct time and tissue in C. elegans: Cas9 must be expressed in the gonad while the germ cells are developing - in order to be passed to the next generation
3. Promoter - heat
4. Reducing the duration that Cas9 is active reduces the potential for embryonic lethality - may due to off-target

# Variations on a Theme: Alternatives to Cas9 and Novel Applications
1. Cas9 is the enzyme's specificity - to let to precise edits - one strategy: increase Cas9 specificity is to pair two different Cas9 enzymes such that each enzyme cuts just one strand of DNA -  A double‐strand break can be generated by targeting two nCas9s to adjacent PAMs at a desired locus with two different sgRNAs.
2. Additional Cas nucleases from bacteria and archaea that recognize alternative PAMs (Cpf1) - Unlike Cas9 that cuts both strands of DNA at the same location, Cpf1 generates a cut with a 5′ overhang, creating “sticky” ends that could be exploited to insert a sequence of interest through complementation and ligation.
3. Two key features are pivotal to Cas9's utility: it can generate double‐stranded breaks and the double‐stranded break location is determined by guide RNAs.
4. dCas9: Mutating each of the catalytic domains of Cas9 results in a protein - fusing other protein to dCas9 

![Figure 5](https://wol-prod-cdn.literatumonline.com/cms/attachment/efa8f010-4a53-4512-aeb4-152351599de3/bmb21108-fig-0005-m.jpg)
**Figure 5: dCas9 can bring different enzymatic activities to precise genomic locations.**
Through attaching different protein domains to dCas9, this modified version of the CRSISPR/Cas9 RNP can be used to repress gene expression (A), activate gene expression (B), add epigenetic modifiers (C), or tag DNA sequences with a fluorescent protein (D).

# Ethical Implications for CRISPR/Cas9 Genome Editing In Humans
1. this technology has the potential to treat and cure diseases by editing the DNA associated with a particular disease before a baby is born.
2. non‐viable triploid embryos
