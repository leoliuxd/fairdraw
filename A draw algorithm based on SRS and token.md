# A Draw Algorithm Based on SRS and Token
## Introduction
In 1995，the prototype of Art Toys were designed first by independent work studios and designers in Japan and Hong Kong；In 1999,Michael,an cartoonist in Hong Kong, hosted a personal exhibition, in which the 12 inch toys are named "Art Toy"，and the trend started to sweep the city；In 2005,independent work studios and designers of Art Toy arisen in Chinese Mainland;During 2015 and 2016，Art Toy communities、e-commercial platform and certain brands were launched gradually; In 2022,POPMART had IPO in HKEx,Art Toy,as a brand-new business has attracted increasing attention.
With the growing of Art Toy culture,various playing methods have appeared,such as Platform Toy,Blind Box,Lucky Bag,Ichiban Kuji etc. And Blind Box,Lucky Bag and Ichiban Kuji are specially popular among players for the fun and playfulness,here is the introduction of the history and strategy.
### 1. Blind box
Blind box traces back to Lucky Bagand Capsule Toys originated in Japan,all of which size the the curiosity of consumers,based on the "randomness".Inside the box are toys of different styles,usually composing a 12pcs set. Player will not know what exactly the style is until the box is opened, that means there may be surprise,comparing to the money paid for the box. The price of the toys will not be too high, so lots players can afford for it.
### 2. Lucky Bag
When it comes to the origin of "Lucky Bag", a widely accepted theory is that in the Edo period, on New Year's Day,the Daimaru Kimono(the predecessor of Daimaru Department Store) put some leftover material of kimono into bags,for sale at a low price.Among the bags, some are filled with kimono belt weaved with golden thread, who buys this kind of bag will be blessed with a whole year's lucky.It stimulated consumption and other shop followed.During the hundred years, Lucky Bag spread out and evolved, now has became the commercial behavior in Japan on New Year's Day. Now in other countries and areas, Lucky Bag is also introduced as a way of sale.  
### 3. Ichiban Kuji
Ichiban Kuji is invented and issued by Banpresto, owned by Bandai,one of the most famous comprehensive entertainment enterprises in Japan. The goods contains garage kit,plush toys, groceries,etc.
## Simple Random Sampling
The strategy of Blind Box,Lucky Bag and Ichiban Kuji conform to Simple Random Sampling(SRS) without replacement.A simple random sample is a randomly selected n-size subset of a N-size population. In this sampling method, each member of the population has an exactly equal chance of being selected.
## Problems
With the commercialization of Art Toys,more and more entities involved,meanwhile, some chaotic phenomenas came into existence.
   1. Some merchants perform dishonest acts or statements, to obtain improper benefit from consumers.In their independent MiniApp,App and website, fairness,justice and transparent are corrupted,through many tricks,including modifying probability,specifying winners,reserving high-price goods,no-shipment,absconding with the money,etc.
   2. Some consumers also pick the high value goods through experience and technology.
   
These actions,not only harmed rights and interests of consumers,but also ruined the reputation of merchants in the business.
## A Draw Algorithm Based on SRS and Token
   To solve problems above，a draw algorithm based on Simple Random Sampling(SRS) and token is proposed，applicable for Blind box,Lucky Bag and Ichiban Kuji, ensuring fair,justice and transparent of the draw progress, and traceability of the result。
   The algorithm contains two main parts: creation of token, draw based SRS without replacement.Here is the pseudo code,describing how to create a draw activity composed of N items, and pick M items.
   <br>
1.Create Token
 ```
   Require: N ≥ 1
   i ← 0
   while i !=N   do
      Create a token with UUID[1]
      i ← i + 1
   end while
```
[1]：The Implementation of UUID algorithm varies in different programming languages, in JAVA *UUID.randomUUID()* ，copyright belongs to Oracle Corporation<br>
2.Random Draw
```
   Require: M ≥ 1
   j ← 0
   Get the set of tokens unused T
   Get the set of goods un-drawn G
   while j !=M   do
      Choose a token t,then remove t from T
      Shuffle G
      Get a random number k[3], k∈[0,Siz of G)
      Build relationship between goods G[k] and token t，remove G[k] fomr G  
      j ← j + 1
   end while
```
[1]：The Implementation of Shuflle-of-a-Set Algorithm varies in different programming languages, in JAVA *Collections.shuffle(List<?> list)* ，copyright belongs to Oracle Corporation<br>
[1]：The Implementation of Random Number-Generation Algorithm varies in different programming languages, in JAVA *Random.nextInt()* ，copyright belongs to Oracle Corporation<br>


## Conclusion
Blind Box,Lucky Bag,Ichiban Kuji ,Lottery tool, and Redeem tool can be built base on the draw algorithm.

---

# 一种基于令牌机制的随机抽选算法
## 导言
1995年，潮玩首次以工作室或独立设计师形式出现在香港和日本；1999年漫画家Michael策划了自己的公仔个展，也正是从这时候开始12寸的公仔开始被定义为“潮流玩具”，这一股“潮玩之风”席卷了整个中国香港；2005年中国大陆开始出现潮玩工作室与独立的设计师；2015年至2016年，潮玩社区电商平台以及玩具收藏品牌开始上线；2022年泡泡玛特（POPMART）正式在港交所上市，潮玩作为一种新的商业模式被更多人重视。
伴随着潮玩文化的发展和壮大，各种玩法层出不穷，例如大娃、吊卡、盲盒、福袋、一番赏等。其中，盲盒、福袋、一番赏因其玩法的趣味性受到了很多玩家的喜爱，下面介绍下这三种玩法的历史和机制。
### 1. 盲盒
盲盒的玩法最早可追溯到日本的福袋、扭蛋，它们都是紧扣消费者猎奇心理，其中最吸引人的因素就是“随机性”。盲盒里装着不同样式的玩偶手办，这些玩偶大多都是12个一套，密封在同样的包装盒中。抽盲盒的时候无法预知盒子里是哪一款，只有开盒后才能知道。消费者在购买时对盲盒中的物品增加了期待值，开盒的时候的结果可能超出预期，更增加了惊喜感。盲盒中单个商品的价格在数十元到百元不等，很少超过100元。
### 2. 福袋
商业中的“福袋”起源，流传较广的一种说法是江户时代的大丸和服店(现在的“大丸百货”)在新年之际，将边角余料的布头塞在袋子里便宜销售，其中有些袋子里随机装入了用金线织的和服腰带，谁买到装有金腰带的袋子就会收获一年好运。这种销售方法非常刺激人们的消费欲望，于是其他卖家也纷纷效仿。如此慢慢流传开来，演变至今，福袋已经成为日本人新年伊始的一种商业习惯，称其为福袋文化也不为过。国内很多商家，包括潮玩商家在日常销售或者重大节日促销，也将自己的产品打包成福袋形式，消费者购买时，随机获取一款产品，有一定的概率买到价格超出付款价格的商品。
### 3. 一番赏
   一番赏是由日本最著名的综合性娱乐公司之一的万代公司旗下的日本老牌游戏娱乐公司Banpresto眼镜厂发行的系列娱乐产品的总称。所有商品均为一番赏限定品，涵盖手办、毛绒玩具、杂货等多种商品种类。
## 简单随机抽样
   盲盒、福袋、一番赏的行为模式符合简单随机抽样中的不放回抽样。所谓简单随机抽样（Simple Random Sampling，简称SRS），是从总体N个单位中随机地抽取n（n<=N）个单位作为样本，使得每一个容量为样本都有相同的概率被抽中,其特点是：每个样本单位被抽中的概率相等，样本的每个单位完全独立，彼此间无一定的关联性和排斥性。
## 存在问题
   当潮玩逐渐商业化之后，越来越多的商家进入这一赛道，一些乱象也随之而来。
   1. 部分不法商家也开始使用一些手段欺诈消费者获取高额不正当利益。主要方式是在自有小程序、App、网站等C端入口破坏玩法公平、公正、公开性，包括但不限于操作概率，指定内部人员获得高价值商品，通过高科技提前挑选高价值商品留作自用，不发货卷款跑路等。
   2.  部分C端玩家也利用商品的差异，如重量、体积等，通过摇盒，称重等方式挑选高价值商品

   这些做法不仅直接损害了消费者的权益，而且对从事相关行业的商家和用户也造成了负面影响。
## 一种基于令牌机制的随机抽选算法
   基于以上问题，本文提出了一种基于令牌机制的随机抽选算法（以下统称为：随机抽选算法），用于盲盒、福袋、一番赏等产品形态（以下统称为：抽选活动），保证抽选的公平、公开、公正，以及结果的可追溯。
   该算法包括两部分，令牌的创建和简单随机抽取（不放回）。下面用伪代码进行描述，如何创建一个含有N（N>=1）个商品的抽选活动， 以及随机抽取M个商品过程。<br>
1.令牌创建
 ```
   Require: N ≥ 1
   i ← 0
   while i !=N   do
   	使用UUID创建一个随机令牌[注1]
   	i ← i + 1
   end while
```
注1：UUID的产生算法不同编程语言有不同实现，JAVA中使用*UUID.randomUUID()* 方法，版权属于Oracle公司<br>
2.随机抽选
```
   Require: M ≥ 1
   j ← 0
   获取未使用的令牌集合T
   获取未被抽选的商品集合G
   while j !=M   do
   	从T中选取一个令牌t，并将t从T中移除
   	G中元素打乱排序[注2]
   	获取一个随机数k[注3]，k∈[0,G的集合大小)
   	将商品G[k]与令牌t关联，并将G[k]从G中移除  
   	j ← j + 1
   end while
```
注2：集合元素顺序打乱算法不同的编程语言有不同实现，JAVA中使用*Collections.shuffle(List<?> list)* 方法，版权属于Oracle公司<br>
注3：随机数生成算法不同的编程语言有不同实现，JAVA中使用*Random.nextInt()* 方法，版权属于Oracle公司

## 结语
基于随机抽选算法，可以构建福袋、一番赏、盲盒等产品，以及有摇号，抽签，兑换等工具。
