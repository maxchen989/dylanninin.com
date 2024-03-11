---
layout: post
title: Day2 Office Plugin 四種開發方法
categories: [Post]
tags : [post,ai_project0]
---


![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/3e71e433-a410-4a73-9720-1308889ff391)

![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/d08f9200-52f8-4932-bf3f-22b23358ee8c)
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/c5637696-79e8-4360-8ebd-8243252001f7)

相較於使用 VBA、COM 或 VSTO 產生的加載項，Office 加載項提供下列優勢。

跨平台支援：Office 加載項在 Office web 版、Windows、Mac 和 iPad 中運作。

集中部署和分發：管理員可以跨組織集中部署 Office 加載項。

透過 AppSource 輕鬆存取：可透過將解決方案提交至 AppSource，使其可供廣大受眾使用。

基於標準 Web 技術：可以使用任何喜歡的程式庫來產生 Office 加載項。

--- 

以上內容取自[Office 加載項平台概述](https://learn.microsoft.com/zh-cn/office/dev/add-ins/overview/office-add-ins)

看來目前主流的Plug in 開發方法是使用web方法，崁入一個網頁的方式進行開發，且是利大於弊(完勝)。

https://learn.microsoft.com/zh-cn/office/dev/add-ins/develop/develop-overview