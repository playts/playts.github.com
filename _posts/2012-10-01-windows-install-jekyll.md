---
layout: post
title: windows 安装 jekyll
date: '2012-10-01'
---

一、下载 RubyInstaller 和 DEVELOPMENT KIT

下载页面： http://rubyinstaller.org/downloads/

下载链接：

http://rubyforge.org/frs/download.php/76054/rubyinstaller-1.9.3-p194.exe
https://github.com/downloads/oneclick/rubyinstaller/DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe

二、安装 ruby 到 C:\ruby

三、解压 DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe 到 C:\DevKit

四、打开命令提示符执行

    $ cd c:\devkit
    $ ruby dk.rb init
    $ ruby dk.rb install
    $ gem install jekyll

五、建立本地开发目录

    $ cd d:\dev
    $ md playts.github.com


建立jekyll基本文件

    $ md _layouts _posts _includes _site

建立文件 `_config.yml` 内容为空

    $ gvim _config.yml

建立文件 index.html ，内容如下：

{% raw %}
    ---
    layout: default
    title: Home
    ---
    <div class="page-front">
    <h1 class="title">Blog Posts</h1>

    {% for post in site.posts limit: 5 %}
      <div class="post">
        <h2 class="title"><a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h2>
        <time datetime="{{ post.date | xmlschema }}">{{ post.date | date:"%Y/%m/%d" }}</time>
        <div class="posts">{{ post.content }}</div>
      </div>
    {% endfor %}
    </div>
{% endraw %}

当然你也可以自行修改它

建立文件 `_layouts\default.html`

    $ gvim _layouts\default.html

内容如下：

{% raw %}
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="utf-8">
      <title>{{ page.title }}</title>
    </head>
    <body>
    {{ content }}
    </body>
    </html>
{% endraw %}

建立文件 `_layouts\post.html`

{% raw %}
    ---
    layout: default
    ---

    <div class="post">
      <div class="title">
        <h1>{{ page.title }}</h1>
        <time datetime="{{ page.date | xmlschema }}">{{ page.date | date: "%Y/%m/%d" }}</time>
      </div>
      <div class="content">
      {{ content }}
      </div>
    </div>
{% endraw %}

拟写一篇测试文章

    $ gvim _posts\2012-10-01-hello

添加内容：

    ---
    layout: post
    title: Hello
    date: '2012-10-01'
    ---

    Hello ! 

保存后，执行：

    $ jekyll --server

此时会在 `_site` 目录生成 html 文件

打开浏览器访问 127.0.0.1:4000

进一步了解请访问： https://github.com/mojombo/jekyll
