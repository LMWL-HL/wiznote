### Jupyter Notebook安装及配置

#### 官网下载miniconda安装包
```
https://docs.conda.io/en/latest/miniconda.html
```

安装命令
```
bash Miniconda3-latest-Linux-x86_65.sh
```

安装时，我选择的目录是（username改成自己的用户名，下同）：
```
/home/username/.miniconda3
```

安装完成后：
```
cd /home/username/.miniconda3/bin/
```

```
bash conda-env create
```

环境设置（我是用的zsh，所以是.zshrc。如果没有用zsh，而是原生bash，则是.bashrc，下同）：
```
vim ~/.zshrc
```

添加如下一行：
```
export PATH="/home/username/.miniconda3/bin:$PATH"
```

然后：
```
source ~/.zshrc
```

#### 解决EnvironmentLocationNotFound报错

安装nb_conda之后，运行jupyter notebook点conda导航栏时报错：
```
EnvironmentLocationNotFound:Not a conda environment:/home/username/.miniconda3/envs/.miniconda3
```

##### 解决办法

在conda的安装目录（我的是`/home/username/.miniconda/`）下的`pkgs/nb_conda-2.2.1-python37_0/lib/python3.7/sitepackages/nb_conda/envmanager.py`
将下面代码
```
for env in info['envs']]
```

改成
```
for env in info['envs'] if env != info['root_prefix']]
```


#### 参考链接
[Erroneous Environments Showing up in Conda Nb tab with error](https://github.com/Anaconda-Platform/nb_conda/issues/66)

[linux 安装Anaconda](https://www.jianshu.com/p/03d757283339)