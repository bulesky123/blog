# 移动开发常用head标签

---

## HTML5、移动开发meta标签

---

- 声明字符编码 `<meta charset="utf-8">`

关于html标签中的lang属性：
简体中文 `<html lang="zh-cmn-Hans">`
繁体中文 `<html lang="zh-cmn-Hant">`

- 使用最新版的IE和Chrome

`<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />`

- 360 使用webkit内核渲染

`<meta name="renderer" content="webkit">`

- 禁止百度对网页转码(百度的Siteapp页面转码)

`<meta http-equiv="Cache-Control" content="no-siteapp" />`

## viewport

---

经常写：
`<meta name ="viewport" content ="width=device-width, initial-scale=1, maximum-scale=3, minimum-scale=1, user-scalable=no">`

content参数：

- width viewport 宽度(数值/device-width)
- height viewport 高度(数值/device-height)
- initial-scale 初始缩放比例
- maximum-scale 最大缩放比例
- minimum-scale 最小缩放比例
- user-scalable 是否允许用户缩放(yes/no)

iPhone 6 和 iPhone 6+ ：
`<meta name="viewport" content="width=375">`
`<meta name="viewport" content="width=414">`

## iOS设备

---

- 添加到主屏后的标题

`<meta name="apple-mobile-web-app-title" content="标题">`

- 是否启用webAPP进入全屏模式

`<meta name="apple-mobile-web-app-capable" content="yes" />`

- 状态栏的背景颜色

`<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />`

  content参数

    + default 默认值。
    + black 状态栏背景是黑色。
    + black-translucent 状态栏背景是黑色半透明。 如果设置为 default 或 black ,网页内容从状态栏底部开始。 如果设置为 black-translucent ,网页内容充满整个屏幕，顶部会被状态栏遮挡。

- 禁止数字识别为电话号码

`<meta name="format-detection" content="telephone=no" />`

## iOS图标

---

link标签，rel 参数： apple-touch-icon 图片自动处理成圆角和高光等效果。
apple-touch-icon-precomposed 禁止系统自动添加效果，直接显示设计原图。

- iPhone 和 iPod touch，默认 57×57px

`<link rel="apple-touch-icon-precomposed" href="/apple-touch-icon-57x57-precomposed.png" />`

- iPad，72×72px

`<link rel="apple-touch-icon-precomposed" sizes="72x72" href="/apple-touch-icon-72x72-precomposed.png" />`

- Retina iPhone 114×114px

`<link rel="apple-touch-icon-precomposed" sizes="114x114" href="/apple-touch-icon-114x114-precomposed.png" />`

- Retina iPad，144×144px

`<link rel="apple-touch-icon-precomposed" sizes="144x144" href="/apple-touch-icon-144x144-precomposed.png" />`

- iOS 图标大小在iPhone 6+上是180×180，iPhone 6 是120×120

适配iPhone 6+ `<link rel="apple-touch-icon-precomposed" sizes="180x180" href="retinahd_icon.png">`

## iOS 启动画面

---

iPad启动画面不包括状态栏区域

- iPad竖屏 768x1004

`<link rel="apple-touch-startup-image" sizes="768x1004" href="/splash-screen-768x1004.png" />`

- iPad 竖屏 1536×2008（Retina）

- iPad 横屏 1024×748（标准分辨率）

- iPad 横屏 2048×1496（Retina）

iPhone 和 iPod touch 的启动画面是包含状态栏区域的

- iPhone/iPod Touch 竖屏 320×480 (标准分辨率)

`<link rel="apple-touch-startup-image" href="/splash-screen-320x480.png" />`

- iPhone/iPod Touch 竖屏 640×960 (Retina)

- iPhone 5/iPod Touch 5 竖屏 640×1136 (Retina)

- iPhone 6对应的图片大小是750×1294，iPhone 6 Plus 对应的是1242×2148 。

`<link rel="apple-touch-startup-image" href="launch6.png" media="(device-width: 375px)">`
`<link rel="apple-touch-startup-image" href="launch6plus.png" media="(device-width: 414px)">`

添加智能 App 广告条 Smart App Banner（iOS 6+ Safari）

`<meta name="apple-itunes-app" content="app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL">`

## Android

---

![](https://camo.githubusercontent.com/de83bffedbcd34e410b660a3cef93fa1a166e345/687474703a2f2f696d6730312e74616f62616f63646e2e636f6d2f746673636f6d2f54423150476171485858585858585f585658585858585858585858)

`<meta name="theme-color" content="#db5945">`

## 完整版

---

```html
<!DOCTYPE html> <!-- 使用 HTML5 doctype，不区分大小写 -->
<html lang="zh-cmn-Hans"> <!-- 更加标准的 lang 属性写法 http://zhi.hu/XyIa -->
<head>
    <!-- 声明文档使用的字符编码 -->
    <meta charset='utf-8'>
    <!-- 优先使用 IE 最新版本和 Chrome -->
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"/>
    <!-- 页面描述 -->
    <meta name="description" content="不超过150个字符"/>
    <!-- 页面关键词 -->
    <meta name="keywords" content=""/>
    <!-- 网页作者 -->
    <meta name="author" content="name, email@gmail.com"/>
    <!-- 搜索引擎抓取 -->
    <meta name="robots" content="index,follow"/>
    <!-- 为移动设备添加 viewport -->
    <meta name="viewport" content="initial-scale=1, maximum-scale=3, minimum-scale=1, user-scalable=no">
    <!-- width=device-width 会导致 iPhone 5 添加到主屏后以 WebApp 全屏模式打开页面时出现黑边 http://bigc.at/ios-webapp-viewport-meta.orz -->

    <!-- iOS 设备 begin -->
    <meta name="apple-mobile-web-app-title" content="标题">
    <!-- 添加到主屏后的标题（iOS 6 新增） -->
    <meta name="apple-mobile-web-app-capable" content="yes"/>
    <!-- 是否启用 WebApp 全屏模式，删除苹果默认的工具栏和菜单栏 -->

    <meta name="apple-itunes-app" content="app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL">
    <!-- 添加智能 App 广告条 Smart App Banner（iOS 6+ Safari） -->
    <meta name="apple-mobile-web-app-status-bar-style" content="black"/>
    <!-- 设置苹果工具栏颜色 -->
    <meta name="format-detection" content="telphone=no, email=no"/>
    <!-- 忽略页面中的数字识别为电话，忽略email识别 -->
    <!-- 启用360浏览器的极速模式(webkit) -->
    <meta name="renderer" content="webkit">
    <!-- 避免IE使用兼容模式 -->
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <!-- 针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓 -->
    <meta name="HandheldFriendly" content="true">
    <!-- 微软的老式浏览器 -->
    <meta name="MobileOptimized" content="320">
    <!-- uc强制竖屏 -->
    <meta name="screen-orientation" content="portrait">
    <!-- QQ强制竖屏 -->
    <meta name="x5-orientation" content="portrait">
    <!-- UC强制全屏 -->
    <meta name="full-screen" content="yes">
    <!-- QQ强制全屏 -->
    <meta name="x5-fullscreen" content="true">
    <!-- UC应用模式 -->
    <meta name="browsermode" content="application">
    <!-- QQ应用模式 -->
    <meta name="x5-page-mode" content="app">
    <!-- windows phone 点击无高光 -->
    <meta name="msapplication-tap-highlight" content="no">
    <!-- iOS 图标 begin -->
    <link rel="apple-touch-icon-precomposed" href="/apple-touch-icon-57x57-precomposed.png"/>
    <!-- iPhone 和 iTouch，默认 57x57 像素，必须有 -->
    <link rel="apple-touch-icon-precomposed" sizes="114x114" href="/apple-touch-icon-114x114-precomposed.png"/>
    <!-- Retina iPhone 和 Retina iTouch，114x114 像素，可以没有，但推荐有 -->
    <link rel="apple-touch-icon-precomposed" sizes="144x144" href="/apple-touch-icon-144x144-precomposed.png"/>
    <!-- Retina iPad，144x144 像素，可以没有，但推荐有 -->
    <!-- iOS 图标 end -->

    <!-- iOS 启动画面 begin -->
    <link rel="apple-touch-startup-image" sizes="768x1004" href="/splash-screen-768x1004.png"/>
    <!-- iPad 竖屏 768 x 1004（标准分辨率） -->
    <link rel="apple-touch-startup-image" sizes="1536x2008" href="/splash-screen-1536x2008.png"/>
    <!-- iPad 竖屏 1536x2008（Retina） -->
    <link rel="apple-touch-startup-image" sizes="1024x748" href="/Default-Portrait-1024x748.png"/>
    <!-- iPad 横屏 1024x748（标准分辨率） -->
    <link rel="apple-touch-startup-image" sizes="2048x1496" href="/splash-screen-2048x1496.png"/>
    <!-- iPad 横屏 2048x1496（Retina） -->

    <link rel="apple-touch-startup-image" href="/splash-screen-320x480.png"/>
    <!-- iPhone/iPod Touch 竖屏 320x480 (标准分辨率) -->
    <link rel="apple-touch-startup-image" sizes="640x960" href="/splash-screen-640x960.png"/>
    <!-- iPhone/iPod Touch 竖屏 640x960 (Retina) -->
    <link rel="apple-touch-startup-image" sizes="640x1136" href="/splash-screen-640x1136.png"/>
    <!-- iPhone 5/iPod Touch 5 竖屏 640x1136 (Retina) -->
    <!-- iOS 启动画面 end -->

    <!-- iOS 设备 end -->
    <meta name="msapplication-TileColor" content="#000"/>
    <!-- Windows 8 磁贴颜色 -->
    <meta name="msapplication-TileImage" content="icon.png"/>
    <!-- Windows 8 磁贴图标 -->

    <link rel="alternate" type="application/rss+xml" title="RSS" href="/rss.xml"/>
    <!-- 添加 RSS 订阅 -->
    <link rel="shortcut icon" type="image/ico" href="/favicon.ico"/>
    <!-- 添加 favicon icon -->

    <title>标题</title>
</head>
```
