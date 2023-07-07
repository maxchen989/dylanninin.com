---
layout: post
title: A workaround of Complex Power BI Desktop is So Slow When Developing | Power BI
categories: [Post]
tags : [post,power bi]
---

這陣子接觸到一個龐大又複雜的REPORT，有很多Hide pages and bookmarks，利用button轉換頁面。

然而每次轉換都耗費很久時間，開啟[Performance Analyzer](https://learn.microsoft.com/en-us/power-bi/create-reports/desktop-performance-analyzer)每次點一次button甚至要等到50s。

我找到的解法是去改 Loading tables simultaneously，將其調整到能夠吃最多資源。

![image](https://user-images.githubusercontent.com/29641586/208858669-aeba1112-e562-4727-8b4e-60c9a442d29a.png)

每台電腦不同，最佳配置也不同，需自行測試。

並且[把自動interact關掉](https://community.powerbi.com/t5/Desktop/is-there-a-way-to-disable-all-interactions-at-once/m-p/915454)，否則每次點到，又要load一次。

![image](https://user-images.githubusercontent.com/29641586/208866790-2970b88e-0956-4cd3-acca-c5bd26dead3f.png)


我也同時把一些自動偵測關掉。
I got better performance by turning off all the auto detect features in settings. You will need "Auto date/time" on if you do not have a designated Date Table/Dimension.

調整後大約每點一次5秒，算順暢了。

![image](https://user-images.githubusercontent.com/29641586/208859002-03205eaa-907f-4399-9fc2-b23d2803e20f.png)


https://community.powerbi.com/t5/Desktop/Power-BI-Desktop-is-So-Slow-Developing-Making-Model-Changes/m-p/842011

