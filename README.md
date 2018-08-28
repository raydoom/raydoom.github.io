# Jekyll-theme-Manami

Manami 是一个简单、清爽的 Jekyll 主题。

## 项目信息

项目地址: [https://github.com/seanhuai/Jekyll-theme-Manami](https://github.com/seanhuai/Jekyll-theme-Manami)

项目文档: [https://seanhuai.github.io/2017/11/jekyll-theme-manami](https://seanhuai.github.io/2017/11/jekyll-theme-manami)

## 使用方法

```bash
  git clone https://github.com/seanhuai/Jekyll-theme-Manami
```

将本项目代码完全复制到本地，修改 `_data` 目录和 `_config.yml` 文件即可。

## 文章页设置

```yml
  layout: post # 布局，可选值：post/page
  title:  React 初步 # 文章名，如未声明，则按照路径自动生成
  date: 2017-11-06 20:02:06 # 时间，如未声明，则按照路径自动生成
  author: Sean Huai # 作者，如未声明，则按照默认作者显示
  tags: # 内容标签，便于查找
    - JavaScript
    - React
  categories: # 内容分类，便于今后扩展查询
    - JavaScript
  comments: true # 评论，可选值：true/false，若为 true，需要配套进行 disqus 设置
  feature: 'https://cdn.ruye.org.cn/blog/images/tumblr_odkypczpCM1utv5hpo7_1280.jpg'
  # 底图，如未声明，则按照默认底图显示
```

## 个性化设置

### 设置站点信息

修改 `_config.yml` 文件设置站点信息。

```yml
  name: # 站点名，显示在首页、页脚和文章选项卡
  description: # 站点副标题，显示在页首
  author: # 作者名，当文章没有声明作者时，采用此名
  permalink: # 永久链接，可用参数 `:year/:month/:day/:title`
  backgroundImage: # 默认页首底图，当文章没有声明背景图时，采用此图
  disqus: # 输入 disqus 用户名或 false，输入用户名时则加载 disqus 评论系统，否则不加载
```

### 设置链接

修改 `_data` 目录的 `link.yml` 文件设置链接。

```yml
  - name: # 显示链接名
    url:  # 链接地址，相对地址(相对首页)或绝对地址
```

### 设置主题色 

修改 `assets/scss` 目录的 `style.scss` 文件设置主题色。

```scss
  $theme-background-color: #51A8DD;
```

修改后请编译成 css 文件，并压缩为 `style.min.css` 放置在 `assets/css` 目录。

## 协议声明

此项目遵守 The MIT License

根据协议，你可以使用，复制和修改软件；可以用于个人项目或商业项目；使用此项目源码必须附带 MIT 协议声明。

使用此项目全部或部分内容，需要署名并保留原始项目链接。
