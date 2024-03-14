## 在 Jupyter-Notebook / Jupyter-Lab 中如何运行.py文件

在Jupyter中运行.py 文件有两种方法：

## 1.使用 `%load`:

> %load xx.py

**`%load` 的作用是将 `xx.py` 文件中的所有代码加载到 `.ipynb`文件中（并未运行），如果需要运行加载的代码，需要再次运行该cell。** 其中 xx.py 是你想要运行的python文件，**以 Jupyter-Lab为例**：
假设当前目录下有python文件 `test.py`，代码功能为实现两数相加，内容如下：

![img](https://pic4.zhimg.com/80/v2-e8816a42dc67de3a1a6026b2bdf172d7_1440w.webp)



之后新建`run_py.ipynb`,在cell中添加代码`%load test.py`，然后运行该cell：
运行前：



![img](https://pic2.zhimg.com/80/v2-62294bc4535cfc6b86350097a750bec9_1440w.webp)



运行后：

![img](https://pic3.zhimg.com/80/v2-b65a65d7c96a8ff5849392ee1e075e8e_1440w.webp)

此时`test.py`中的所有代码全部加载到当前cell中，并且自动将`%load test.py`语句注释。**重复一遍，此时cell内的代码还未运行！**
若此时需要运行代码，只需再次运行cell，如下：

![img](https://pic1.zhimg.com/80/v2-6ce927a381ebb4aaadc6634dbc27ac3c_1440w.webp)



## 2.使用`%run`:

> %run test.py
> 与使用`%load`的不同点在于，该方法将在不加载代码到cell的前提下直接运行`test.py`得出结果:

![img](https://pic4.zhimg.com/80/v2-e0d03b7437ae0c4ecff0199ab92ad6c7_1440w.webp)



## 3.对比

直接上截图：



![img](https://pic1.zhimg.com/80/v2-ed94f66a4b332c844cb043d63b68da90_1440w.webp)