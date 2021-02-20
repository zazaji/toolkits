# DOCKER 小贴士

## DOCKER 创建虚拟网络
```bash
docker network create -d macvlan --subnet=192.168.2.0/24 --gateway=192.168.2.1  -o parent=eth0 macnet
```
注意eth0与网卡设备对应，gateway与物理网卡网关对应，可以尝试增加--dns

## 使用虚拟桥接网卡，与宿主机在同一网段，独立IP不需要-p
-v、-p，冒号前为宿主机，冒号后为虚拟机
docker run -d --name=xxx -v /media:/media --restart always --privileged --network macnet --ip 192.168.2.7 sulinggg/xxx:x86_64  /sbin/init
