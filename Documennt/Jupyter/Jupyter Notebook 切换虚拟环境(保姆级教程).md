# Jupyter Notebook 切换虚拟环境(保姆级教程)

### **具体流程：**

1. 查看当前jupyter notebook的环境：

   

   从上面可看出当前jupyter只有一个python 3的环境。

2. 在cmd中切换至想要添加的环境：(这里要切换到环境目录下)

```
conda activate env_name
```

3. 在当前的环境中安装好[ipykernel](https://so.csdn.net/so/search?q=ipykernel&spm=1001.2101.3001.7020):

```
conda install ipykernel
```

4. 输入以下代码添加当前环境至jupyter notebook:

```
python -m ipykernel install --name env_name
```

5. 重启jupyter notebook即可看见新增的环境:

 这样就完成了，以后就可以在jupyter notebook中自由切换环境了！

## 1、前言

在使用Anconda时，为了满足不同Python环境、深度学习框架的需要，需要安装大量的环境。在Jupyter中配置并切换不同环境是个令人头疼的问题。本教程参考个人经验以及不同博客，适用于Jupyter Lab/ Jupyter Notebook。

## 2、安装

### 2.1 安装ipykernel

**必须进入Base环境安装**，因为Anaconda的默认环境安装了Jupyter Notebook(版本高的也安装了Jupyter Lab)

```text
conda install jupyter ipykernel
```

### 2.2 创建新的conda环境

创建并激活要使用Jupyter的环境，如果已经创建好了就直接激活环境即可。本文以tensorflow-gpu 2.4安装为例。

```text
conda create -n tfgpu2.4 python=3.7
```

创建好后激活环境

```text
conda activate tfgpu2.4
```

安装tensorflow-gpu 2.4

```text
conda install tensorflow-gpu==2.4
```

### 2.3 在新环境中安装kernel

```text
conda install ipykernel
```

## 3、配置

### 3.1 将conda环境写入jupyter的kernel中

--name 环境名称

--display-name 在jupyter notebook看到的别名

```text
python -m ipykernel install --user  --name tfgpu2.4 --display-name "tensorflow-gpu2.4"
```

## 4、使用

### 4.1 激活jupyter

**必须进入Base环境启动jupyter notebook!**

**必须进入Base环境启动jupyter notebook!**

**必须进入Base环境启动jupyter notebook!**

重要的事说三遍，然后激活jupyter。

- Jupyter Notebook激活方式：

```text
conda activate base
jupyter notebook
```

- Jupyter Lab激活方式：

```text
conda activate base
jupyter lab
```

### 4.2 jupyter中切换不同环境

- Jupyter Notebook：

在Jupyter Notebook界面上方的kernel---->change kernel中选择即可。或者新建文件的时候直接选择不同版本的环境

- Jupyter Lab

在Jupyter Lab界面右上方点击内核，然后选择环境。或者新建文件的时候直接选择不同版本的环境。

### 4.3 查看jupyter中的环境内核

```text
jupyter kernelspec list
```

### 4.4 删除jupyter notebook中的环境内核

<env-name> 环境名称

```text
jupyter kernelspec remove <env-name>
```

例：

```text
jupyter kernelspec remove tfgpu2.4
```