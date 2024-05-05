# 8、利用Docsify制作个人博客-正式开工

## 前言

对自己建个人博客的想法长期停留在应该做，但还没做的阶段。今天想了一些事情，想通了。很多事情在你没动手的时候，是没法预测太远的，毕竟能力有限，尽早开始才是适合大部分犹豫不决之人的路。

看到docsify后，让自己专注写作就能建站，很适合自己。

居于前面几章的折腾，大概了解了如何使用docsify，并将它发布到互联网上。今天正式开工，该怎么设计个人博客的布局呢？我在犹豫。在 `https://github.com/docsifyjs/awesome-docsify?tab=readme-ov-file#showcase`逛了逛，发现[字节飞扬](https://bytesfly.github.io/blog/)，建站的初心，页面布局，需要呈现的内容与我的想法比较一致，决定参考进行页面布局设计，感谢！

## 设计思路

* 导航栏

参考：[字节飞扬](https://bytesfly.vercel.app/#/)

```markdown
├──首页
├──导航
│   ├──"只展示侧边栏第一层级的链接"
├──友链
├──常用工具
│   ├── JSON在线解析
│   ├── 子网掩码计算器
├──GitHub
```

* 侧边栏

相关内容后续可能会动态变化。

参考：[侠客岛](https://bytesfly.github.io/island/#/)，支持多层级收缩，点击后可展示，最多四级。点击后右侧内容区直接展示内容。

```markdown
├──AI
├──CICD
│   ├──DroneCI
│   ├──ArgoCD
│   ├──Jenkins
├──macOS
├──建站
├──Linux
├──监控
├──日志
├──Kubernetes
├──个人生活
├──技术随笔
```

* 封面

要有，先用默认的

* 网站icon

先用AI制作的icon

![icon](assets/icon.png)

* 底部栏

```markdown
留下一些成长的印记。 —— luyx30

Published with docsify.
```

* 其他

支持扫描添加微信公众号，使用大模型制作一个自动回复信息的机器人

支持搜索

支持打赏

支持统计

使用github pages存放页面：`https://github.com/luyx30/blog`

同时支持使用自定义域名访问：`https://blog.dmxing.top`

个人信息说明

```markdown
昵称：luyx30
头像：用网站icon
主页：https://blog.dmxing.top/
说明：留下一些成长的印记。
```

## 参考链接

字节飞扬：`https://bytesfly.github.io/blog/`、`https://github.com/bytesfly/blog`

AI & CS & SE：`https://notebook.js.org/#/`、`https://github.com/wugenqiang/NoteBook`

侠客岛：`https://bytesfly.github.io/island/#`
