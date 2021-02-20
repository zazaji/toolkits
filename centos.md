

## centos 8 国内镜像

```bash
cd /etc/yum.repos.d/
rm -f CentOS-Base.repo CentOS-AppStream.repo CentOS-PowerTools.repo CentOS-centosplus.repo CentOS-Extras.repo
curl -o CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-8.repo
yum makecache
yum install -y curl
```


## 安装bt面板

```bash
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh
```

## anaconda 清华软件站地址

`https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/`

## conda 国内镜像
```bash
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda config --set show_channel_urls yes

```


##pip 国内源
```bash
mkdir ~/.pip/
touch ~/.pip/pip.conf
vi ~/.pip/pip.conf
```
写入
```bash
[global]
index-url = http://pypi.douban.com/simple
[install]
trusted-host=pypi.douban.com
```
或者
```bash
[global]
index-url = http://mirrors.aliyun.com/pypi/simple
[install]
trusted-host=mirrors.aliyun.com
```

## conda 安装模块
```bash
conda update --all keras  pandas numpy scipy  requests  theano  scikit-learn bcolz mysqlclient clang llvm line_profiler  
```

## pip 模块

```bash
pip install paddlepaddle stable_baselines snapshot-phantomjs pyecharts torch
pip install 	gym Ta-lib ta tflearn joypy  pywaffle  squarify calmap  bs4 urllib3 backtrader 
pip install   cython seaborn snownlp nltk bert word2vec ipywidgets scrapy jieba tushare baostock openpyxl 
pip install   pattern BeautifulSoup4 requests  backtrader seaborn pillow statsmodels keras scikit-Learn  
pip install   bokeh pandas  pymysql autopep8  selenium  pymc3 xgboost lightgbm pymysql sqlalchemy autopep8 
pip install   pyalgotrade pandas-datareader tensorflow redis  visualdl  superset alphalens statsmodels pyecharts 
pip install   jupyterthemes jupyter_contrib_nbextensions catboost sympy better_exceptions  
pip install   tornado django flask django-admin flask-admin
pip install git+https://www.github.com/keras-team/keras-contrib.git
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
