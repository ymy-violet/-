### GitHub 弃用 TLS 1.0、1.1 导致 push 异常

#### 报错

git push到 github上报错：
![QQ图片20200330175404.png](https://i.loli.net/2020/03/30/ArJZmtc8EKMiPCf.png)

#### 原因
在 2018年2月22日19:00 UTC（太平洋标准时间上午11:00），GitHub 停止了对加密弱 TLS 1.0 和 1.1 协议的支持，并且仅支持与 TLS 1.2 协议的连接。

官方声明：

[Github . Weak cryptographic standards removal notice](Github . Weak cryptographic standards removal notice)

因此，如果你的 git 连接方式仍然是 TLS 1.0 或 1.1，则会报错。

#### 解决
- 查看你的TLS版本

> git config --global --list 

-  如果仍然是 TLS 1.0 或 1.1，则下载更新 Git 最新版：[https://git-scm.com/](https://git-scm.com/)
-  安装好最新版 Git 后，更新 TLS

> git config --global --unset http.sslVersion
> git config --global --add http.sslVersion tlsv1.2

操作如下图：
![QQ图片20200330191830.png](https://i.loli.net/2020/03/30/lof7y5INjdWpQCA.png)

