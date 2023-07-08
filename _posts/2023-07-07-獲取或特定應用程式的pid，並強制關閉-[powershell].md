---
layout: post
title: 獲取或特定應用程式的PID，並強制關閉 [Powershell]
categories: [Post]
tags : [post,powershell]
---

以excel為例
```

# 獲取所有 Excel 進程
$excelProcesses = Get-Process -Name "excel" -ErrorAction SilentlyContinue

# 终止每個 Excel 進程
if ($excelProcesses) {
    foreach ($process in $excelProcesses) {
        $processID = $process.Id
        Write-Host "Terminating Excel process with PID: $processID"
        $process.Kill()
    }
}
else {
    Write-Host "No Excel processes found."
}

```