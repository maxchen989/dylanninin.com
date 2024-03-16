---
layout: post
title: Day3 Visual Studio 開發及部屬第一個Excel Add-ins
categories: [Post]
tags : [post,ai_project0]
---

### 第一個Office 365 Plugins開發
這裡已經講得很清楚，就不再重複：[Build an Excel task pane add-in](https://learn.microsoft.com/en-us/office/dev/add-ins/quickstarts/excel-quickstart-jquery?tabs=visualstudio)

基本上就是兩個東西 [manifest](https://learn.microsoft.com/en-us/office/dev/add-ins/develop/xml-manifest-overview?tabs=tabid-1)與web app.
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/95467b5b-5a32-4f25-bb75-6caceac2fb9b)


我是使用Visual Sutido開發，你需要安裝Office套件(如果一開始沒安裝，在Visual Studio Installer可以安裝)。

### Publish Office 365 Plugins Project
這裡也講得很清楚：[Publish your add-in using Visual Studio](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/package-your-add-in-using-visual-studio)

而Office 365 Plugins你會需要Publish兩個東西，一個是web project，一個是manifest。
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/fa1849fa-9f81-4dad-9f9b-51f9af7c9440)

Visual Studio Publish的操作可以[參考](https://www.youtube.com/watch?v=022Q7fzoQ-Y)。

### Deploy and Publish Office 365 Plugins
可以參考[這裡](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish)，我是使用sideload方式(因為公司限制，無法使用microsoft 365 developer的sandbox，很多種部屬方法也有限制，所以我是使用sideload的web方法測試，測試起來也方便)。
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/4a90c1f5-11ce-42cb-bf17-c5966bf62a4d)

[Test Office Add-ins](https://learn.microsoft.com/en-us/office/dev/add-ins/testing/test-debug-office-add-ins#sideload-an-office-add-in-for-testing)
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/b7146d98-f0de-46a2-a8f8-3e105c6203f2)

[Manually sideload an add-in to Office on the web] ([內容擷取自)](https://learn.microsoft.com/en-us/office/dev/add-ins/testing/sideload-office-add-ins-for-testing)
This method doesn't use the command line and can be accomplished using commands only within the host application (such as Excel).

1. Open [Office on the web](https://office.com/). Open a document in Excel, OneNote, PowerPoint, or Word.

2. Select Home > Add-ins, then select More Add-ins.

3. On the Office Add-ins dialog, select the MY ADD-INS tab, choose Manage My Add-ins, and then Upload My Add-in.
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/e1307fe8-5af2-4461-af7c-f8a98d79847f)

5. Browse to the add-in manifest file, and then select Upload.
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/d4a4018e-57b5-476d-b961-8ed8aa431bc7)

7. Verify that your add-in is installed. For example, if it has an add-in command, it should appear on either the ribbon or the context menu. If it's a task pane add-in that has no add-in commands, the task pane should appear.
測試結果，成功！
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/d56aa0c4-6119-4223-b7ee-c6fe18205188)

### IIS架設
關於IIS的架設可以參考：[How to install IIS](https://www.youtube.com/watch?v=3NuMmgM0u4o) 
這是Web結果，記得IIS架設時要使用SSL，否則將無法使用Excel plugin。
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/e58ce3c8-0f42-4063-b757-58b9084bcfa1)
[Requirements for running Office Add-ins](https://learn.microsoft.com/en-us/office/dev/add-ins/concepts/requirements-for-running-office-add-ins)
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/ebd92809-6205-4ce9-a093-e46815b67302)

[註]IIS SSL設定
1. SSL Setting調整成如此
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/835e9d6c-dc1e-445b-9287-66acd23b8106)
2. url binding到443並設定ssl憑證
![image](https://github.com/maxchen989/dylanninin.com/assets/29641586/e19b7c86-c94b-4039-8636-7b9197072ba0)

### Debug Office 365 
可以參考[Debug add-ins using developer tools in Microsoft Edge (Chromium-based)](https://learn.microsoft.com/en-us/office/dev/add-ins/testing/debug-add-ins-using-devtools-edge-chromium)，基本上跟一般的Web debug一樣。

Reference:
https://learn.microsoft.com/en-us/office/dev/add-ins/quickstarts/excel-quickstart-jquery?tabs=visualstudio
[Can i publish Office add-in without having a corporate/company?](https://stackoverflow.com/questions/68092889/can-i-publish-office-add-in-without-having-a-corporate-company)
