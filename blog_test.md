-------如何创建个人博客(hexo+Github)--------

博客由“生成框架(hexo)”，“托管平台(GitHub)”，“静态网站托管”来构建而成
---------------------------------------
附Hexo官网：[https://hexo.io/zh-cn/](https://hexo.io/zh-cn/)
附GitHub官网：[https://github.com/](https://github.com/huangyingyuan)
# 第一步，先配置开发环境（博客生成框架）
个人用的是windows系统

配置框架：hexo
## 输入网址(codejs.org)配置下载codejs,下载完成后
## 打开codejs小窗口
查看code版本：code -v

npm版本:       npm _v

能正常看到版本信息即可说明配置完成
## 插入疑惑？npm是啥？
npm（node package manager）：node.js 的包管理器，用于node插件管理（包括安装、卸载、管理依赖等） ，npm 是随同 node.js 一起安装的包管理工具，能解决 node.js 代码部署上的很多问题
## 修改npm的网源(因为npm官网源下载速度比较慢)
推荐用TB(淘宝)的网源：
npm config get registry # 查看原来的源

npm config set registry [https://registry.npm.taobao.org](https://registry.npm.taobao.org) # 修改为淘宝源

npm config get registry # 查看现在的源
## 有了npm，安装hexo就方便了，只需要一行代码
npm install hexo-cli -g # 全局安装hexo命令行工具
## 插入疑惑？hexo是啥？
Hexo 是一个快速、简洁且高效的博客框架。它允许用户使用 Markdown 语言编写内容，并将其渲染为静态网页。它相当于与一个网站的主题模板，只需要做简单的配置就能够完成页面的渲染。其主要特点包括快速部署，Markdown 支持，灵活的布局，丰富的插件。
### 初始化
在桌面右键建立一个名为MyBlog文件夹，点进文件夹里，再次右键，点击更多，打开Open Git Bash here(目的是在文件夹目录中下载hexo)
上步操作后，输入hexo init“你的目录名”
等待下载一系列文件在文件夹中即可

1. 在github平台上注册账号(需要翻墙，因为是国外的站点)
2. 在github平台上创建库

	----找到“Start a new respository”然后在CesteoNew右边输入自己的仓库的名称(最好是“自己的用户名.github.io”)
## 在git小窗口上初始化自己的邮箱和用户名
初始化用户名： git config –global user.name “自己的用户名”

初始化邮箱：	git config -gloobal user.email “自己的邮箱”

疑惑？
如何自己检查自己的用户名与邮箱是否被记住？

检查自己的用户名----输入代码“git config -global user.name

检查自己的郵箱------输入代码“git config -global user.email

### 配置SSH
先在git小窗口，输入“ssh-keygen -t rsa -C “你的邮箱”。然后一直按回车，直到出现一串代码，把代码复制下来(用在后面的SSH key提取)

点开Github，点击头像，点击setting然后找到SSH and GPG keys，进入里面，new一个SSH key

-----在Tille处，随便填即可

-----下面的key粘贴刚才的代码进去即可（产生一个简单的连接）

验证是否连接成功？

在小窗口输入“ssh -T [git@github.com](mailto:git@github.com)”  出现yes与no的问答，回答yes即可
### 配置连接来上传部署
(获取仓库地址)点开Github，点击左上角头像，下面有一串网址，点击进去后，点击SSH键，复制那个码(用于下面加进去的repository后的网址)

	然后在文件‘_config.yml’中用记事本打开，在后面几行输入如下：

![](https://cdn.nlark.com/yuque/0/2024/png/43278603/1712670272067-bea9c831-2fd5-4043-ae1b-3ad791d7d670.png#averageHue=%23eeedec&id=LEsax&originHeight=157&originWidth=1343&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

注意，在冒号后面是要加一个空格的，否则报错

保存好修改的内容后，将git用cd切换到对应的目录内，然后输入hexo d 来上传文件到github内，出现以下代码即可

![](https://camo.githubusercontent.com/869baa856bc7d205940d71301116679045c687966d2f33bf108c042b6e0034f9/68747470733a2f2f63646e2e6e6c61726b2e636f6d2f79757175652f302f323032342f706e672f34333237383630332f313731323637303237323332322d61333630353537652d653066392d346539352d626363622d3236643966376363363732652e706e6723617665726167654875653d2532333063306130372669643d55466d7738266f726967696e4865696768743d333632266f726967696e57696474683d373238266f726967696e616c547970653d62696e61727926726174696f3d3126726f746174696f6e3d302673686f775469746c653d66616c7365267374617475733d646f6e65267374796c653d6e6f6e65267469746c653d#from=url&id=lwIrB&originHeight=362&originWidth=728&originalType=binary&ratio=1.25&rotation=0&showTitle=false&status=done&style=none&title=)

可以在github上的code查看是否上传成功
## 重要的_config.yml文件
### _config.yml文件是干嘛用的？
是 Hexo 博客框架的主配置文件，用于配置和管理整个 Hexo 项目的各种设置。这个文件通常位于 Hexo 项目的根目录下，包含了大量的配置选项，可以让您自定义博客的行为、外观和功能。
### 继续修改_config,yml文件里的内容
(主要修改url，将你打开hexo的网址复制粘贴到url位置就可以，title是指标题，subtitle是副标题，author是指自己的称呼，自行修改即可)
	统一资源定位符（Uniform Resource Locator）”简称为URL。![](https://cdn.nlark.com/yuque/0/2024/png/43278603/1712670273010-5496424d-0f11-40ce-ac3e-fbe677e48a35.png#averageHue=%23f1f0f0&id=pck3w&originHeight=521&originWidth=1763&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
上传后去hexo界面自己刷新一下就好了，主题之类的就会发生变化

## 如何部署网站
要将 Hexo 博客从本地（localhost）部署到一个永久可以访问的地址上，通常有两种常见的方法：

1. **部署到 GitHub Pages**
2. **部署到其他静态网站托管服务**

我是使用“部署到GitHub Pages”来实现的(推荐，推荐原因：方便)
### 1. 部署到 GitHub Pages
#### 步骤 1：创建 GitHub 仓库

1. 登录 GitHub 并创建一个新的仓库，命名为 `username.github.io`，其中 `username` 是你的 GitHub 用户名。
#### 步骤 2：配置 Hexo 部署设置
在 Hexo 项目的根目录下找到 `_config.yml` 文件，打开并找到 `deploy` 部分，添加如下配置：
```
deploy:
  type: git
  repository: https://github.com/username/username.github.io.git
  branch: main
```
将 `username` 替换为你的 GitHub 用户名。

如果你的仓库默认分支是 `master` 而不是 `main`，需要将 `branch` 设置为 `master`。
#### 步骤 3：安装 Hexo 部署插件
在 Hexo 项目的根目录下，安装 `hexo-deployer-git` 插件：
```
npm install hexo-deployer-git --save
```
#### 步骤 4：生成和部署网站
生成并部署你的网站：
```
hexo clean
hexo generate
hexo deploy
```
运行上述命令后，你的网站将被生成并推送到 GitHub Pages 仓库。你可以在浏览器中访问 `https://username.github.io` 来查看你的博客。
### 2. 部署到其他静态网站托管服务
如果你不想使用 GitHub Pages，你也可以选择其他静态网站托管服务，如 Netlify、Vercel 或者 GitLab Pages。
#### 部署到 Netlify

1. 创建一个 Netlify 账号并登录。
2. 新建一个站点并关联到你的 GitHub 仓库。
3. 在构建设置中，将构建命令设置为 `hexo generate`，将发布目录设置为 `public`。
4. 保存并部署。

Netlify 将自动生成并部署你的网站，你可以在 Netlify 提供的 URL 上访问你的网站。
#### 部署到 Vercel

1. 创建一个 Vercel 账号并登录。
2. 新建一个项目并关联到你的 GitHub 仓库。
3. 在项目设置中，将构建命令设置为 `hexo generate`，将输出目录设置为 `public`。
4. 保存并部署。

Vercel 将自动生成并部署你的网站，你可以在 Vercel 提供的 URL 上访问你的网站。
### 3. 配置自定义域名
无论你选择哪种托管服务，你都可以配置一个自定义域名来访问你的网站。

1. 购买一个域名并登录到你的域名注册商的控制面板。
2. 添加一个 CNAME 记录，指向你的托管服务提供的域名。例如，对于 GitHub Pages，CNAME 记录应该指向 `username.github.io`。
3. 在你的 Hexo 项目根目录下的 `source` 文件夹中创建一个名为 `CNAME` 的文件，文件内容是你的自定义域名（例如，`www.yourdomain.com`）。
4. 部署你的网站，托管服务将使用你的自定义域名。

通过以上步骤，你可以将你的 Hexo 博客从本地部署到一个永久可以访问的地址上，并且可以使用自定义域名来访问你的博客
# 使用
在自己部署的GitHub项目的文件下，使用git bash打开
## 1，上传文章到hexo上
	---在git的小窗口，输入hexo new “文章的新名字”，就可以生成一篇新的文章
		在自己的目录下，点击sourse，点post，即可看到文章，点进去后用记事本编辑内容即可，写完文章后，在git上输入hexo g 来上传文章，如果报错，可能是要删除tig下面的符号即可(具体说明原因我也不清楚)
	上传成功后可以在自己的目录下，点击public，里面有year，点进去后可以看到对应日期的文章(是同步GitHub上传的文章)
hexo d(hexo deploy)    自动生成网站静态文件，并部署到设定的仓库。
hexo clean             清除缓存文件 db.json 和已生成的静态文件 public。
hexo g (hexo generate)  生成网站静态文件到默认设置的 public 文件夹

## 2，如何删除文件夹
 先在sourse上删除文件，然后在public上删除文件，最后在git小窗口输入
	hexo clean来刷新，后来用hexo g，再用hexo d ，即可删除内容

# 优化界面
依旧是在自己部署的GitHub项目的文件下，在与_config.yml同级文件下，命名一个为themes的文件夹，里面存放在别人的Hithub开源的主题代码，拉取到该文件themes下即可

开源网址(一时嫖一时爽，天天嫖天天爽)
有多种主题自己选：    [https://hexo.io/themes/](https://hexo.io/themes/)  
我非常喜欢逛的博主(最喜欢白嫖他的东西)：[https://www.fomal.cc/page/2/#content-inner](https://www.fomal.cc/page/2/#content-inner)
## 部署主题
具体流程：
### 步骤 1：安装 Hexo

如果你还没有安装 Hexo，请先安装：
npm install -g hexo-cli
### 
步骤 2：创建一个新的 Hexo 项目

在你的工作目录中创建一个新的 Hexo 项目：
hexo init myblog
cd myblog
npm install
### 
步骤 3：选择并下载一个 Hexo 主题

你可以从 Hexo 官方主题网站 或者其他第三方网站选择一个你喜欢的主题。以下是安装主题的示例：
打开主题的 GitHub 页面，找到下载地址。
在 Hexo 项目的根目录下，克隆主题仓库：(注意将对应的参数替换成自己的)
git clone [https://github.com/hexojs/hexo-theme-landscape](https://github.com/hexojs/hexo-theme-landscape) themes/landscape
### 
步骤 4：修改 Hexo 配置文件

在 Hexo 项目的根目录下找到 _config.yml 文件，打开并修改 theme 字段为你下载的主题名称：
yaml
#### Hexo Configuration
Docs: [https://hexo.io/docs/configuration.html](https://hexo.io/docs/configuration.html)

Source: [https://github.com/hexojs/hexo/](https://github.com/hexojs/hexo/)
#### Site
title: Huangyingyuan's new Blog

subtitle: 'Welcome to My Blog'

description: 'programming study'

author: Hungyingyuan

language: zh-CN

timezone: 'Asia/Shanghai'
#### URL
url: [https://huangyingyuan.github.io/](https://huangyingyuan.github.io/)

permalink: year/:month/:day/:title/

pretty_urls:

  trailing_index: false

  trailing_html: false
#### Directory
source_dir: source

public_dir: public
#### Writing
new_post_name: :title.md

default_layout: post
#### Extensions
theme: landscape  # 这里修改为你下载的主题名称
### 
步骤 5：配置主题

大多数 Hexo 主题都有自己的配置文件。通常，这些配置文件位于主题目录下的 _config.yml 文件中。你可以根据需要修改这些配置文件以定制主题样式和功能。
cd themes/landscape
打开并编辑 _config.yml 文件，根据需要进行配置。例如：
#### Landscape theme configuration
menu:
  Home: /
  Archives: /archives
widgets:

- category
- tag
- tagcloud
- recent_posts
#### 配置其他参数，如社交媒体链接、分页、侧边栏等
rss: /atom.xml
favicon: /favicon.png
### 
步骤 6：生成和部署网站

在完成配置后，回到 Hexo 项目的根目录，生成并部署你的网站：
cd ../../
hexo clean
hexo generate
hexo deploy
### 
步骤 7：本地查看效果

你可以在本地启动一个服务器来查看效果：
hexo server
然后在浏览器中打开 [http://localhost:4000](http://localhost:4000) 查看你的网站。


这篇新鲜出炉的教程如果我写得不好的话，那还是挺好的
# 待完未续......敬请期待。。。。。。。。。。
## 看到都看到这里了，微信一键发个红包，支付宝也不介意..


