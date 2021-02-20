# 安装rust
```bash
curl https://sh.rustup.rs -sSf | sh
```
# 如果不能安装

### 编辑文件
```bash
vim ~/.bashrc
```
### 在文件中加入以下两句
```bash
export RUSTUP_DIST_SERVER=https://mirrors.ustc.edu.cn/rust-static
export RUSTUP_UPDATE_ROOT=https://mirrors.ustc.edu.cn/rust-static/rustup
```
### 接下来运行命令使文件生效
```
source ~/.bashrc
```
### 然后就可以进行安装

curl -sSf https://mirrors.ustc.edu.cn/rust-static/rustup.sh | sh -s
## 进行最后的配置,config可能不存在，创建就完了
```bash
cd /root/
mkdir .cargo
cd .cargo 
vim config
```
## 在文件中填入以下内容
```note
[registry]
index = "https://mirrors.ustc.edu.cn/crates.io-index/"
[source.crates-io]
registry = "https://github.com/rust-lang/crates.io-index"
replace-with = 'ustc'
[source.ustc]
registry = "https://mirrors.ustc.edu.cn/crates.io-index/"
```
