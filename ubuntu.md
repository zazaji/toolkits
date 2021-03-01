### 更新apt国内源
```
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
```

### 安装 typra
```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -

sudo add-apt-repository 'deb https://typora.io/linux ./'
sudo apt-get update
sudo apt-get install typora
```
### 安装rime输入法
`https://github.com/rime/home/wiki/RimeWithIBus`
```bash
sudo apt-get install ibus-rime
sudo apt-get install librime-data-luna-pinyin
sudo yum install ibus-rime
```
然后配置安装方案`https://rime.im/`

### 修改密码
sudo passwd username

### simple note 笔记软件
snap install simplenote

gpg --keyserver keyserver.ubuntu.com --recv 4E5E17B5
gpg --export --armor 4E5E17B5 | sudo apt-key add -
apt install unzip


### 配置IP
```bash
cd /etc/netplan
vi ifcfg-enp3s0
ethernets:
     enp3s0: #配置的网卡名称,使用ifconfig -a查看得到
       dhcp4: no #dhcp4关闭
       addresses: [192.168.202.36/24] #设置本机IP及掩码
       gateway4: 192.168.202.1 #设置网关
       nameservers:
       addresses: [192.168.202.1]
sudo netplan apply
```
