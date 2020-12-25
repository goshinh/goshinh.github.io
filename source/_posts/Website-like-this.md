---
title: 从零开始，在互联网上，搭建一个自己的“家”
date: 2018-07-14 20:39:41
tags:
- hexo
- 站点配置
- 主题配置
- next
- github
---

房子让我们有了栖身之所，个人网站是我们的精神家园。互联网时代，每个人都应该有自己的网站，因为它价值连城！我写此文力图将个人网站的所涉及方方面面作专业的指导，希望对相关人士有所帮助。

我平时没有写博客的习惯，但是我对建站前沿技术比较关注。 建过很多网站，为找到适合自己的建站解决方案，反反复复折腾过很多次，坑也没少填过：

- 云服务器 + wordpress 太费钱

- github Pages 功能单一
- github Pages + Jekyll + theme  不能满足个性化需求
- github Pages + hexo + theme

之前建的网站，因不满意，全给下线了。最后剩下这个[IT达摩院](www.itdamo.org)，这个网站算是我心目中向往的博客类网站应有的样子。

<!-- more -->

## Github Pages+ Hexo + Next简介

俗话说的好“金窝银窝不如自家的狗窝”，虽然现在有很多可以写博客的平台，如[新浪](https://www.baidu.com/s?wd=%E6%96%B0%E6%B5%AA&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)、[网易](https://www.baidu.com/s?wd=%E7%BD%91%E6%98%93&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)、[搜狐](https://www.baidu.com/s?wd=%E6%90%9C%E7%8B%90&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)、百度、51com、天涯、[豆瓣](https://www.baidu.com/s?wd=%E8%B1%86%E7%93%A3&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)、[开心网](https://www.baidu.com/s?wd=%E5%BC%80%E5%BF%83%E7%BD%91&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)、[人人网](https://www.baidu.com/s?wd=%E4%BA%BA%E4%BA%BA%E7%BD%91&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)、凤凰网、21频道等，但是个人感觉都不够个性化，不能高度自定义！

因此，喜欢上了Github Pages+hexo+next（以下简称GHN）建站方案。

- [Github](www.github.com) 是全球知名的代码托管平台，这对持续开发的网站非常有用，而且可以免费使用。
- [Hexo](hexo.io)一个快速、简洁且高效的博客框架，生成网页速度快，支持Markdown，拥有丰富的插件，还可以一键部署到Github等其他网站。
- [NexT](http://theme-next.iissnan.com/) 一个主题有三种风格(Sckeme)任你选，同时支持10种语言。除了常见的 [主题设定](http://theme-next.iissnan.com/theme-settings.html) 与 [第三方服务集成](http://theme-next.iissnan.com/third-party-services.html) 以外， NexT 也提供了一些进阶的设定，让 NexT 更具定制性。

## 利用Github Pages+Hexo+NexT搭建博客网站

GHN是目前我所知道的非常适合个人建博客网站的选择方案。那么，GHN方案如何实施部署？我结合自己的亲身体验和网友的分享，做以下总结：

### Github Pages侧

Github在本方案中主要用于托管网站源代码和担任服务器的角色。

#### Github Pages 是什么

GitHub Pages 是通过我们网站托管和发布的公开网页。

你可以通过 [Automatic Page Generator](https://help.github.com/articles/creating-pages-with-the-automatic-generator) 在线创建和发布 GitHub Pages。如果你更喜欢本地操作，你可以使用 [Mac](http://mac.github.com/) 或者 [Windows](http://windows.github.com/) 平台的 GitHub App，或者使用 [命令行](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line)。

*警告：GitHub Pages 网站是在互联网上**公开**的，即使它们所在的库是私有的。如果你有敏感的数据在 Pages 库，你应该在发布之前删除它。*

想要获取更多信息，可以查看 [Github Pages](http://pages.github.com/) 网页，或者这里的 [相关帮助文档](https://help.github.com/categories/github-pages-basics/)。

#### 三种类型的Pages

这里有两种基本的 GitHub Pages 类型：*用户/组织 Pages 和项目 Pages。*它们极其相似，但是有一些很重要的差别。

##### 用户/组织 Pages

**用户/组织 Pages** 存在于一个特定的 GitHub Pages 文件专有库中。你将使用用户名来命名这个库，比如 [atmos/atmos.github.io](https://github.com/atmos/atmos.github.io)。

- 你必须使用`username.github.io`这样的命名体制。
- `master`分支上的内容将用于构建和发布你的 GitHub Pages 网页。

你只可以使用你自己的用户名创建用户或者组织 Pages 的库。像`joe/bob.github.io`这样的命名将不能构建用户 Pages 网站。

当用户 Pages 构建完之后，打开`http(s)://<username>.github.io`就可以正常使用了。

##### 项目 Pages

不像用户和组织的 Pages，**项目 Pages** 是作为一个项目保存在同一个库中。个人账户和组织都可以创建项目 Pages。个人账户的项目 Pages 的 URL将会是这样 `http(s)://<username>.github.io/<projectname>`，但组织的 URL 是`http(s)://<orgname>.github.io/<projectname>`。创建项目 Pages 的步骤两者都是相同的。 

项目 Pages 与用户和组织 Pages 很相似，但有一些轻微的不同：

- `gh-pages`分支用来构建和发布项目 Pages 网站。
- 如果没有 [自定义的域名](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages)，项目 Pages 网站将服务在用户 Pages 网站的子域名下：`username.github.io/projectname`。
- 用户和组织 Pages 网站的 [自定义域名](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages) 适用于这个账户托管的所有重定向项目 Pages 的相同域名。使用自定义域名的项目 Pages 网站同样在个人账户的`username.github.io/projectname`和组织的`orgname.github.io/projectname`中有效。
- [自定义的 404s](https://help.github.com/articles/custom-404-pages) 只用在使用了自定义域名的网站。否则，将使用用户 Pages 404。

#### 构建自己的Pages

**用户 Pages** 的构建可以通过任何经过认证邮件的账户。它也可以使用 [部署 keys](https://developer.github.com/guides/managing-deploy-keys/#deploy-keys) 来自动化这个过程。

**组织 Pages** 的构建可以通过任何有 push 权限的成员和有认证邮件的用户。想要自动构建，你可以 [设置一个机器用户](https://developer.github.com/guides/managing-deploy-keys/#machine-users) 作为你的组织的成员。组织 Pages 不支持部署 keys。

##### 途径一：手动创建

如果你是熟悉 Git 的命令行的，手动创建项目 Pages 网站是非常直观易懂的。

- **做一个新的 clone**

为了建立一个项目 Pages，你需要在你的库中新建一个新的 `orphan` 分支（一个与现存分支没有共同的历史的分支）。最安全的做法是从一个新的 clone 开始来做这件事：

```
$ git clone github.com/user/repository.git
# Clone our repository
Cloning into 'repository'...
remote: Counting objects: 2791, done.
remote: Compressing objects: 100% (1225/1225), done.
remote: Total 2791 (delta 1722), reused 2513 (delta 1493)
Receiving objects: 100% (2791/2791), 3.77 MiB | 969 KiB/s, done.
Resolving deltas: 100% (1722/1722), done.
```

- **新建一个 gh-pages 分支**

一旦你拥有一个空的库，你将需要创建一个新的 `gh-pages` 分支且从工作目录和首页中去除所有的内容：

```
$ cd repository
$ git checkout --orphan gh-pages
Creates our branch, without any parents (it's an orphan!)
Switched to a new branch 'gh-pages'
$ git rm -rf .
Remove all files from the old working tree
rm '.gitignore'
```

提示：直到你第一次提交之前，`gh-pages` 分支不会出现在 `git branch` 生成的分支列表中。

- **添加内容和 push**

当你 push 你的程序到页面库中，为了触发它构建，你必须首先[验证你的邮箱地址](https://help.github.com/articles/verifying-your-email-address)。

现在你有一个空的工作目录。你可以在这个分支中创建一些内容和 push 它到 GitHub。例如：

```
$ echo "My Page" > index.html
$ git add index.html
$ git commit -a -m "First pages commit"
$ git push origin gh-pages
```

你的 GitHub Pages 应该是可用了。如果你建立的代码不成功，你将会收到一封邮件。

- **加载你的新 GitHub 网页**

在你推送 `gh-pages` 分支后，你的项目 Pages 在`http(s)://<username>.github.io/<projectname>` 上是可用的。记住，这个 Pages 总是公开课进入的，当它发布之后，尽管它的库是私有的。

关于如何给 GitHub Pages 建立一个自定义的域名，可以看看[给 GitHub 网页建立一个自定义的域名](http://wiki.jikexueyuan.com/project/github-pages-basics/set-custom-domains.html)。

##### 途径二：自动生成

你可以使用 GitHub Pages 自动生成器快速的建立一个项目的网页、用户或组织的网页。

- **用户和组织 Pages**

为了生成用户和组织的网页，你需要[生成一个库](https://help.github.com/articles/creating-a-new-repository)叫作`username.github.io`。用户名和组织名**必须**是你自己的否则你的 GitHub Pages 不会建立的。页面自动生成器是容易通过库的设置页面进入的。你可以[从这里](https://help.github.com/articles/user-organization-and-project-pages)阅读更多关于用户和组织页面。

警告： GitHub Pages 在互联网上是公开的可进入的，尽管它们的库是私有的。如果你有一些敏感的数据在你的页面库中，你可能想把它在发布前去除。

- **项目 Pages**

你可以用页面自动生成器给任何项目库去发布 GitHub Pages。

警告：你必须新建一个符合命名规则描述的库，否则你将不能把它发布到你的 GitHub Pages。

- **页面自动生成器**

1. 在 GitHub 上打开库的页面。
2. 在你的库右面的侧边栏，点击![img](http://wiki.jikexueyuan.com/project/github-pages-basics/images/automatic-generator1.png)。
3. 点击 **Automatic Page Generator** 按钮。
4. 编辑的的内容在 Markdown 编辑器。
5. 点击 **Continue To Layouts** 按钮。
6. 在主题中预览你的内容。
7. 当你找到你喜欢的主题，点击 **Publish page**。

在你的 GitHub Pages 生成之后，你可以得到它 HTML 代码的本地复制。如果你生成一个项目网页，fetch 和 check out 一个新的分支。

```
$ cd repository
$ git fetch origin
remote: Counting objects: 92, done.
remote: Compressing objects: 100% (63/63), done.
remote: Total 68 (delta 41), reused 0 (delta 0)
Unpacking objects: 100% (68/68), done.
From https://github.com/user/repo.git
* [new branch]      gh-pages     -> origin/gh-pages
$git checkout gh-pages
Branch gh-pages set up to track remote branch gh-pages from origin.
Switched to a new branch 'gh-pages'
```

如果你生成了一个用户网页，代码会在 `master` 的分支，而不是 `gh-pages` 的分支，所以仅仅 check out `master`然后 pull 就可以了。

```
$cd repository
$git checkout master
Switched to branch 'master'
git pull origin master
remote: Counting objects: 92, done.
remote: Compressing objects: 100% (63/63), done.
remote: Total 68 (delta 41), reused 0 (delta 0)
Receiving objects: 100% (424/424), 329.32 KiB | 178 KiB/s, done.
Resolving deltas: 100% (68/68), done.
From https://github.com/user/repo.git
 * branch      master     -> FETCH_HEAD
Updating abc1234..def5678
Fast-forward
index.html                                     |  265 ++++
...
98 files changed, 18123 insertions(+), 1 deletion(-)
create mode 100644 index.html
...
```

#### 关于 GitHub Pages 的自定义域名

有两种自定义域名可用于重定向 GitHub Pages：子域名和顶端域名（apex domains）。

##### 子域名

一个子域名[通过您的 DNS 提供商来配置 `CNAME` 记录](https://help.github.com/articles/tips-for-configuring-a-cname-record-with-your-dns-provider)。

我们因为以下这些原因强烈建议您使用自定义子域名：

- 它把我们[内容分发网络](http://en.wikipedia.org/wiki/Content_delivery_network)的好处带给你的 GitHub Pages。
- 它不会受到 GitHub 服务底层 IP 地址变化影响。
- Pages 将加载得更加快，因为[拒绝服务](http://en.wikipedia.org/wiki/Denial-of-service_attack)保护可以更有效地实施。

##### 顶端域名

一个顶端域名[通过你的 DNS 供应商配置一个 `A`、`ALLAS` 或者 `ANAME`](https://help.github.com/articles/tips-for-configuring-an-a-record-with-your-dns-provider)，和经常被分配给一个或更多的 IP 地址。

注意：一些 DNS 供应商支持配置顶端域名的 ALIAS 或者 ANAME 记录，但是没有专门的工业标准。一些 DNS 供应商（像 [DNSimple](https://dnsimple.com/) ）允许顶端域名配置 ALIAS 或者 ANAME 指向其它域。

对于你的 GitHub Pages，我们推荐使用一个自定义的子域名，而不是一个顶端域名。

#### GitHub Pages 怎样使用自定义域名

| GitHub Pages 种类            | GitHub 的主机位置                | 页面是怎么重定向的                                           | 自定义域名例子        |
| ---------------------------- | -------------------------------- | ------------------------------------------------------------ | --------------------- |
| 用户 Pages                   | `username.github.io`             | 自动重定向至已经设定好的自定义域名                           | `user.example.com`    |
| 组织 Pages                   | `orgname.github.io`              | 自动重定向至已经设定好的自定义域名                           | `org.example.com`     |
| **用户账号**拥有的项目 Pages | `username.github.io/projectname` | 自动重定向到一个由用户指定的，用户网站自定义域名的子目录（` user.example.com/projectname`），以及所有自定义域名 | `project.example.com` |
| **组织**拥有的项目 Pages     | `orgname.github.io/projectname`  | 自动重定向到一个由组织指定的，项目 Pages 自定义域名的子目录(`org.example.com/projectname`)，以及所有自定义域名 | `project.example.com` |

解决自定义域的问题，可以参考[“我的自定义域出现问题了。”](https://help.github.com/articles/my-custom-domain-isn-t-working)。

#### 设置 GitHub Pages 的自定义域名

你可以为用户、组织和项目 Pages 配置一个自定义域名。

获取在不同类型的自定义域名信息，可以参看关于 GitHub 网站的自定义域。

##### *CNAME* 文件的创建

为了重定向你的 GitHub Pages，可以有两种方式创建**CNAME**文件。这个文件包含你的库根目录的自定义域名。

一种就是手动创建并上传至库的根目录，另一种就是在项目的Setting 中设置自定义域名，设置成功后，GithubPages自动在库的根目录创建CNAME文件。更多资讯，请参看为你的库添加一个 CNAME 文件。

##### 通过你的 DNS 提供商配置自定义子域名

如果你的自定义域名是一个[子域名](http://wiki.jikexueyuan.com/project/github-pages-basics/custom-domains.html)，你必须通过你的 DNS 提供商配置 CNAME 记录。欲了解更多信息，请参见[通过你的 DNS 提供商配置 `CNAME` 记录的技巧](http://wiki.jikexueyuan.com/project/github-pages-basics/tip-cname.html)。

##### **通过你的 DNS 提供商配置自定义顶端域名**

如果你的自定义域名是一个[顶端域名](http://wiki.jikexueyuan.com/project/github-pages-basics/custom-domains.html)，你必须配置 `ALIAS` 、`ANAME` 或通过 DNA 提供商配置 `A` 记录，欲了解更多信息，请参见[通过你的DNS提供商配置 `A` 记录的技巧](http://wiki.jikexueyuan.com/project/github-pages-basics/tip-record.html)。

### Hexo配置

Hexo主要负责解析各种文档（大部分场合即是你的博文），部署网站。
Hexo版本：3.7.1
Node版本：10.6.0
#### 官方说明文档

https://hexo.io/docs/configuration.html

#### 项目开源代码

https://github.com/hexojs/hexo/

打开根目录下的_config.yml文件，开始对Hexo配置：
#### 基本信息 
``` yaml
# Site
title: # 站点名
subtitle: # 站点详细描述，一般在这里写你的站点是干什么的
description: # 对作者的描述
author: # 作者署名
language: zh-CN # 这里NexT用zh-Hans会显示他国语言
timezone: # 时区
```
#### URL

``` yaml
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: # 站点的URL
root: / # 站点根目录位置
permalink: :year/:month/:day/:title/ / # 文章url命名格式
permalink_defaults:
```
#### 目录
``` yaml
# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render: # 不渲染source/aaa/bbb文件，可使用通配符*
```
#### 写作
```yaml
# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: true #文章资源文件夹，如果打开，你在用Hexo new创建新一篇新文章时，Hexo会自动创建一个与之文件名相同的文件夹，用于存放与文章相关的资源。
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: false
  tab_replace:
```
#### 首页
```yaml
# Home page setting
# path: Root path for your blogs index page. (default = '')
# per_page: Posts displayed per page. (0 = disable pagination)
# order_by: Posts order. (Order by date descending by default)
index_generator:
  path: ''
  per_page: 10 # 每页显示的文章数
  order_by: -date # 文章排列依据，`-`代表降序
```
#### 分类和标签
```yaml
# Category & Tag
default_category: uncategorized
category_map:
tag_map:
```
#### 日期与时间
```yaml
# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss
```
#### 翻页
```yaml
# Pagination
## Set per_page to 0 to disable pagination
per_page: 10
pagination_dir: page
```
#### 扩展应用

扩展应用包括插件和主题。

```yaml
# Extensions
## Plugins: https://hexo.io/plugins/ 插件资源
## Themes: https://hexo.io/themes/ 主题资源
theme: next # 改变主题
## sitemap 站点地图
#plugins:
#- hexo-generator-sitemap

# Deployment 部署
## Docs: https://hexo.io/docs/deployment.html
deploy:
- type: # 类型，如git
  repo: # 仓库地址
  branch: # 分支
  message: 
# other deployer
- type: leancloud_counter_security_sync

leancloud_counter_security:
  enable_sync: true
  app_id: 
  app_key: 
  username: 
  password: ******* # 不建议将用户名和密码写在配置文件中
```

### NexT主题配置

NexT负责网页中各种元素的组织形式和内容的外观样式。欲了解更多信息，请参见[NexT官方说明文档](http://theme-next.iissnan.com/getting-started.html)。

Next版本：6.3.0

打开next/_config.yml文件，开始对主题配置：

#### 主题核心配置设置
一般不需要动它，默认即可。

```yaml
# ---------------------------------------------------------------
# Theme Core Configuration Settings
# ---------------------------------------------------------------

# If false, merge configs from `_data/next.yml` into default configuration (rewrite).
# If true, will fully override default configuration by options from `_data/next.yml` (override). Only for NexT settings.
# And if true, all config from default NexT `_config.yml` must be copied into `next.yml`. Use if you know what you are doing.
# Useful if you want to comment some options from NexT `_config.yml` by `next.yml` without editing default config.
override: false

# Allow to cache content generation. Introduced in NexT v6.0.0.
cache:
  enable: true

# Redefine custom file paths. Introduced in NexT v6.0.2.
# If commented, will be used default custom file paths.

# For example, you want to put your custom styles file
# outside theme directory in root `source/_data`, set
# `styles: source/_data/styles.styl`
#custom_file_path:
  # Default paths: layout/_custom/*
  #head: source/_data/head.swig
  #header: source/_data/header.swig
  #sidebar: source/_data/sidebar.swig

  # Default path: source/css/_variables/custom.styl
  #variables: source/_data/variables.styl
  # Default path: source/css/_mixins/custom.styl
  #mixins: source/_data/mixins.styl
  # Default path: source/css/_custom/custom.styl
  #styles: source/_data/styles.styl
```
#### 站点信息设置
##### 网站图标
``` yaml
# ---------------------------------------------------------------
# Site Information Settings
# ---------------------------------------------------------------

# To get or check favicons visit: https://realfavicongenerator.net
# Put your favicons into `hexo-site/source/` (recommend) or `hexo-site/themes/next2/source/images/` directory.

# Default NexT favicons placed in `hexo-site/themes/next2/source/images/` directory.
# And if you want to place your icons in `hexo-site/source/` root directory, you must remove `/images` prefix from pathes.

# For example, you put your favicons into `hexo-site/source/images` directory.
# Then need to rename & redefine they on any other names, otherwise icons from Next will rewrite your custom icons in Hexo.
favicon:
  small: /images/favicon-16x16-next.png
  medium: /images/favicon-32x32-next.png
  apple_touch_icon: /images/apple-touch-icon-next.png
  safari_pinned_tab: /images/logo.svg
  #android_manifest: /images/manifest.json
  #ms_browserconfig: /images/browserconfig.xml
```
##### RSS
``` yaml
# Set rss to false to disable feed link.
# Leave rss as empty to use site's feed link, and install hexo-generator-feed: `npm install hexo-generator-feed --save`.
# Set rss to specific value if you have burned your feed already.
rss: /atom.xml
```
##### 页脚
``` yaml
footer: # 页脚
  # Specify the date when the site was setup.
  # If not defined, current year will be used.
  since: 2015

  # Icon between year and copyright info.
  icon: # 图标
    # Icon name in fontawesome, see: https://fontawesome.com/v4.7.0/icons
    # `heart` is recommended with animation in red (#ff0000).
    name: heart #user
    # If you want to animate the icon, set it to true.
    animated: true
    # Change the color of icon, using Hex Code.
    color: "#ff0000" #"#808080"

  # If not defined, will be used `author` from Hexo main config.
  copyright: # 版权
  # -------------------------------------------------------------
  powered:
    # Hexo link (Powered by Hexo).
    enable: true
    # Version info of Hexo after Hexo link (vX.X.X).
    version: true

  theme:
    # Theme & scheme info link (Theme - NexT.scheme).
    enable: true
    # Version info of NexT after scheme info (vX.X.X).
    version: true
  # -------------------------------------------------------------
  # Any custom text can be defined here.
  custom_text: Hosted by <a target="_blank" rel="external nofollow" href="https://github.com"><b>GitHub</b></a>
```
#####  设置SEO
``` yaml
# ---------------------------------------------------------------
# SEO Settings
# ---------------------------------------------------------------

# Canonical, set a canonical link tag in your hexo, you could use it for your SEO of blog.
# See: https://support.google.com/webmasters/answer/139066
# Tips: Before you open this tag, remember set up your URL in hexo _config.yml ( ex. url: http://yourdomain.com )
canonical: true

# Change headers hierarchy on site-subtitle (will be main site description) and on all post/pages titles for better SEO-optimization.
seo: false

# If true, will add site-subtitle to index page, added in main hexo config.
# subtitle: Subtitle
index_with_subtitle: false
```
#### 菜单设置
``` yaml
# ---------------------------------------------------------------
# Menu Settings
# ---------------------------------------------------------------

# When running the site in a subdirectory (e.g. domain.tld/blog), remove the leading slash from link value (/archives -> archives).
# Usage: `Key: /link/ || icon`
# Key is the name of menu item. If translate for this menu will find in languages - this translate will be loaded; if not - Key name will be used. Key is case-senstive.
# Value before `||` delimeter is the target link.
# Value after `||` delimeter is the name of FontAwesome icon. If icon (with or without delimeter) is not specified, question icon will be loaded.
menu:
  home: / || home
  about: /about/ || user
  tags: /tags/ || tags
  categories: /categories/ || th
  archives: /archives/ || archive
  #schedule: /schedule/ || calendar
  sitemap: /sitemap.xml || sitemap
  #commonweal: /404/ || heartbeat

# Enable/Disable menu icons / item badges.
menu_settings:
  icons: true
  badges: true
```
#### 主题风格设置
``` yaml
# ---------------------------------------------------------------
# Scheme Settings
# ---------------------------------------------------------------

# Schemes 风格
#scheme: Muse
#scheme: Mist
#scheme: Pisces
scheme: Gemini
```
#### 侧边栏设置
``` yaml
# ---------------------------------------------------------------
# Sidebar Settings
# ---------------------------------------------------------------

# Posts / Categories / Tags in sidebar.
site_state: true

# Social Links. 社交链接
# Usage: `Key: permalink || icon`
# Key is the link label showing to end users.
# Value before `||` delimeter is the target permalink.
# Value after `||` delimeter is the name of FontAwesome icon. If icon (with or without delimeter) is not specified, globe icon will be loaded.
social:
  GitHub: https://github.com/goshinh || github
  E-Mail: mailto:jiller@126.com || envelope
  #Google: https://plus.google.com/yourname || google
  #Twitter: https://twitter.com/yourname || twitter
  #FB Page: https://www.facebook.com/yourname || facebook
  #VK Group: https://vk.com/yourname || vk
  #StackOverflow: https://stackoverflow.com/yourname || stack-overflow
  #YouTube: https://youtube.com/yourname || youtube
  #Instagram: https://instagram.com/yourname || instagram
  #Skype: skype:yourname?call|chat || skype

social_icons:
  enable: true
  icons_only: false
  transition: false
  # Dependencies: exturl: true in Tags Settings section below.
  # To encrypt links above use https://www.base64encode.org
  # Example encoded link: `GitHub: aHR0cHM6Ly9naXRodWIuY29tL3RoZW1lLW5leHQ= || github`
  exturl: false

# Follow me on GitHub banner in right-top corner.
# Usage: `permalink || title`
# Value before `||` delimeter is the target permalink.
# Value after `||` delimeter is the title and aria-label name.
#github_banner: https://github.com/yourname || Follow me on GitHub

# Blog rolls
links_icon: link
links_title: 友情链接
links_layout: block
#links_layout: inline
links:
  百度: http://baidu.com/

# Sidebar Avatar
avatar:
  # in theme directory(source/images): /images/avatar.gif
  # in site  directory(source/uploads): /uploads/avatar.gif
  # You can also use other linking images.
  url: /images/avatar.jpeg
  # If true, the avatar would be dispalyed in circle.
  rounded: true
  # The value of opacity should be choose from 0 to 1 to set the opacity of the avatar.
  opacity: 1
  # If true, the avatar would be rotated with the cursor.
  rotated: true

# Table Of Contents in the Sidebar
toc:
  enable: true

  # Automatically add list number to toc.
  number: true

  # If true, all words will placed on next lines if header width longer then sidebar width.
  wrap: false

# Creative Commons 4.0 International License.
# http://creativecommons.org/
# Available: by | by-nc | by-nc-nd | by-nc-sa | by-nd | by-sa | zero
#creative_commons: by-nc-sa
#creative_commons:

sidebar:
  # Sidebar Position, available value: left | right (only for Pisces | Gemini).
  position: left
  #position: right

  # Manual define the sidebar width.
  # If commented, will be default for:
  # Muse | Mist: 320
  # Pisces | Gemini: 240
  #width: 300

  # Sidebar Display, available value (only for Muse | Mist):
  #  - post    expand on posts automatically. Default.
  #  - always  expand for all pages automatically
  #  - hide    expand only when click on the sidebar toggle icon.
  #  - remove  Totally remove sidebar including sidebar toggle.
  display: post
  #display: always
  #display: hide
  #display: remove

  # Sidebar offset from top menubar in pixels (only for Pisces | Gemini).
  offset: 12

  # Back to top in sidebar (only for Pisces | Gemini).
  b2t: false

  # Scroll percent label in b2t button.
  scrollpercent: false

  # Enable sidebar on narrow view (only for Muse | Mist).
  onmobile: false
```
#### 文章设置
``` yaml
# ---------------------------------------------------------------
# Post Settings
# ---------------------------------------------------------------

# Automatically scroll page to section which is under <!-- more --> mark.
scroll_to_more: true

# Automatically saving scroll position on each post/page in cookies.
#保存阅读位置
save_scroll: true

# Automatically excerpt description in homepage as preamble text.
excerpt_description: true

# Automatically Excerpt. Not recommend.
# Please use <!-- more --> in the post to control excerpt accurately.
auto_excerpt:
  enable: false
  length: 150

# Post meta display settings
post_meta:
  item_text: true
  created_at: true
  updated_at:
    enabled: true
    # If true, show updated date label only if `updated date` different from 'created date' (post edited in another day than was created).
    # And if post will edited in same day as created, edited time will show in popup title under created time label.
    # If false show anyway, but if post edited in same day, show only edited time.
    another_day: true
  categories: true

# Post wordcount display settings
# Dependencies: https://github.com/theme-next/hexo-symbols-count-time
symbols_count_time:
  separated_meta: true
  item_text_post: true
  item_text_total: false
  awl: 4
  wpm: 275

# 复制代码功能
codeblock:
  # Manual define the border radius in codeblock
  # Leave it empty for the default 1
  border_radius:
  # Add copy button on codeblock
  copy_button:
    enable: true
    # Show text copy result
    show_result: true

# Wechat Subscriber 二维码订阅
wechat_subscriber:
  enabled: true
  qcode: /uploads/wechat-qcode.jpg
  description: 欢迎您扫一扫上面的微信公众号，订阅我的博客！

# Reward
reward_comment: 坚持原创技术分享，您的支持将鼓励我继续创作！
wechatpay: /images/wechatpay.jpg
alipay: /images/alipay.jpg
#bitcoin: /images/bitcoin.png

# Related popular posts
# Dependencies: https://github.com/tea3/hexo-related-popular-posts
related_posts:
  enable: true
  title: # custom header, leave empty to use the default one
  display_in_home: false
  params:
    maxCount: 5
    #PPMixingRate: 0.0
    #isDate: false
    #isImage: false
    #isExcerpt: false

# Declare license on posts 版权说明
post_copyright:
  enable: true
  license: <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/" rel="external nofollow" target="_blank">CC BY-NC-SA 4.0</a>

# Post edit
# Dependencies: https://github.com/hexojs/hexo-deployer-git
post_edit:
  enable: false
  url: https://github.com/theme-next/theme-next.org/_posts/tree/master/ # Link for view source.
# url: https://github.com/theme-next/theme-next.org/_posts/edit/master/ # Link for fork & edit.
```
#### Misc主题设置
如果你不用Misc主题，可以跳过此节。
``` yaml
# ---------------------------------------------------------------
# Misc Theme Settings
# ---------------------------------------------------------------

# Reduce padding / margin indents on devices with narrow width.
mobile_layout_economy: false

# Android Chrome header panel color ($brand-bg / $headband-bg => $black-deep).
android_chrome_color: "#222"

# Custom Logo.
# !!Only available for Default Scheme currently.
# Options:
#   enabled: [true/false] - Replace with specific image
#   image: url-of-image   - Images's url
custom_logo:
  enabled: false
  image:

# Code Highlight theme 代码高亮风格
# Available values: normal | night | night eighties | night blue | night bright
# https://github.com/chriskempson/tomorrow-theme
highlight_theme: normal

# Enable "cheers" for archive page.
cheers_enabled: true
```
#### 字体设置
可以跳过，选择默认即可。
``` yaml
# ---------------------------------------------------------------
# Font Settings
# - Find fonts on Google Fonts (https://www.google.com/fonts)
# - All fonts set here will have the following styles:
#     light, light italic, normal, normal italic, bold, bold italic
# - Be aware that setting too much fonts will cause site running slowly
# - Introduce in 5.0.1
# ---------------------------------------------------------------
# CAUTION! Safari Version 10.1.2 bug: https://github.com/iissnan/hexo-theme-next/issues/1844
# To avoid space between header and sidebar in Pisces / Gemini themes recommended to use Web Safe fonts for `global` (and `logo`):
# Arial | Tahoma | Helvetica | Times New Roman | Courier New | Verdana | Georgia | Palatino | Garamond | Comic Sans MS | Trebuchet MS
# ---------------------------------------------------------------
font:
  enable: false

  # Uri of fonts host. E.g. //fonts.googleapis.com (Default).
  host:

  # Font options:
  # `external: true` will load this font family from `host` above.
  # `family: Times New Roman`. Without any quotes.
  # `size: xx`. Use `px` as unit.

  # Global font settings used for all elements in <body>.
  global:
    external: true
    family: Lato
    size:

  # Font settings for Headlines (H1, H2, H3, H4, H5, H6).
  # Fallback to `global` font settings.
  headings:
    external: true
    family:
    size:

  # Font settings for posts.
  # Fallback to `global` font settings.
  posts:
    external: true
    family:

  # Font settings for Logo.
  # Fallback to `global` font settings.
  logo:
    external: true
    family:
    size:

  # Font settings for <code> and code blocks.
  codes:
    external: true
    family:
    size:
```
#### 第三方服务设置
##### 数学公式
``` yaml
# Math Equations Render Support
math:
  enable: true

  # Default(true) will load mathjax/katex script on demand
  # That is it only render those page who has 'mathjax: true' in Front Matter.
  # If you set it to false, it will load mathjax/katex srcipt EVERY PAGE.
  per_page: true

  engine: mathjax
  #engine: katex

  # hexo-rendering-pandoc (or hexo-renderer-kramed) needed to full MathJax support.
  mathjax:
    # Use 2.7.1 as default, jsdelivr as default CDN, works everywhere even in China
    cdn: //cdn.jsdelivr.net/npm/mathjax@2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML
    # For newMathJax CDN (cdnjs.cloudflare.com) with fallback to oldMathJax (cdn.mathjax.org).
    #cdn: //cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML
    # For direct link to MathJax.js with CloudFlare CDN (cdnjs.cloudflare.com).
    #cdn: //cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML
    # For automatic detect latest version link to MathJax.js and get from Bootcss.
    #cdn: //cdn.bootcss.com/mathjax/2.7.1/latest.js?config=TeX-AMS-MML_HTMLorMML
  # hexo-renderer-markdown-it-plus (or hexo-renderer-markdown-it with markdown-it-katex plugin)
  # needed to full Katex support.
  katex:
    # Use 0.7.1 as default, jsdelivr as default CDN, works everywhere even in China
    cdn: //cdn.jsdelivr.net/npm/katex@0.7.1/dist/katex.min.css
    # CDNJS, provided by cloudflare, maybe the best CDN, but not works in China
    #cdn: //cdnjs.cloudflare.com/ajax/libs/KaTeX/0.7.1/katex.min.css
    # Bootcss, works great in China, but not so well in other region
    #cdn: //cdn.bootcss.com/KaTeX/0.7.1/katex.min.css
```
##### 汉字支持

``` ymal
# Han Support
# Dependencies: https://github.com/theme-next/theme-next-han
han: true
```
##### Pangu支持

``` ymal
# Pangu Support
# Dependencies: https://github.com/theme-next/theme-next-pangu
# For more information: https://github.com/vinta/pangu.js
pangu: true
```
##### Leancloud 的极简风评论系统
``` ymal
# Valine.一款基于 Leancloud 的极简风评论系统
# You can get your appid and appkey from https://leancloud.cn
# more info please open https://valine.js.org
valine:
  enable: true
  appid:  kS************************sz # your leancloud application appid
  appkey: 757******************orG # your leancloud application appkey
  notify: true # mail notifier , https://github.com/xCss/Valine/wiki
  verify: true # Verification code
  placeholder: 我来说两句... # comment box placeholder
  avatar: mm # gravatar style
  guest_info: nick,mail,link # custom comment header
  pageSize: 10 # pagination size

```
##### NeedMoreShare2 分享系统
``` ymal
# NeedMoreShare2 分享系统
# Dependencies: https://github.com/theme-next/theme-next-needmoreshare2
# See: https://github.com/revir/need-more-share2
# Also see: https://github.com/DzmVasileusky/needShareButton
# iconStyle: default | box
# boxForm: horizontal | vertical
# position: top / middle / bottom + Left / Center / Right
# networks: Weibo,Wechat,Douban,QQZone,Twitter,Linkedin,Mailto,Reddit,
#           Delicious,StumbleUpon,Pinterest,Facebook,GooglePlus,Slashdot,
#           Technorati,Posterous,Tumblr,GoogleBookmarks,Newsvine,
#           Evernote,Friendfeed,Vkontakte,Odnoklassniki,Mailru
needmoreshare2:
  enable: true
  postbottom:
    enable: true
    options:
      iconStyle: box
      boxForm: horizontal
      position: bottomCenter
      networks: Weibo,Wechat,Douban,QQZone,Evernote,Twitter,Facebook
  float:
    enable: true
    options:
      iconStyle: box
      boxForm: horizontal
      position: middleRight
      networks: Weibo,Wechat,Douban,QQZone,Evernote,Twitter,Facebook
```

##### 文章访问量统计
``` ymal
# Show number of visitors to each article.
# You can visit https://leancloud.cn get AppID and AppKey.
leancloud_visitors:
  enable: true
  app_id: kSad***************************oHsz #<app_id>
  app_key: 75***************7orG #<app_key>
  # Dependencies: https://github.com/theme-next/hexo-leancloud-counter-security
  # If you don't care about security in lc counter and just want to use it directly
  # (without hexo-leancloud-counter-security plugin), set the `security` to `false`.
  security: true
  betterPerformance: true

# Another tool to show number of visitors to each article.
# visit https://console.firebase.google.com/u/0/ to get apiKey and projectId
# visit https://firebase.google.com/docs/firestore/ to get more information about firestore
firestore:
  enable: false
  collection: articles #required, a string collection name to access firestore database
  apiKey: #required
  projectId: #required
  bluebird: false #enable this if you want to include bluebird 3.5.1(core version) Promise polyfill
```
##### 访客统计
``` ymal
# 访客统计
# Show Views/Visitors of the website/page with busuanzi.
# Get more information on http://ibruce.info/2015/04/04/busuanzi/
busuanzi_count:
  enable: true
  total_visitors: true
  total_visitors_icon: user
  total_views: true
  total_views_icon: eye
  post_views: false #避免与leanclound_visitors冲突
  post_views_icon: eye
```
##### 站内搜索
``` ymal
# Local search 站内搜索
# Dependencies: https://github.com/theme-next/hexo-generator-searchdb
local_search:
  enable: true
  # if auto, trigger search by changing input
  # if manual, trigger search by pressing enter key or search button
  trigger: auto
  # show top n results per article, show all results by setting to -1
  top_n_per_article: 1
  # unescape html strings to the readable one
  unescape: false
```
##### 书签支持
``` ymal
# Bookmark Support
# Dependencies: https://github.com/theme-next/theme-next-bookmark
bookmark:
  enable: true
  # if auto
  #   - save the reading position when closing the page
  #   - or clicking the bookmark-icon
  # if manual, only save it by clicking the bookmark-icon
  save: auto
```
##### 阅读进度显示
``` ymal
# Reading progress bar
# Dependencies: https://github.com/theme-next/theme-next-reading-progress
reading_progress:
  enable: true
  color: "#37c6c0"
  height: 2px
```
至此，GHN方案建站的流程介绍完了。如有疑问欢迎交流。
