# btpanel
btpanel7.7开心版

1、安装时如果报错，请先部署环境后再重新安装（此处以Debian系统为例，其他系统参照）
```
apt update -y && apt dist-upgrade -y && apt install -y curl && apt install -y socat 
apt-get install -y xz-utils openssl gawk file wget screen && screen -S os
```

宝塔面板自7.8开始，违背了宝塔开源协议，竟然在免费版的源码里面加入了加密的授权验证模块。除此之外，7.8版本使用各种方法均无法绕过面板强制绑定账号，如果不绑定账号插件就无法下载。因此这里分享一下7.7版本的安装脚本，以及开心方法。

纯原版？：
```
curl -sSO https://raw.githubusercontent.com/youink/panel/master/install_panel.sh && bash install_panel.sh 
```

彩虹优化版：
``` 
wget -O install.sh https://raw.githubusercontent.com/youink/panel/master/install_6.0.sh && bash install.sh 
```

彩虹升/降级到7.7命令：
``` 
curl https://raw.githubusercontent.com/youink/panel/master/update6.sh|bash
```

2、宝塔7.7原版一键开心脚本
```
curl -sSO https://raw.githubusercontent.com/youink/panel/master/one_key_happy.sh && bash one_key_happy.sh
```

3、更改SSH终端中文语言
```
wget -N --no-check-certificate https://raw.githubusercontent.com/youink/panel/master/LocaleCN.sh && bash LocaleCN.sh
```
开心版安装完成后使用 bt 命令可能出现报错，只需要将终端设置为中文语言即可。（可以查阅LocaleCN.sh文件中对应系统的修改命令，先备份好原始文件，然后使用该命令修改语言并重启，尝试 bt 命令正常后，再恢复原有语言文件。这样做的目的是因为在后期使用时个别程序会因为语言不一致，而导致程序无法正常运行。）


4、宝塔7.7一键优化补丁
```
1.去除宝塔面板强制绑定账号
2.去除各种删除操作时的计算题与延时等待
3.去除创建网站自动创建的垃圾文件（index.html、404.html、.htaccess）
4.关闭未绑定域名提示页面，防止有人访问未绑定域名直接看出来是用的宝塔面板
5.关闭活动推荐与在线客服，去除首页企业版广告
6.去除自动校验文件与上报信息定时任务
7.去除面板日志与网站绑定域名上报
```

原链接
```
bash
wget -O optimize.sh http://f.cccyun.cc/bt/optimize.sh && bash optimize.sh
```

本仓库
```
bash
wget -O optimize.sh https://raw.githubusercontent.com/youink/panel/master/optimize_mod.sh && bash optimize.sh
```
* 如果Ngnix创建的网站出现403 forbidden(保留网站创建的文件)
```
bash
wget -O optimize.sh https://raw.githubusercontent.com/youink/panel/master/optimize_mod.sh && bash optimize.sh
```
