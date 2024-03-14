# anaconda配置虚拟环境

### 一. 使用 cmd 创建[虚拟环境](https://so.csdn.net/so/search?q=虚拟环境&spm=1001.2101.3001.7020)

#### 1. 创建虚拟环境

- 最简单的创建 python 虚拟环境的命令是：

  ```python
  conda create -n your_env_name  
  ```

- 我在这里创建一个名为：test 的 python 虚拟环境

  ```python
  conda create -n test   
  ```

- 输入命令后，你需要输入一个 y 。输入完成后，一个 python 虚拟环境就创建好了。

- 注意

  - 在我们创建新的虚拟环境的时候，我们最好指定 python 版本

  - 假如想指定 python 版本为 3.6 ，我们可以输入命令：

    ```python
    conda create -n test python=3.6
    ```

    这是虚拟环境的 python 版本就为 3.6 了。

#### 2. 查看虚拟环境

- 有时候我们需要查看我们的虚拟环境，我们可以看 cmd 里面输入：

  ```python
  conda env list
  ```

  就可以查看所有的 python 虚拟环境了。

#### 3. 激活虚拟环境

- 如果你想要使用你所创建的 python 虚拟环境，首先你就要激活你想用的虚拟环境

- 激活虚拟环境的命令是：

  ```python
  conda activate your_env_name
  ```

  

- 比如我想激活我刚才创建的 test 命令，我只要使用

  ```python
  conda activate test
  ```

  命令就可以了.

- 可以看到，在我们激活虚拟环境之后，在 cmd 的前面会显示所激活虚拟环境的名称。

![](C:\Users\sharon\Desktop\20200402195214511.png)

#### 4. 为虚拟环境安装包

- 可以看到，在新建虚拟环境后，一个包都没有。那怎么去安装包呢？
- 这里我提供两种方法：

(1) 激活了虚拟环境

- 如果我们激活了虚拟环境，我们使用 pip install xxx 或 conda install xxx ，就可以安装包了。
- 假如我们想安装 numpy 包，直接输入：conda install numpy
- 安装完成之后，我们就可以看到 numpy 包以及其他的依赖包了。

(2) 未激活虚拟环境

- 如果未激活虚拟环境，我们就要使用：
  `python conda install -n your_env_name [package]`
- 如果想安装 numpy 库，输入：conda install -n test numpy

#### 5. 退出以及删除虚拟环境

- 删除当前虚拟环境的命令是：

  ```python
  conda deactivate
  ```

- 删除虚拟环境的命令是：

  ```python
  conda remove -n  your_env_name --all
  ```

- 如果我们想要删除刚创建的 test 虚拟环境，只需要输入：

  ```python
  conda remove -n test --all
  ```

- 关于更多的 conda 创建虚拟环境的命令，可以通过命令：

  ```python
  conda create -h
  ```

### 二. 使用 Anaconda 客户端创建虚拟环境

- 使用 anaconda 客户端来操作虚拟环境很方便，只需要我们点击几下鼠标就可以了。

#### 1. 创建 Python 虚拟环境

- 使用 Anaconda 客户端创建 python 虚拟环境，我们只要打开 anaconda 客户端，然后点击 **Environment** ，再点击 **Create** ，填写相应的东西，然后点击 **Create** 就可以了。

### 2. 安装包

- 在 anaconda 里面安装包，我们首先要选择虚拟环境，然后点击 **Not installed**，然后搜索想安装的包，最后点击 **Apply** 就可以了。

#### 3. 激活虚拟环境

- 想要激活虚拟环境，我们只要点击选择的虚拟环境的 **停止符号** ，然后点击 **Open Terminal** 就可以了。

#### 4. 删除虚拟环境

- 想要删除创建的虚拟环境，我们只要先选择想要的删除的虚拟环境，然后点击 **Remove** 就可以了。

### 三. 使用 cmd修改虚拟环境python版本

#### 1.使用python -V命令查看当前[虚拟环境](https://so.csdn.net/so/search?q=虚拟环境&spm=1001.2101.3001.7020)的python版本：

```undefined
python -V
```

#### 2.使用命令：

```
conda install python=3.8
```

可知python版本已经变为3.8。

#### 3.如果在conda install python=3.8中遇到问题

 则可以先使用：

```
conda uninstall python
```

 当当前版本python进行卸载，然后再使用conda install python=3.8安装即可。

### 四.Anaconda查看、创建、切换虚拟环境

#### 1、查看已有[虚拟环境](https://so.csdn.net/so/search?q=虚拟环境&spm=1001.2101.3001.7020)

```python
# 在命令行输入以下命令
conda info --envs
```

这里的base,带星号的，代表基层或者当前虚拟环境，[paddle](https://so.csdn.net/so/search?q=paddle&spm=1001.2101.3001.7020)是我新建的一个虚拟环境。

#### 2、创建新的虚拟环境

```python
# 在命令行输入如下命令
conda create --name newName python=3.7
```

这个意思就是，创建一个新的名为“newName”的虚拟环境，同时使用的python版本为3.7

```python
# 激活新建的虚拟环境
activate newName
```

#### 3、切换虚拟环境（非常重要）

当你的本地创建了多个虚拟环境之后，加之又在不同的虚拟环境中安装了不同的第三方package，这样一来，虚拟环境的切换就很重要了。否则，当你再次打开jupyter notebook，通过import命令试图导入某个package的时候，总是会得到如期的错误**Cannot import module. “No module named …”**解决步骤如下：

```python
# 查看已有的虚拟环境，选择你要切换到的虚拟环境
conda info --envs
# 或者
conda env list
```

```python
# 在命令行中切换到想要的虚拟环境，我这里切换到paddle
conda activate paddle
```

```python
# 在当前的paddle环境中安装好ipykernel
conda install ipykernel
```

```python
python -m ipykernel install --name paddle
```

再次打开jupyter，新建notebook,如图：可以看到，paddle环境出现在了jupyter里面，哈哈哈。