---
layout: post
title: Throw vs Write-Error 有何差別？ [Powershell]
categories: [Post]
tags : [post]
---

`throw` 和 `Write-Error` 是在 PowerShell 中處理錯誤的不同機制。

`throw` 關鍵字用於拋出異常，它會中斷當前的代碼執行，並將控制權交給上層的 `catch` 塊或調用棧中的異常處理程序。當使用 `throw` 拋出異常時，你可以選擇指定一個異常消息，以提供關於異常原因的信息。

`Write-Error` 是用於在控制台輸出錯誤消息，並且不會中斷代碼的執行。它通常用於在出現非致命錯誤或異常情況時提供警告或記錄錯誤信息。 `Write-Error` 不會中斷代碼執行，因此在執行 `Write-Error` 後的代碼仍然會繼續執行。

下面是這兩種機制在使用上的一些差別：

- `throw` 關鍵字用於拋出異常，可中斷代碼執行並將異常傳遞給上層處理程序。
- `Write-Error` 用於輸出錯誤消息，不會中斷代碼執行。
- `throw` 可以自定義異常類型，可以在 `catch` 塊中捕獲並進一步處理。
- `Write-Error` 輸出的錯誤消息可以在控制台中看到，但不能在調用棧中捕獲。

在異常處理的過程中，你可以根據情況選擇使用 `throw` 或 `Write-Error`：

- 如果遇到需要立即停止代碼執行並將控制權傳遞給上層處理程序的嚴重錯誤或異常，使用 `throw` 拋出異常是一個更好的選擇。
- 如果你只需要在控制台輸出錯誤消息或記錄錯誤信息，而不需要中斷代碼執行，可以使用 `Write-Error`。