---
layout: post
title:  "Unity 打 iOS 包出现 com.. 问题"
date:   2022-01-15 21:58:50 +0800
categories: work error build
---
使用 Jenkins 在 Mac 打包时，出现包名被修改为 `com..` 问题

核对后，发现是 Unity 的某个版本（2018.4.21f1 到 2018.4.36f1 之间）中，ProjectSetting 废弃了 `iOS` 字段，改用 `iPhone` 字段存储 Identifier 导致

Unity 会判定无自定包名时候（无iPhone字段==无配置），会使用 Company Name 和 Product Name 自动生成一份 com.CompanyName.ProductName 的 Identifier

由于我们的 CompanyName 和 ProductName 都是中文，导致无法正常生成，最终结果就变成了 `com..`

但是负责iOS打包的同事说在代码中强制设置 ApplicationIdentifier 也无效，之后看来得研究下是什么原因

先简单用 2018.4.36f1 版本设置下 iOS 的 Identifier，并将 ProjectSetting 提交上去解决吧

---

核对后，同事使用 [PleyrSetting.applicationIdentifier](https://docs.unity3d.com/cn/current/ScriptReference/PlayerSettings-applicationIdentifier.html) 属性进行设置，该接口仅对当前平台生效，我们项目默认是使用 Android 平台打开，故而导致其修改的是 Android 平台的 Identifier

这里算是一个坑点，推荐使用 [PlayerSetting.SetApplicationIdentifer](https://docs.unity3d.com/cn/current/ScriptReference/PlayerSettings.SetApplicationIdentifier.html) 接口进行设置，传入平台和标识

之前在设置其他东西的时候，印象里也踩过类似的坑，扶额