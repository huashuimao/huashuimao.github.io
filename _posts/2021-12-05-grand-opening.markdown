---
layout: post
title:  "开张大吉"
date:   2021-12-05 23:11:17 +0800
categories: common
---
1. 搭建 GitHub Pages ，我这里跟着 [使用Github做一个完全免费的个人网站(步骤很细)]{:target="_blank"} 、或者也可看官方文档 [GitHub Pages 文档]{:target="_blank"} 创建的 github 的 pages 仓
    1. 创建仓库，名称必须是 用户名.github.io， 例如我这里个是 huashuimao.github.io
    1. 放一个 index.html ，里面写上 hello world 
    1. 刷新后就可以通过 用户名.github.io 访问
    1. 你也可以直接拉我的仓库，回退到第一个提交，看看效果，hhhh~

使用 jekyll 生成静态网页

1. 简单看了下各个静态网页生成器，选择 Jekyll
    1. 安装 Ruby - 去 Ruby 官网下最新的，我这里同时安装了 Ruby + Devkit，之后通过 ruby --version 、 gem --version 查看安装结果
    1. 安装 bundle - gem install bundler
    1. 添加 webrick ，否则之后 jekyll 生成页面会报错，内容为 cannot load such file -- webrick (LoadError)
    1. 安装 jekyll - gem install jekyll
    1. 找个空目录生成默认主题的站点 - jekyll new .
    1. 使用 jekyll serve 启动并生成网页，并可进行访问

markdown 语法还不熟练，先这样简单几个流水账，hhhh~

1. 想要加个统计
    1. 这里使用了百度统计，发现需要在 head.html 模版中加入js脚本
    1. 了解了模版，我这里默认模版 minima ，在 ruby 的安装目录 Ruby30-x64/lib/ruby/gems/3.0.0/gems 下
    1. 按照 jekyll 规则创建 _includes 文件夹，并拷贝 head.html 出来
    1. 在头部添加从百度统计中拷贝出来的 js 脚本
    1. 这里参考了 [在jekyll中使用腾讯统计或百度统计]{:target="_blank"} 这篇文章
        1. 这里的链接本来是本页面打开，学习了 [让超链接在新窗口(新标签页)中打开Permalink]{:target="_blank"} 的方法，就可以新建页面打开了

Markdown语法参考：[Markdown官方教程] <https://markdown.com.cn/>{:target="_blank"}

[使用Github做一个完全免费的个人网站(步骤很细)]:https://zhuanlan.zhihu.com/p/91652100
[GitHub Pages 文档]:https://docs.github.com/cn/pages
[在jekyll中使用腾讯统计或百度统计]:https://plutotree.me/jekyll/2019/02/01/using-tencent-analytics-in-jekyll.html
[让超链接在新窗口(新标签页)中打开Permalink]:https://yinping4256.github.io/cn/Markdown%E8%AF%AD%E6%B3%95%E5%9C%A8%E6%96%B0%E7%AA%97%E5%8F%A3%E6%96%B0%E6%A0%87%E7%AD%BE%E9%A1%B5%E4%B8%AD%E6%89%93%E5%BC%80/
