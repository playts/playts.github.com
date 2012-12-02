---
layout: post
title: 从Windows导出的Thunderbird通讯录到Ubuntu乱码的解决办法
date: '2012-12-02'
description:
categories:
---
当我将 Windows 7中Thunderbird通讯录导出为逗号分隔符文件(即csv格式文件)，然后在Ubuntu 中的Thunderbird执行导入，却发现是乱码，凭感觉是编码引起的，下面是我的解决方法：

1. 假定导出的文件名为：`my-address-book.csv`
2. 确定你的.vimrc文件中 设置了`set fencs=ucs-bom,utf-8,cp936`

接着在终端执行下面步骤：

	vim my-address-book.csv
	:set fenc=utf-8
	:wq

然后再执行通讯录的导入操作即可。

另一个方法是在终端下执行：

	iconv -f gb2312 -t utf8 my-address-book.csv > my-address-book-2.csv

然后选择 `my-address-book-2.csv`导入即可

