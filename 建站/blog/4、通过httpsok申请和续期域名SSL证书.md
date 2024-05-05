# 4、通过httpsok申请和续期域名SSL证书

## httpsok介绍

主页：https://httpsok.com/

用途：httpsok 是一个便捷的 HTTPS 证书自动续签工具，专为 Nginx 服务器设计。已服务众多中小企业，稳定、安全、可靠。

### 特性

- ⚡️ 简单高效 一行命令，一分钟轻松搞定SSL证书自动续签
- ✅ 自动检测 无需关心nginx配置，自动识别证书配置，适合老旧系统、复杂配置的生产环境
- ✅ 泛解析、多域名、多服务器 轻松搞定
- ✅ 证书监控 对于即将失效的证书，提供公众号推送提醒
- ✅ 兼容性好 兼容主流的Linux系统 `Debain` `CentOS` `Ubuntu` `TencentOS` 等
- ✅ 支持手动申请 支持手动申请证书，方便部署CDN、OSS等场景。
- httpsok部署方式整个部署过程相对传统服务器部署要简单易操作，一键HTTPS，仅需配置一个 CNAME 解析，即可实现从 HTTP 到 HTTPS 的能力升级。不仅能够降低维护成本，简单的配置方式也可降低操作性事故发生的可能性。

### 使用场景

- Nginx自动续期https证书
- 适合多台nginx服务器的情况
- 适合多域名、泛解析
- 老旧系统，不敢去修改nginx配置

## 申请SSL证书

登录后台 `https://httpsok.com/console/cert`，访问证书管理页面，选择申请免费证书

- 域名：选通配符证书
- 证书厂商：ZeroSSL
- 加密算法：ECC

按提示，登录域名解析后台，添加域名解析记录，等待一段时间，验证通过后状态会变成通过即可

```Plain
_acme-challenge CNAME xxxxxxxxx.httpsok.com
```

申请通过后，在证书管理界面可以下载证书，上传到服务器并替换成对应的名称

![image-20240430221221731](assets/image-20240430221221731.png)

上传到主机/etc/nginx目录下，并修改名称

## 自动更新SSL证书

SSH登录服务器，执行快速部署，其中$token，按实际情况填写

```Bash
curl -s https://get.httpsok.com | bash -s $token
```

httpsok会下载脚本到主机上，并添加定时任务，每天自动检测证书过期情况，进行延期处理

```Bash
45 9 * * * '/home/ubuntu/.httpsok/httpsok.sh' -m -r >> '/home/ubuntu/.httpsok/httpsok.log' 2>&1
```