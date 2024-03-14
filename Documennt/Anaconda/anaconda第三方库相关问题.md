# anaconda第三方库相关问题

# 在anaconda中使用pip安装第三方库

作为一个刚入门不久的新手，以前比较依赖pycharm中直接安装第三方镜像源库。但是最近使用anaconda配置虚拟环境之后，这一招就不灵了。
由于anaconda中我需要的的很多库文件找不到，所以找到了这个方法来配置环境，需要者自提。

第一步 打开anaconda prompt，此时所在环境为base，如果需要切换环境，输入
```
activate name 
```

切换到你需要配置的环境下，`name`换成自己需要配置的环境名字，例如我需要配置的环境名字叫[pytorch](https://so.csdn.net/so/search?q=pytorch&spm=1001.2101.3001.7020)，则

```
activate pytorch
```

**第二步** 安装自己需要的库
输入自己需要安装的库，如我需要安装torchvision，则

```
pip3 install torchvision 
```

**ps**：如果安装失败，或者安装完成后在Jupyter中无法运行，则考虑pip版本问题或者直接卸载后重装

```
python -m pip install --upgrade pip -i https://pypi.douban.com/simple
```

# Anaconda以及Pip配置清华镜像源

## 一、Conda配置清华镜像源

### 1. 查看镜像源

```python
conda config --show channels
```

### 2. 删除添加源，恢复默认源

```python
conda config --remove-key channels
```

### 3. 添加清华镜像源

```python
#添加镜像源
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2

#终端显示包从哪个channel下载，以及下载地址是什么
conda config --set show_channel_urls yes
```

## 二、Pip配置清华镜像源

### 1. 临时使用清华镜像源

代码如下（示例）：

```python
# some-package代表你需要安装的包
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
```

下面这种方式也是一样的

```python
pip install some-package -i https://pypi.tuna.tsinghua.edu.cn/simple
```

### 2.永久配置

代码如下（示例）：

```python
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

## 三、国内常用的镜像源

```python
pip install -i https://mirrors.aliyun.com/pypi/simple/ some-package

清华大学开源软件镜像站：https://pypi.tuna.tsinghua.edu.cn/simple
阿里云开源镜像站：https://mirrors.aliyun.com/pypi/simple/
豆瓣：https://pypi.douban.com/simple/
中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
```

## 四.查看安装的所有的该虚拟环境的库

```
conda list
```



