---
layout: post
title: 使用PowerShell自动化创建Jekyll文章
categories: [技术]
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
categories: [技术]
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

## 关键参数说明
| 参数                | 说明                          | 示例值                  |
|---------------------|-------------------------------|-------------------------|
| `$currentDate`      | 文件名的日期部分              | 2023-10-26             |
| `layout: post`      | 文章布局模板                  | 必须保持post           |
| `categories: [技术]`| 分类标签                      | 需与分类页配置完全匹配  |
| `date`              | 精确到秒的发布时间            | 2023-10-26 14:30:00 +0800 |

## 常见问题处理
### 问题1：中文乱码
```powershell
# 强制使用UTF-8无BOM编码
[System.IO.File]::WriteAllText($path, $content, [System.Text.Encoding]::UTF8)
```

### 问题2：分类不显示
```powershell
# 检查分类标签格式
$categories = "[技术]"  # 正确
$categories = "技术"    # 错误
```

### 问题3：未来日期文章
```powershell
# 在_config.yml添加配置
$configContent = @"
future: false
"@
Add-Content -Path _config.yml -Value $configContent
```

> ​**提示**：建议配合Git进行版本控制，每次生成后执行：
> ```powershell
> git add _posts/$currentDate*
> git commit -m "新增技术文章：$currentDate"
> ```
