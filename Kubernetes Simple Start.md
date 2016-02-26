 <p id="top"></p>
 
[TOC]

# Kubernetes Simple Start
 
@(K8s)[Kubernetes, Build]
![kube](https://www.ustack.com/wp-content/uploads/2015/06/og_img.jpg)

Kubernetes��Google��Դ����������ϵͳ, �Ѿ���չ��1.0.1�棬Ϊ�˸��õ�ѧϰkubernetes, ���ǿ����Լ�������������л������о�ϵͳϸ�ڡ�����Ī���ڴһ������ʵ�黷��������һ̨����������Kubernetes�Ķ�����������etcd��kube-apiserver��kube-scheduler��kube-controller-manager��kube-proxy��kubelet��

![���](https://www.ustack.com/wp-content/uploads/2015/06/k8s-singlenode-docker.png)

## Requirements
### Linux
ubuntu �Ƽ�ubuntu 14.04,  15.04 ð�Ʊ�����bug. �����ﶼ��fedroa20����ʵ�飬fedroa ��20��ʼ֧��docker���ʰ汾��ʹ�� fedroa 20+. 
### golang 
��Ҫ�汾 1.3+
`$ go version`
`go version go1.4.2 linux/amd64`

### docker
��Ҫ�汾1.3+
`$ docker --version`
`Docker version 1.8.3, build f4bf5c7`

[goto top](#top)

### etcd
���ص�ַ��https://github.com/coreos/etcd/releases
�����и���ƽ̨�����º���ʷ�汾�����µ�kubernetes Ҫ��etcd�汾����2.0.0

- ��ȡetcd, ����Ƚϼ򵥣���ѹ��ֱ�ӷŵ�/usr/local/bin�¼��ɡ�

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
�����ű������÷Ǳ���

[goto top](#top)
### ע������
- �����vmware�����±���
kubernetes �ýű�build-go.shʱ��Ҫ����һЩ�����ӣ����Դ������windows�Ĺ���Ŀ¼�£������޷�����ͨ��������Ҫ���ص�������ڲ�

## Starting the cluster
���뱾��Ŀ¼��ʹ��rootȨ�����нű����ýű����ȱ��룬Ȼ�����ò�����cluster. ���ֻ��Ҫ�������У�����������Ľű���

`cd kubernetes`
`hack/local-up-cluster.sh` 

���ֻ���뱾ƽ̨��ִ�г���������
`hack/build-go.sh`

�ο���
1.  [�����ο�](http://kubernetes.io/v1.0/docs/getting-started-guides/locally.html)
2.  [�����Kubernetes��������](https://www.ustack.com/blog/kubernetes1/)
