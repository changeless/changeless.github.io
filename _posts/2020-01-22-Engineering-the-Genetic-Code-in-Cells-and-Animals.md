---
title: Engineering the Genetic Code in Cells and Animals
categories: 
- biology
tags: 
- biology
---

## Background
1. The genetic code uses 61 codons to specify 20 common amino acids and 3 stop codons for termination in protein translation.
![translation](https://pic4.zhimg.com/80/v2-1ea42199b0f6c560329de50bcf94da53_hd.png)
2. This code is preserved in virtually all life forms on earth with minor variations.
3. In recent years, the genetic code has been expanded to encode unnatural amino acids (Uaas) by introducing into live cells a new **tRNA/aminoacyl-tRNA synthetase (aaRS) pair**, which is **orthogonal** to endogenous tRNA/aaRS pairs.

        orthogonal:指能在生物系统中发生而且不干扰内源性生物化学过程的化学反应
    
4. First expansion of the genetic code: 2001
5. Now: over 150 Uaas have been incorporated

## Developing a general method for expression orthogonal tRNAs in eukaryotic cellsand animals
Challenge: how to functionally express an orthogonal tRNA, often derived from prokaryotes, in eukaryotic cells.
1. Prokaryotic tRNAs: transcribed through promoters upstream of the tRNA gene
2. Eukaryotic tRNA: transcribed through promoters elements within the tRNA known as the A- and B- box (conversed among Eukaryotic tRNA but absent in prokaryotic tRNA)

Solution:
1. The **type-3 Pol III promoter** has promoter elements exclusively upstream of the coding sequence, does not require intragenic elements for transcription, and has a well-defined transcriptional initiation site.

    In eukaryote cells, RNA polymerase III (also called Pol III) transcribes DNA to synthesize ribosomal 5S rRNA, tRNA and other small RNAs. 
    (bacteria contain a single type of RNA polymerase, while eukaryotes (multicellular organisms and yeasts) contain three distinct types)

2. A type-3 Pol III promoter in combination with a 3’-flanking sequence can drive the functional expression of prokaryotic tRNAs in various mammalian cells 

## Generating Uaa-specific Synthetase for Use in Mammalian Cellsand Animals
Challenge: how to generate an orthogonal synthetase specific for the Uaa - Changing the synthetase substrate specificity from its cognate amino acid to a Uaa

    Aminoacyl tRNA synthetase: 既要识别特定的氨基酸，又要识别特定的tRNA，然后将两者连在一起。

Solution:
1. E. coli: generate large mutant synthetase libraries (>109 members) followed by high-throughput selection or screen. - low transfection efficiency
2. Evolve the E. coli synthetase in yeast and transfer the evolved tRNA/synthetase pairs for use in mammalian cells. 
3. The evolved E. coli TyrRS mutant can then be transferred for use in mammalian cells.
如果两个物种在进化的道路上早早就分道扬镳，他们的tRNA和氨酰tRNA合成酶一定相差较远，那么在此基础上进行优化，得到正交性好的tRNA-氨酰tRNA合成酶组合应该会简单不少。
-- E. coli and Methanocaldococcus jannaschii

![evolution](https://pic1.zhimg.com/80/v2-5af7e25571bbe7feda421370d69bf30c_hd.png)

## Optimizing aaRS Recognition of tRNACUA
To decode the amber stop codon UAG, the orthogonal tRNA has to change its anticodon to CUA, which may decrease the affinity of the resultant tRNACUA toward the synthetase, since anticodon is a major recognition element of most synthetases.


## Expanding Uaa Specificity of aaRS beyond Analogs of Native Substrate



## Reference
1. Wang, L.* Engineering the genetic code in cells and animals: biological considerations and impact. Acc. Chem. Res. 50:2767-2775 (2017)
2. [蛋白里混进了奇怪的东西：非天然氨基酸的前世今生（二）
伯伯的花房子](https://zhuanlan.zhihu.com/p/24893936)



Expansion of the genetic code allows unnatural amino acids (Uaas) to be site-specifically incorporated into proteins in live biological systems, thus enabling novel properties selectively introduced into target proteins in vivo for basic biological studies and for engineering of novel biological functions.

Orthogonal components including tRNA and aminoacyl-tRNA synthetase (aaRS) are expressed in live cells to decode a unique codon (often the amber stop codon UAG) as the desired Uaa.
