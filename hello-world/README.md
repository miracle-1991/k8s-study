# Hello-World

## 安装Docker-Desktop

[安装地址](https://docs.docker.com/desktop/linux/install/)  
首先下载deb,然后执行  
```
sudo apt install ./docker-desktop-4.9.1-amd64.deb
```
如果ubuntu之前已经安装过docker service并且设置为开机自启，需要进行关闭，否则会导致docker-desktop无法启动，一直显示Stoped：  
```
sudo systemctl disable docker
```
如果配置过代理，并且设置过http_proxy环境变量，需要删除此环境变量，此环境变量会导致kubectl命令失败：
```
#export http_proxy='http://127.0.0.1:1095/'
#export https_proxy='http://127.0.0.1:1095/'
#export no_proxy='localhost,127.0.0.1,kubernetes*'
#export all_proxy='socks5://127.0.0.1:1080/'
#export HTTP_PROXY='http://127.0.0.1:1095/'
#export HTTPS_PROXY='http://127.0.0.1:1095/'
#export ALL_PROXY='socks5://127.0.0.1:1080/'
#export NO_PROXY='localhost,127.0.0.1,kubernetes*'
```
安装完毕后，打开Docker-Desktop，并勾选"Enable Kubernetes"  
在设置中添加镜像加速：
```
  "registry-mirrors": [
    "https://c8it25aj.mirror.aliyuncs.com",
    "https://hub-mirror.c.163.com",
    "https://mirror.baidubce.com"
  ]
```

## 安装k8s插件
在goland的插件市场中找到Kubenetes插件，然后安装。  
打开“视图”-“工具窗口”-“服务”就能看到k8s中的各种资源对象。   
右键yaml文件就可以应用到k8s中，避免了手动输入kubectl的麻烦。