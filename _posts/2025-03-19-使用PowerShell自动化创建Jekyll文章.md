---
layout: post
author: "Zengle"
categories: [Technology] 
tags: [automation, Jekyll]
image: flower-3.jpeg
---


本文介绍如何通过PowerShell脚本实现Jekyll博客文章的自动化创建，有效提升内容发布效率。

<!--more-->

## 脚本功能特性
✅ 自动生成合规文件名  
✅ 预设Front Matter模板  
✅ 支持中文路径编码  
✅ 自动校验生成结果

## 完整操作流程

### 1. 打开PowerShell终端
```powershell
# 导航至博客根目录
cd D:\Projects\ZenBlog
```

### 2. 执行自动化脚本
```powershell
# 生成带时间戳的文件名
$currentDate = Get-Date -Format "yyyy-MM-dd"
$newPost = "_posts\$currentDate-技术文章模板.md"

# 构建Front Matter模板
$frontMatter = @"
---
layout: post
title: 技术文章模板
categories: [Technology]
date: {currentDateTime}
---

这是通过脚本自动生成的摘要内容...

<!--more-->

## 正文内容
请在此处开始撰写文章正文
"@ -replace "{currentDateTime}", (Get-Date -Format "yyyy-%m-%d %H:%M:%S %z")

# 写入文件（UTF-8无BOM编码）
$utf8NoBom = New-Object System.Text.UTF8Encoding $false
[System.IO.File]::WriteAllText($newPost, $frontMatter, $utf8NoBom)
```

### 3. 验证生成结果
```powershell
# 查看生成文件
Get-Item $newPost | Select-Object FullName, Length, LastWriteTime

# 查看文件内容
Get-Content $newPost -Encoding UTF8
```