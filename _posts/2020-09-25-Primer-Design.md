---
title: Primer Design
categories: 
- biology
tags: 
- biology
---
引物设计的核心：扩增特异性 + 扩增效率

# 引物长度（18-30bp）—— 决定退火温度
1. 在引物长度小于20bp时：[4(G+C)+2(A+T)]-5℃
2. 在引物长度大于20bp时：62.3℃+0.41℃(%G-C)-500/length-5℃
3. 引物越长，越难通过退火结合到靶细胞上
4. 每增加一个核苷酸，引物特异性提高4倍
5. 不应大于38bp，因为过长会导致其延伸温度大于74℃，不适于Taq DNA聚合酶进行反应

# Tm值
1. Tm值在72℃左右可使复性条件最佳，至少要在55-80℃之间

# 退火温度
1. 退火温度不低于54℃的最短的引物可获得最好的效率和特异性
2. 退火温度需要比解链温度低5度
3. 如果引物碱基数较少，可以适当提高退火温度，这样可以使PCR的特异性增加
4. 如果引物碱基数较多，可以适当降低退火温度，使DNA双链结合
5. 一对引物的退火温度相差4℃～6℃不会影响PCR的产率，但是理想情况下一对引物的退火温度是一样的，可以在55℃～75℃间变化。
6. 引物的ΔG值最好呈正弦曲线形状，即3’端ΔG值较低，而5’端和中间ΔG值相对较高

# GC含量
1. 40～60%，以45-55%为宜
2. 上下游引物GC含量和Tm值要保持接近，如果引物存在严重的GC倾向或AT倾向，则可以在引物5’端加适量的A、T或G、C尾巴

# 避免扩增模板的二级结构区域
1. 待扩区域自由能（△G）小于58.6lkJ/mol时，扩增往往不能成功
2. 若不能避开这一区域时，用7-deaza-2’-脱氧GTP取代dGTP对扩增的成功是有帮助的。

# 与靶DNA的错配
1. 当被扩增的靶DNA序列较大的时候，一个引物就有可能与靶DNA的多个地方结合，造成结果中有多个条带出现。这个时候有必要先使用BLAST软件进行检测
2. 将引物序列粘贴到1区，将靶DNA序列粘贴到2区，这两者可以互换的，并且BLAST会计算互补、反义链等多种可能，所以不需要用户注意两条链是否都是有义链。如果知道序列在数据库中的GI号也可以直接输入GI号，这样就不用粘贴一大段的序列了。最后在3处点击Align就可以查看引物在靶DNA中是否有多个同源位点了。

# 引物末端
1. 引物3’端是延伸开始的地方，因此要防止错配就从这里开始
2. 3’端不应超过3个连续的G或C，因这样会使引物在G+C富集序列区错误引发
3. 3′端也不能有形成任何二级结构可能，除在特殊的PCR（AS-PCR）反应中，引物3′端不能发生错配
4. 如扩增编码区域，引物3′端不要终止于密码子的第3位，因密码子的第3位易发生简并，会影响扩增特异性与效率。
5. 引物3’端的碱基一般不用A，因为A在错误引发位点的引发效率相对比较高。
6. 引物3’端出现3个以上的连续碱基，如GGG或CCC，也会使错误引发机率增加。

# 引物5’端
1. 引物5’端序列对PCR影响不太大，因此常用来引进修饰位点或标记物。

# 引物的二级结构
1. 引物自身不应存在互补序列，否则引物自身会折叠成发夹状结构，这种二级结构会因空间位阻而影响引物与模板的复性结合
2. 若用人工判断，引物自身连续互补碱基不能大于3bp。
3. 两引物之间不应该存在互补性，尤应避免3′端的互补重叠以防引物二聚体的形成
4. 一般情况下，一对引物间不应多于4个连续碱基的同源性或互补性。

# Reference
1. [科研干货丨手把手教你做PCR引物设计！](https://zhuanlan.zhihu.com/p/50089556)
2. [PCR引物设计原则之个人心得篇](http://www.ebiotrade.com/newsf/2006-4/2006429175034.htm)