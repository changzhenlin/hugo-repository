---
title: "Mac系统安装ChromeDriver🌐"
date: 2023-01-05
author: Tyler
tags: ["code"]
categories:  ["Tips"]
---
# Mac系统安装ChromeDriver

## 介绍

该方法可以让您在Mac系统中安装和更新ChromeDriver，以便能够在本地运行Selenium WebDriver的测试，控制chrome调试。

## 下载ChromeDriver

首先，您需要在ChromeDriver的官方网站上下载适用于MacOS的正确版本。 ChromeDriver的官方网站提供了最新版本的ChromeDriver，并且您可以根据自己的需要下载适用于不同操作系统的正确版本。

## 将ChromeDriver添加到系统路径

下载完成之后，您需要将ChromeDriver添加到系统路径中，以便Selenium WebDriver能够找到它。要添加ChromeDriver到系统路径，请打开终端，然后输入以下命令：

```
export CHROMEDRIVER_PATH=/path/to/chromedriver

```

将上面的命令中的`/path/to/chromedriver`替换为您下载的ChromeDriver文件的路径。

### **也可以在finder目录下按command+shift+G输入/usr/local/bin，打开后将解压后的文件**

## 测试ChromeDriver

最后，您可以使用以下命令来测试安装是否成功：

```
chromedriver --version

```

如果安装成功，那么您将看到ChromeDriver的版本号。