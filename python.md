
## python 环境

### anaconda 清华软件站地址

`https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/`

### conda 国内镜像
```bash
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
conda config --set show_channel_urls yes
```


## pip 国内源
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

### conda 安装模块
```bash
conda update --all keras  pandas numpy scipy  requests  theano  scikit-learn bcolz mysqlclient clang llvm line_profiler  
```

### pip 模块

```bash
pip install paddlepaddle stable_baselines snapshot-phantomjs pyecharts torch
pip install 	gym Ta-lib ta tflearn joypy  pywaffle  squarify calmap  bs4 urllib3 backtrader 
pip install   cython seaborn snownlp nltk bert word2vec ipywidgets scrapy jieba tushare baostock openpyxl 
pip install   pattern BeautifulSoup4 requests  backtrader seaborn pillow statsmodels keras scikit-Learn  
pip install   bokeh pandas  pymysql autopep8  selenium  pymc3 xgboost lightgbm autopep8 yapf
pip install   pyalgotrade pandas-datareader tensorflow redis  visualdl  superset alphalens statsmodels pyecharts 
pip install   jupyterthemes jupyter_contrib_nbextensions catboost sympy better_exceptions  optuna
pip install   tornado django flask django-admin flask-admin 
pip install git+https://www.github.com/keras-team/keras-contrib.git
```

## jupyter notebook 远程设置

1. 产生配置文件
```bash
jupyter notebook --generate-config
```

2. 进入python
```bash
from IPython.lib import passwd
passwd()
```


产生一组加密字符串，拷贝
3. 修改之前产生的文件
```bash
vi ~/.jupyter/jupyter_notebook_config.py
```

```bash
c.NotebookApp.ip='*'
c.NotebookApp.password = u'sha1:fd86831c7f45:ea05b2d77fa19eaec9c2eda3db5a8d8a4303xxxxx'
c.NotebookApp.open_browser = False
c.NotebookApp.port =8000 #随便指定一个端口
c.IPKernelApp.pylab = 'inline'
```
4. 启动
```bash
jupyter notebook --allow-root --no-browser --port=8000
```
  
5. 安装jupyter扩展插件Nbextensions库
`pip install jupyter_contrib_nbextensions`
`jupyter contrib nbextension install --user --skip-running-check`
打开jupyter notebook, 在网页中显示
---->Nbextensions
---->Hinterland //选中它，重启

6. 设置jupyter notebook 主题样式
`pip install --upgrade jupyterthemes`
` jt -t solarizedd -f roboto -nf robotosans -tf robotosans -N -T -cellw 70% -dfs 10 -ofs 10`
`jt -t grade3 -f fira -fs 10 -nf 10`
`jt -t grade3  -f fira -fs 10 -tf robotosans -N -T -cellw 90% `
##如果工具栏被隐藏了，可以这样开启
-N -T显示工具栏

7.图片变清晰
`%config InlineBackend.figure_format = 'retina'`

8.安装R
也许这样一次成功
```bash
conda install r r-essentials 
yum install epel-release
yum install R
```
进入Rstudio，
`install.packages(c('rzmq','repr','IRkernel','IRdisplay'), repos = c('http://irkernel.github.io/', getOption('repos')))`
或者
```tk
install.packages(c('crayon', 'pbdZMQ', 'devtools'))
devtools::install_github(paste0('IRkernel/', c('repr', 'IRdisplay', 'IRkernel')))
IRkernel::installspec(user = FALSE)
```
