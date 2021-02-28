MAC OSX 重装系统后必备步骤
1. 安装brew ,北外源速度最快
```bash
xcode-select --install
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```
2. brew插件安装
```bash
brew install ta-lib   git wget mongo php composer mysql mysql-connector-c node libomp gcc llvm boost-python scrcpy
brew --cask install qlcolorcode qlstephen qlmarkdown quicklook-json qlimagesize webpquicklook suspicious-package quicklookase qlvideo
brew --cask install java8 android-platform-tools
```

3. mysql安装后不能登录
```bash
mysql_secure_installation
sudo mysql.server start
brew services start mysql
mysql -u root -p
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '12345678';FLUSH PRIVILEGES;
```
4. 安装 finalshell
```bash
curl -o finalshell_install.sh www.hostbuf.com/downloads/finalshell_install.sh;chmod +x finalshell_install.sh;sudo ./finalshell_install.sh
```
5. Sublime 配置
```js
{
"encoding": "utf-8",
 "working_dir": "_XXXX$file_pathXXXX_",
 "shell_cmd": “$path/python3 -u \"$file\"",
 "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
 "selector": "source.python"
}
```

6. 安装未知来源软件
`sudo spctl --master-disable`

7. 安装conda
```
curl  https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-py37_4.9.2-MacOSX-x86_64.sh｜bash
```
然后替换pip，conda国内源

8.鼠须管输入法
`brew install --cask squirrel`
`https://dl.bintray.com/rime/squirrel/Squirrel-0.15.2.zip`
9.搜狗拼音
`https://pinyin.sogou.com/mac/`
