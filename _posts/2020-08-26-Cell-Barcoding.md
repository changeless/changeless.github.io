---
title: Cell Barcoding
categories: 
- biology
tags: 
- Barcode
---


Cellular barcoding is a technique in which individual cells are labeled with unique nucleic acid sequences ,termed barcodes, so that they can be tracked through space and time.
Cellular barcoding can be used to track millions of cells in parallel, and thus is an efficient approach for investigating heterogeneous population of cells.
Although the advent of single-cell RNA sequencing (scRNA-seq) technology has made it possible to routinely obtain a snapshot of the transcriptome of thousands of single cells, it remains challenging to track individual cells over space and time with similar throughput. 

## Principles and methods of cellular barcoding
### Labeling cells with nucleic acid sequences
### Methods of barcode delivery
1. Easiest way: manually assign individual barcodes to cells one by one
2. Challenge: assign specific barcodes to individual cells
3. Currently, the most common, robust and efficient method to barcode individual cells relies on the production of a large pool pf barcoded vectors in vitro
4. The most common delivery method for such pooled barcode libraries is retroviral (including lentivirus) transfection, but other viruses such as Sindbis virus and pseudo-rabies virus can be used, as can nonviral delivery methods including plasmid injection and electroporation.
5. Given a sufficiently large number of barcodes relative to the number of transfected cells, it is very unlikely that the same barcode will be transfected into two different cells. Every transfected cell is therefore uniquely labeled by the barcode it takes up.
6. Brainbow: in vivo barcode generation centered on the action of a DNA recombinase on an array of possible targets. - in Brainbow, Are recombinase, which can excise or flip DNA sequences flanked by specific recognition sequences, acts on an array of fluorescent protein open reading frames. Repeated Cre action leads to stochastic shuffling and collapse of the target array, generating different combinations of fluorophores in each cell that can be distinguished by imaging.
7. Generate higher barcode diversity in vivo by replacing fluorophores with shorter DNA sequence that can be read out by sequencing, which make it possible to expand the array to contain more targets.
8. A fundamental drawback of recombinase-based barcoding approaches is that target arrays tend to be long and repetitive, as dictated by the low diversity of recombinase recognition sites and their minimum spacing requirements.

### CRISPR-based in vivo barcoding
1. Cas9-induced double-strand breaks in genomic DNA are often repaired by nonhomologous end joining (NHEJ)38, an error-prone mechanism that introduces short random insertions and deletions at the cut site - These untemplated changes to the parental sequence act as a short barcode that can be used to distinguish cells 
2. ScarTrace/ GESTALT/ MEMOIR
3. mSCRIBE - increase barcode diversity - guide RNA can be evolved to target the mutated genomic locus
4. Deletion leads to the collapse of the CRISPR barcodes over time 

### Methods of barcode readout
1. Nearly all work on cellular barcoding to date has relied on the extraction of nucleic acids followed by bar- code detection or quantification in vitro. 
2. Methods used to read out barcodes have varied with the available technology, beginning with PCR amplification and sizing and progressing to microarray detection, Sanger sequencing, and high-throughput sequencing.
3. scRNA-seq approach - simultaneous readout of a cell’s barcode and transcriptome.
4. The combination of cellular barcoding with scRNA-seq has been exploited in genome-wide screens, lineage- tracing approaches and neuroanatomy studies 
5. the MEMOIR method was used with highly multiplexed fluorescence in situ hybridization (FISH) to read out a combination of in vitro and CRISPR–Cas9-generated barcodes. Similarly, multiplexed FISH was used to register live images of bacteria to their cellular barcodes 

## Application of cellular barcoding
### Lineage tracing and fate mapping
#### Lineage tracing: the developmental history of a cell is decoded and a tree is produced
1. Require that cell in intermediate states receive distinct labels.

#### Fate Mapping: cells originating from a specific progenitor are marked identically, which can obscure information about intermediate steps.
1. Overcame the barcode-detection bottleneck by using microarrays for quantification - allow us to track thousands of barcode in parallel
2. Used in disease study: track cancer; track the emergence of drug resistance; investigate microbial evolutionary dynamics

### High-throughput screen
1. Traditionally - screen for gene function is performed one gene at a time
2. Every strain was tagged with a different barcode sequence - lay a foundation for functional genomics and generating deep insights into cell biology.
3. Researcher developed short hairpin RNA (shRNA) screens in which each shRNA construct is tagged with a know unique barcode sequence - allow the first genome-wide screens in mammalian cells

### Mapping the brain with barcodes
### Barcodes as molecular recoding device
1. CRISPR-Cas9-Based mScribe system: mScribe uses the rate of barcode divergence from the ancestral sequence to record the intensity or duration of inflammatory stimulation by placing the mutagenic Cas9 under the control of an inflammation-responsive promoter

## Outlook
Limitation:
1. in vivo barcoding methods currently do not produce diverse enough barcodes to uniquely label every cell in many organs, including even small mammalian brains 
2. the biases with which barcodes are generated in vivo are not sufficiently understood 
3. although encouraging progress has been made, the functionalization of barcodes to read out neuroanatomical features and lineage is still at an early stage in its development. Specifically, it is currently not possible to read out synaptic connectivity on the basis of barcoding at high efficiency, and lineage tracing based on barcodes is hampered by the lack of synchronization between barcode mutation and cell division. 
4. in situ readout of barcodes, or the cellular transcriptome, is currently slow, inefficient or biased. More technological development is needed. 

## Reference
1. Cellular barcoding: lineage tracing, screening and beyond (Nature methods, 2018)
