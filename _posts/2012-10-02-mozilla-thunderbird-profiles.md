---
layout: post
title: Mozilla Thunderbird profiles 备份和恢复
date: 2012-10-02
---
## 什么是 Thunderbird profiles ##

Thunderbird profiles 存储着用户的Email帐户设置和邮件,包括该用户安装的扩展等等。

Thunderbird 安装后会自动创建一个名为“default”的配置文件，该配置文件会自动调用，除非我们使用配置管理器创建了新的配置文件。

## Thunderbird profiles 存放在那里？ ##

**Windows**

    %APPDATA%\Thunderbird\Profiles\xxxxxxxx.default\.

> **提示：**
>
> * `%AppData%` 在那里？你依次点“开始菜单"--"运行“ 输入`%AppData%` 确定后就会打开这个目录。例如：在win7中 `C:\Users\<username>\AppData\Roaming\`
> * `xxxxxxxx`是随机8位的数字或字母的组合

**Mac OS X**

    ~/Library/Thunderbird/Profiles/xxxxxxxx.default/.

**Linux**

    ~/.thunderbird/xxxxxxxx.default/.


你也可以点击 “帮助-->故障排除信息” 应用程序概要 点击“显示文件夹” 来打开您的配置目录。

## 备份和恢复 Thunderbird profiles ##

既然我们知道 Thunderbird profiles 存放的位置，备份和恢复就很简单了。

> 注意：在备份和恢复操作之前请退出 Thunderbird , `xxxxxxxx`是随机8位的数字或字母的组合

**备份：**

只需复制 `xxxxxxxx.default` 到 U 盘 或其他位置即可。

**恢复**

将之前备份的数据粘贴回来即可。

## 移动 Thunderbird profiles 到其他位置 ##

对于 windows 用户来讲，重装 windows 就意味着 系统分区被格式化，如果你没有及时的备份 Thunderbird profiles ，后果会很严重。

将 Thunderbird profiles 移动到其他位置是个不错办法

> 注意：操作之前请 退出 Thunderbird , `xxxxxxxx`是随机8位的数字或字母的组合

例如 我在win7 中把 Thunderbird profiles 移动到 `D:\backup\Thunderbird\Profiles\xxxxxxxx.default`

编辑 `%AppData%\Thunderbird\profiles.ini`

查找： `Path=Profiles/xxxxxxxx.default`

替换为： `Path=D:\backup\Thunderbird\Profiles\xxxxxxxx.default`

查找： `IsRelative=1`

替换为： `IsRelative=0`

把 `%AppData%\Thunderbird\Profiles\xxxxxxxx.default` 移动 `D:\backup\Thunderbird\Profiles\xxxxxxxx.default`

参考： https://support.mozillamessaging.com/en-US/kb/profiles
