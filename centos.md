

## centos 8 国内镜像

```bash
cd /etc/yum.repos.d/
rm -f CentOS-Base.repo CentOS-AppStream.repo CentOS-PowerTools.repo CentOS-centosplus.repo CentOS-Extras.repo
curl -o CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-8.repo
yum makecache
yum install -y curl geoip
yum install mesa-libGL.x86_64
```
或者
```bash
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-8.repo
```

## 安装bt面板

```bash
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh
```
## npm国内源及镜像
```bash
yum install -y node
npm install -g cnpm --registry=https://registry.npm.taobao.org
cnpm install yarn -g
cnpm install nodemon -g
Cnpm i n -g
cnpm install vue-cli -g
```

```

## talib 安装

```bash
wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz
tar -xvf ta-lib-0.4.0-src.tar.gz&&cd ta-lib&&./configure&&make&&make install
```
在 /etc/profile最后一行加上
`export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH`
```bash
source /etc/profile
pip install TA-Lib
```

##  Matplotlib 中文字体显示
拷贝文件simhei.ttf到matplotlib字体目录
```bash
plt.rcParams['font.sans-serif'] = ['SimHei']  # 用来正常显示中文标签
plt.rcParams['axes.unicode_minus'] = False  # 用来正常显示负号
jupyter notebook retina
%config InlineBackend.figure_format = 'retina'
```
由于 notebook 是 JSON 文件，因此，可以轻松将其转换为其他格式。Jupyter 附带了一个名为 nbconvert 的实用程序，可将 notebook 转换为 HTML、Markdown、幻灯片等格式。
例如，要将 notebook 转换为 HTML 文件，请在终端中使用
jupyter nbconvert --to html notebook.ipynb
幻灯片：
jupyter nbconvert notebook.ipynb --to slides
jupyter nbconvert notebook.ipynb --to slides --post serve
