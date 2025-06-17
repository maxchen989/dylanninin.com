---
layout: post
title: SQL is not Objective Oriented Programming, so the best test is integration testing but not unit test
categories: [Post]
tags : [post,engineer]
---

就算使用tsqlt，還是無法跨DB做Fake Table，這不像OOP一樣方便做Mock。

而且就算你強制做，做出來的Code也難以維護，因此做好的做法是測試結果，做整合測試。

> 就是：把sp結果塞到table，然後對其做各種測試。