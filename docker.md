# DOCKER 小贴士

## DOCKER 创建虚拟网络
```bash
docker network create -d macvlan --subnet=192.168.2.0/24 --gateway=192.168.2.1  -o parent=eth0 macnet
```
注意eth0与网卡设备对应，gateway与物理网卡网关对应，可以尝试增加--dns

## 使用虚拟桥接网卡，与宿主机在同一网段，独立IP不需要-p，需要配置网络之后才能使用
-v、-p，冒号前为宿主机，冒号后为虚拟机
```bash
docker run -d --name=xxx --restart always -v /media:/media --privileged --network macnet --ip 192.168.2.7 sulinggg/xxx:x86_64  /sbin/init
```

## 使用虚拟桥接网卡，与宿主机共享对外IP，映射端口
-v、-p，冒号前为宿主机，冒号后为虚拟机
```bash
docker run -d -p 9000:9000 --restart=always -v /var/run/docker.sock:/var/run/docker.sock --name prtainer-test portainer/portainer
```

## 一个已经生成的容器挂载目录
```bash
docker run -it -v /home/dock/Downloads:/usr/Downloads ubuntu64 /bin/bash
```

## 进入容器配置网络
```bash
docker container exec -it openwrtX86 bash
vi /etc/config/network
	option ipaddr '192.168.2.6'                                                                                                                         
	option gateway '192.168.2.1'                                                                                                                         
	option dns '8.8.8.8 192.168.2.1'                                                                                                                         
 
/etc/init.d/network restart
```


## 容器导出
```bash
docker export 1e560fca3906 > ubuntu.tar
```

## 容器导入
```bash
$ cat docker/ubuntu.tar | docker import - test/ubuntu:v1
```
此外，也可以通过指定 URL 或者某个目录来导入，例如：
```bash
$ docker import http://example.com/exampleimage.tgz example/imagerepo
```
