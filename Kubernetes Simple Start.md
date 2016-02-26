 <p id="top"></p>
 
[TOC]

# Kubernetes Simple Start
 
@(K8s)[Kubernetes, Build]
![kube](https://www.ustack.com/wp-content/uploads/2015/06/og_img.jpg)

Kubernetes是Google开源的容器调度系统, 已经发展到1.0.1版，为了更好的学习kubernetes, 我们可以自己编译后搭建本地运行环境，研究系统细节。最方便的莫过于搭建一个单机实验环境，即在一台主机上运行Kubernetes的多个组件，包括etcd、kube-apiserver、kube-scheduler、kube-controller-manager、kube-proxy、kubelet。

![组件](https://www.ustack.com/wp-content/uploads/2015/06/k8s-singlenode-docker.png)

## Requirements
### Linux
ubuntu 推荐ubuntu 14.04,  15.04 冒似编译有bug. 我这里都在fedroa20做的实验，fedroa 从20开始支持docker，故版本请使用 fedroa 20+. 
### golang 
需要版本 1.3+
`$ go version`
`go version go1.4.2 linux/amd64`

### docker
需要版本1.3+
`$ docker --version`
`Docker version 1.8.3, build f4bf5c7`

[goto top](#top)

### etcd
下载地址：https://github.com/coreos/etcd/releases
这里有各个平台的最新和历史版本，最新的kubernetes 要求etcd版本大于2.0.0

- 获取etcd, 这个比较简单，解压后直接放到/usr/local/bin下即可。

```
$ curl -L  https://github.com/coreos/etcd/releases/download/v2.3.0-alpha.0/etcd-v2.3.0-alpha.0-linux-amd64.tar.gz -o etcd-v2.3.0-alpha.0-linux-amd64.tar.gz
$ tar xzvf etcd-v2.3.0-alpha.0-linux-amd64.tar.gz
```
- copy to system
```
cp etcd /usr/local/bin
cp etcdctl /usr/local/bin
```

- config
```
/etc/init.d/etcd
/etc/sysconfig/etcd
```
启动脚本和配置非必须

[goto top](#top)
### 注意事项
- 如果在vmware环境下编译
kubernetes 用脚本build-go.sh时需要产生一些软连接，如果源代码在windows的共享目录下，下则无法编译通过，故需要下载到虚拟机内部

## Starting the cluster
进入本地目录，使用root权限运行脚本，该脚本会先编译，然后配置并启动cluster. 如果只需要部分运行，可以自行需改脚本。

`cd kubernetes`
`hack/local-up-cluster.sh` 

如果只编译本平台可执行程序则运行
`hack/build-go.sh`

参考：
1.  [官网参考](http://kubernetes.io/v1.0/docs/getting-started-guides/locally.html)
2.  [搭建单机Kubernetes开发环境](https://www.ustack.com/blog/kubernetes1/)
