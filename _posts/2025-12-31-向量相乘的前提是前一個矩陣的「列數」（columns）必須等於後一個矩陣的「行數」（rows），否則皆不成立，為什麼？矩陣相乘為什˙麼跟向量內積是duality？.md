---
layout: post
title: 向量相乘的前提是前一個矩陣的「列數」（Columns）必須等於後一個矩陣的「行數」（Rows），否則皆不成立，為什麼？矩陣相乘為什˙麼跟向量內積是Duality？
categories: [Post]
tags : [post,math]
---


<img width="179" height="122" alt="Image" src="/maxchennote.com/assets/images/issues/e604a4af-0ea5-45a2-a51b-30ae38d39b55.png" />
<img width="179" height="122" alt="Image" src="/maxchennote.com/assets/images/issues/e604a4af-0ea5-45a2-a51b-30ae38d39b55.png" />

向量（或矩陣）相乘的前提是：前一個矩陣的「列數」（Columns）必須等於後一個矩陣的「行數」（Rows）。

1. 運算過程的「對應關係」
當我們計算兩個矩陣 A 與 B 相乘時，結果中的每一個元素都是由 A 的**橫向列（Row）與 B 的縱向行（Column）**進行「一般矩陣乘積」或「內積」得到的。(這裡其實有兩種乘法，一般矩陣乘積方法以及向量方法) [矩陣乘法](https://zh.wikipedia.org/zh-tw/%E7%9F%A9%E9%99%A3%E4%B9%98%E6%B3%95)
 * 操作方式： 你拿左邊的第一個數乘上右邊的第一個數，第二個乘第二個，依此類推，最後加總。
 * 關鍵點： 如果左邊橫向有 3 個數字（3 列），但右邊縱向只有 2 個數字（2 行），那麼左邊最後一個數字就會找不到對象可以乘。
這就像是「拉鍊」： 左右兩邊的齒數必須一樣多，拉鍊才能順利合上。
2. 線性變換的「接力賽」
在數學意義上，矩陣相乘代表的是連續的空間變換。
假設向量 v 先經過矩陣 B 轉換，再經過矩陣 A 轉換，這寫作 A(Bv)。
 * 矩陣 B 的輸出維度，必須等於矩陣 A 的輸入維度。
 * 如果 B 把一個 2D 向量變成了 3D 向量（輸出 3 維），那麼接下來的 A 就必須有能力處理 3D 向量（輸入 3 維）。
如果這兩個數字不相等，就像是你要把一個三孔插頭插進一個二孔插座，物理上（數學上）是無法銜接的。
總結規則（口訣）
假設矩陣 A 是 m * n，矩陣 B 是 p * q：
 * 中間兩個數字必須相同： 也就是 n = p（前寬等於後高）。
 * 外側兩個數字決定結果： 相乘後的結果矩陣大小會是 m * q。



---

向量内積代表投影但同時又是線性轉換？沒錯就是這樣，因為他們之間是Duality。

所謂Duality<=>Natural-but-surprising correspondence, 自然但出乎意料的一致。

### [向量內積定義](https://zh.wikipedia.org/zh-tw/%E5%90%91%E9%87%8F)
內積是向量與向量的乘積，其結果為一個純量。

幾何上，內積可以定義如下：
<img width="333" height="34" alt="Image" src="/maxchennote.com/assets/images/issues/b2f39fb9-40b4-45ea-b941-44f27d5e58cb.png" />

<img width="331" height="46" alt="Image" src="/maxchennote.com/assets/images/issues/2b20ad55-38fb-40a7-aed3-afecab9fea58.png" />

我的理解是這樣，向量內積a。b的定義就是b向量在a向量的投影量，然而其實說投影量不那麼準確，因為投影好像是如果b比a長，那麼最終還是不會超過a，但其實這樣忽略了向量的大小，所以上面向量內積更準確的定義是這樣寫的：
 
b向量在 a向量方向上的投影長度（同方向為正反方向為負號），**與 a向量長度的乘積**。

還有**a向量長度的乘積。**，也就是還要考慮到a向量的大小。

其實就等於再說有一個Transformation matrix b transform將a向量轉換為一維數線 <=> 或者有一個Transformation matrix a transform將b向量轉換為一維數線。

而投影就是降維，向量內積既降維又考慮原本大小，而Transdoemation matrix本身也是降維又考慮原本大小，所以兩者是Duality。

總結：矩陣相乘是「空間到空間」的映射，而向量內積是「空間到數線」的映射。兩者的前提條件（維度必須匹配）是一致的，因為它們本質上都是在處理**「輸入」與「處理能力」之間的對接**。因此矩陣相乘是「空間變換」的接力，那麼向量相乘內積 其實可以看作是這種變換的一個極致簡化版，在線性代數中，這種關係被稱為「對偶性」（Duality）。