---
title: inception部署配置
description: 一个是集审核、执行、回滚于一体的一个自动化运维工具，它是根据MySQL代码修改过来的，用它可以很明确的，详细的，准确的审核MySQL的SQL语句
categories:
 - mysql
tags:
---

## 概述
> 一个集审核、执行、回滚于一体的一个自动化运维工具，它是根据MySQL代码修改过来的，用它可以很明确的，详细的，准确的审核MySQL的SQL语句

<!-- more -->

[Inception](https://github.com/mysql-inception/inception)是集审核、执行、回滚于一体的一个自动化运维工具，它是根据MySQL代码修改过来的，用它可以很明确的，详细的，准确的审核MySQL的SQL语句，
它的工作模式和MySQL完全相同，可以直接使用MySQL客户端来连接，但不需要验证权限，它相对应用程序（上层审核流程系统等）而言，是一个服务器，
在连接时需要指定服务器地址及Inception服务器的端口即可，而它相对要审核或执行的语句所对应的线上MySQL服务器来说，是一个客户端，
它在内部需要实时的连接数据库服务器来获取所需要的信息，或者直接在在线上执行相应的语句及获取binlog等，Inception就是一个中间性质的服务。


**Inception的架构如下**

![Inception的架构](https://raydoom.github.io/assets/images/post_images/mysql/Inception的架构.png)



## Installation

Check whether you have `Ruby 2.1.0` or higher installed:

```sh
ruby --version
```

Install `Bundler`:

```sh
gem install bundler
```

Clone Jacman theme:

```sh
git clone https://github.com/Simpleyyt/jekyll-theme-next.git
cd jekyll-theme-next
```

Install Jekyll and other dependencies from the GitHub Pages gem:

```sh
bundle install
```

Run your Jekyll site locally:

```sh
bundle exec jekyll server
```

More Details：[Setting up your GitHub Pages site locally with Jekyll](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)


## Features

### Multiple languages support, including: English / Russian / French / German / Simplified Chinese / Traditional Chinese.

Default language is English.

```yml
language: en
# language: zh-Hans
# language: fr-FR
# language: zh-hk
# language: zh-tw
# language: ru
# language: de
```

Set `language` field as following in site `_config.yml` to change to Chinese.

```yml
language: zh-Hans
```

### Comment support.

NexT has native support for `DuoShuo` and `Disqus` comment systems.

Add the following snippets to your `_config.yml`:

```yml
duoshuo:
  enable: true
  shortname: your-duoshuo-shortname
```

OR

```yml
disqus_shortname: your-disqus-shortname
```

### Social Media

NexT can automatically add links to your Social Media accounts:

```yml
social:
  GitHub: your-github-url
  Twitter: your-twitter-url
  Weibo: your-weibo-url
  DouBan: your-douban-url
  ZhiHu: your-zhihu-url
```

### Feed link.

> Show a feed link.

Set `rss` field in theme's `_config.yml`, as the following value:

1. `rss: false` will totally disable feed link.
2. `rss:  ` use sites' feed link. This is the default option.

    Follow the installation instruction in the plugin's README. After the configuration is done for this plugin, the feed link is ready too.

3. `rss: http://your-feed-url` set specific feed link.

### Up to 5 code highlight themes built-in.

NexT uses [Tomorrow Theme](https://github.com/chriskempson/tomorrow-theme) with 5 themes for you to choose from.
Next use `normal` by default. Have a preview about `normal` and `night`:

![Tomorrow Normal Preview](http://iissnan.com/nexus/next/tomorrow-normal.png)
![Tomorrow Night Preview](http://iissnan.com/nexus/next/tomorrow-night.png)

Head over to [Tomorrow Theme](https://github.com/chriskempson/tomorrow-theme) for more details.

## Configuration

NexT comes with few configurations.

```yml

# Menu configuration.
menu:
  home: /
  archives: /archives

# Favicon
favicon: /favicon.ico

# Avatar (put the image into next/source/images/)
# can be any image format supported by web browsers (JPEG,PNG,GIF,SVG,..)
avatar: /default_avatar.png

# Code highlight theme
# available: normal | night | night eighties | night blue | night bright
highlight_theme: normal

# Fancybox for image gallery
fancybox: true

# Specify the date when the site was setup
since: 2013

```

## Browser support

![Browser support](http://iissnan.com/nexus/next/browser-support.png)
