---
layout: post
title:  "使用 luajit 生成二进制报错"
date:   2021-12-06 23:11:17 +0800
categories: build
---
报错:
```
unknown luaJIT command or jit.* modules not installed
```

解决：
```
机器上配置了 **LUA_PATH**、**LUA_CPATH** 导致 luajit 无法正常工作
删掉这两个环境变量就OK了
```
  
过程：
1. 打包失败，发现拷贝 Lua 生成的二进制数据时候错误
1. 在打包机上一通查找，最后直接到 luajit 目录下，使用命令行 luajit.exe -b 来源路径 生成路径 ，发现根本没有正确生成路径
1. 有且仅有那台打包机发生问题
1. 网络上搜索 unknown luaJIT command or jit.* modules not installed 报错，基本都是说 luajit 层级错误
1. 在 [unknown luaJIT command or jit.* modules not installed #9] 中得到一些头绪
1. 无法生成，是否是环境变量里面出问题
1. 检查，发现环境变量中，存在 LUA_PATH、LUA_CPATH，进一步发现是安装了 Scoop 并同步安装了 Lua 环境
1. 删除环境变量，并重启机器
    1. 前面忘记重启了，浪费了一些时间

[unknown luaJIT command or jit.* modules not installed #9]:https://github.com/openresty/opm/issues/9