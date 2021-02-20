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
c.NotebookApp.password = u'sha1:fd86831c7f45:ea05b2d77fa19eaec9c2eda3db5a8d8a4303c09'
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
