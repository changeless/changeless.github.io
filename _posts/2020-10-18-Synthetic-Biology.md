---
title: Synthetic Biology
categories: 
- biology
tags: 
- biology
- Synthetic biology
---


【凌乱的合成生物学大事记（科普）- 如果以后与机会做合成生物学方向再来补充，合成生物学真有意思\^-^/ 】

1. 2010 J. Craig Venter研究所（JCVI）的研究团队完整的合成了一个细菌基因组 - DNA合成和组装可以扩展到兆碱基大小
2. 2016 Chris Voigt (MIT) Cello - 用于大肠杆菌中的逻辑基因电路设计，这是一种出色的端到端计算机辅助设计系统
3. 2016 Craig Veter 迄今为止拥有最小基因组的生命Synthia 3.0诞生了
4. David Baker研究团队 - 让人工合成的功能蛋白成为了酵母细胞中基因线路的关键组分
5. 2006年以来 George Church 将每个TAG终止密码子突变为TAA密码子 - 希望最终能够省出一个密码子用于非天然氨基酸的高效引入
6. CRISPR先驱 - TALENs（TAL-Effector核酸酶）
7. Golden Gate Assembly现在在基因构建过程中主导方法之一，通过Addgene共享的许多模块化克隆（MoClo）工具箱和遗传元件库
8. 2019 剑桥 大肠杆菌在合成基因组上也取得了进一步的进展：我们删减了基因组上的3个密码子，这使得我们可以在细胞内引入更多的非天然氨基酸分子。同时我们还可以在生物中引入非天然核酸，并实现了非天然核酸-非天然氨基酸的编码与解码过程。
9. “分子记录仪Molecular Recorder” - 通过重组酶或者CRISPR在细胞生长过程中对基因进行修改来储存信息
10. 2019年合成生物学年度进展回顾

# 基因（组）编辑、合成和组装领域
## 开发更加精准、高效的的基因编辑工具
1. Harvard David Liu - Prime Editing “Search-and-replace genome editing without double-strand breaks or donor DNA”
精确、高效和高度通用的方式直接编辑人体细胞，可以有效地进行四种类型的单碱基置换：C到T，T到C，A到G和G到A
可能纠正多达89％的已知致病基因变异

## 利用基因编辑工具治疗重大遗传病
1. 北京大学 邓宏魁 “CRISPR-Edited Stem Cells in a Patient with HIV and Acute Lymphocytic Leukemia”
利用CRISPR技术编辑干细胞治愈艾滋病毒和急性淋巴细胞白血病患者治疗领域取得关键进展

## 基因组的合成和改造能力进一步增强
1. 剑桥 Jason W. Chin - Total synthesis of Escherichia coli with a recoded genome
人工合成并替换了全部的4Mb大肠杆菌基因组，并将其中丝氨酸的密码子TCG和TCA替换为同义密码子AGC、AGT，琥珀密码子TAG替换为TAA，成功构建一株只有61个密码子的大肠杆菌，从而为重编码多种非标准氨基酸奠定了基础。

2. 剑桥 Jason W. Chin - Programmed chromosome fission and fusion enable precise large-scale genome rearrangement and assembly
利用基因组工程改造技术将细菌的基因组改成为任意不同大小的环化基因组对，同时通过基因组融合技术，将来自不同菌株的基因组区域组装成一个单一的基因组

3. Ben Black - 设计可以绕开着丝粒DNA序列的人类人工染色体\
此种人工染色体无需大阵列的着丝粒α-卫星重复序列，从而能够为人工基因组设计带来极大的便利，移除了哺乳动物合成基因组的关键阻碍

4. 人类基因组编写计划（Human Genome Project-Write）
旨在通过对人类基因组进行从头合成编码，在10年之内将大基因组（大到1000亿对碱基）的改造和测序成本再降低1000倍
满足人体器官移植日益增长的需求
通过基因组水平的基因改造技术，创造出抵抗所有病毒的细胞株
创造能够抵抗癌症的细胞株系
利用人体细胞或者类器官高效的生产疫苗和药物


# 元件开发与基因线路设计
## 开发多种优质调控工具和传感器工具
1. 英国帝国理工学院 Tom Ellis “Engineering a Model Cell for Rational Tuning of GPCR Signaling”
通过对于酵母基因组的GPCR信号感应系统进行工程化改造，可以使酵母作为高灵敏、价格低廉的生物传感器用于疾病、感染因子和药物分子的监测和响应。 

2. 苏黎世联邦理工学院 Martin Fussenegger团队
设计了一种可通过感受体表感觉来调节治疗性蛋白质的生产的生物开关
用于治疗糖尿病和肌肉萎缩症

3. 中国华东师范大学 叶海峰研究团队
可以响应绿茶成分的开关 ：当人体植入某种定制化细胞后，人们只需通过饮用特制的浓缩绿茶，便可使其在体内产生代谢物原儿茶酸进而控制细胞中目的基因的表达
而这种目的基因可按照需求调整改变，可以变为提高人体免疫力的抗体，也变为清除体内有害分子的酶，还可以变为降低血糖的胰岛素

4. 英国爱丁堡大学 Baojun Wang研究团队
- 设计了更加灵敏的重金属感应系统来进行环境污染检测，其灵敏度和便捷实用程度得到了进一步的优化和提升

5. 加州理工学院 Mikhail G. Shapiro “Ultrasound imaging of gene expression in mammalian cells”
设计了哺乳动物细胞中基因表达的超声成像系统。
将超声造影剂与哺乳动物细胞中的基因表达联系起来，研究团队在细胞内引入了经过改造的声波报告系统
哺乳动物的声学报告基因可以使细胞以低于0.5％的体积密度可视化，并可以对活体动物中的基因表达进行高分辨率成像。

6. 斯坦福大学 Michael Z. Lin研究团队 “A compact synthetic pathway rewires cancer signaling to therapeutic effector release”
开发了一种名为RASER的技术用于癌症治疗：重编程异变信号，使其成为效应因子
利用合成生物学方法构建了一个可以响应这些癌症激活信号的通路（蛋白质基因线路—蛋白酶+磷酸化结合位点+下游信号拓展）
只要细胞发生癌变，这个合成的信号通路就会被激活从而在下游表达一些效应因子
而这些效应因子可以做很多事情，比如利用dCas9调控癌症细胞基因的表达或者激活细胞自噬的过程，从而导致癌症细胞的凋亡。

7. 英国爱丁堡大学 Baojun Wang
设计了报导了第一种“类真核”的原核CRISPR基因激活装置
该研究利用了原核生物中σ54因子的一种特殊“闭锁技能”，实现了高质量的CRISPR激活调控。

## 利用蛋白质设计开发全新蛋白质功能，取得关键突破
1. 美国 David  Baker研究团队 “De novo design of bioactive protein switches”
从头设计自然界不存在的生物活性蛋白质开关LOCKR和生物反馈网络degronLOCK

2. 加州大学 Tanja Kortemme “Computational design of a modular protein sense-response system“
进一步利用蛋白质计算设计工具设计了模块化蛋白质感应系统

## 合成生物学领域在计复杂基因线路的能力进一步增强
1. MIT James Collins团队 “Complex signal processing in synthetic gene circuits using cooperative regulatory assemblies”
使用人工设计的真核系统协同调控组件在合成基因电路中进行复杂信号处理

2. MIT的Michael Laub Chris Voigt
设计了与大肠杆菌本身完全正交的双组分信号传导网络，并指出旁系同源物的序列空间具有相对稀疏性，新的正交途径在进化过程中很容易出现或者可以完全从头设计。

3. 苏黎世联邦理工学院 Mustafa Khammash研究团队 “A universal biomolecular integral feedback controller for robust perfect adaptation”
设计了一种可以实现完美自适应的生物分子积分反馈控制器

# 宿主和生物群系工程
## 设计非天然生物系统，扩展生命的可能性
1. 美国 Steven Benner研究团队 “Hachimoji DNA and RNA: A genetic system with eight building blocks”
阐述了“八碱基遗传系统”
研究人员人工开发了两对新的核苷酸碱基对，分别是S:B和Z:P。
这两种新的碱基对均以氢键形式配对，具有储存遗传信息、满足达尔文进化需求、满足遗传信息传递的能力。
这项工作将原本人体内的4种核酸碱基拓展到了8种核酸碱基，进一步丰富了生命的遗传信息，拓展了生命进化方向以及宇宙中生命存在的可能性。

2. 德国 Edward Lemke “Designer membraneless organelles enable codon reassignment of selected mRNAs in eukaryotes”
设计了一种人造无膜细胞器，其可以在哺乳动物细胞中进行正交翻译

## 利用宿主进行天然或者非天然物质的按需生产
1. Jay Keasling研究团队 “Complete biosynthesis of cannabinoids and their unnatural analogues in yeast”
在酵母中合成了大麻素等多种衍生分子

2. 美国伊利诺伊大学香槟分校 Wilfred A. van der Donk研究团队
- 阐述了一种特殊的天然产物合成方式：核糖体合成的小肽充当非核糖体肽延伸和化学修饰的支架，氨基酸则通过这种骨架转移到肽的羧基末端，而这种化学反应与核糖体无关

## 改造和设计宿主解决人类社会挑战
1. 美国 Donald R. Ort研究团队
- 利用合成生物学手段在转基因烟草植物中构建了一种新的代谢途径，其可以更有效地重新捕获光合作用的副产物，同时减少植物的能量损耗。

2. 哥伦比亚大学 Tal Danino研究团队
通过对细菌进行编程，可使其表达CD47抗肿瘤蛋白，可以诱导持久的肿瘤消退和全身性抗肿瘤免疫，对患者癌症有极大的改善。

3. MIT Tim Lu研究团队
通过定向进化和结构建模对细菌体的用于识别宿主的尾部结构进行工程改造

## 探索合成群系系统的复杂原理，为创造复杂系统建立基础
1. 中国科学院 刘陈立研究团队 “An evolutionarily stable strategy to colonize spatially extended habitats”
揭示了生物菌群迁移进化过程中的竞争规律

2. 多国的科研人员
阐述了工程化改造生物群系的一般原则，为合成生物学设计和探索更复杂生物群体提供了指导和方向。

3. UCSD Jeff Hasty研究团队 “Rock-paper-scissors: Engineered population dynamics increase genetic stability”
利用工程化的动态种群提高了基因线路的遗传稳定性

## 数据集成、建模和自动化
1. 全球合作推动设施共建、标准共享与数据互通
2. 利用机器学习等AI技术推动合成生物学复杂设计

# Reference
1. [再创丨2019年合成生物学年度进展回顾](https://mp.weixin.qq.com/s/7keGwa86ZZYj8hxbyho7Lw)
2. [再创丨合成生物学第二个十年：2010–2020](https://mp.weixin.qq.com/s/MYfK1gBjC-LrYDN2W2YsAA)
