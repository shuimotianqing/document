## 一、tensorflow + [keras](https://so.csdn.net/so/search?q=keras&spm=1001.2101.3001.7020) + python 版本对照

详情看 tensorflow 官网链接如下：

[Build from source on Windows  | TensorFlow (google.cn)](https://tensorflow.google.cn/install/source_windows)

| Framework       | Python version                  | Description                     |
| --------------- | ------------------------------- | ------------------------------- |
| TensorFlow 2.9  | 3.7.-3.10.                      | TensorFlow 2.9.0 + Keras        |
| TensorFlow 2.8  | 3.7.-3.10.                      | TensorFlow 2.8.0 + Keras        |
| TensorFlow 2.7  | 3.7.-3.9.                       | TensorFlow 2.7.0 + Keras        |
| TensorFlow 2.6  | 3.6.-3.9.                       | TensorFlow 2.6.0 + Keras 2.6.0  |
| TensorFlow 2.5  | 3.6.-3.9.                       | TensorFlow 2.5.0 + Keras 2.5    |
| TensorFlow 2.4  | 3.6.-3.8.                       | TensorFlow 2.4.0 + Keras 2.4.3  |
| TensorFlow 2.3  | 3.5.-3.8.                       | TensorFlow 2.3.0 + Keras 2.4.3  |
| TensorFlow 2.2  | 3.7.                            | TensorFlow 2.2.0 + Keras 2.3.1  |
| TensorFlow 2.1  | 3.6.                            | TensorFlow 2.1.0 + Keras 2.3.1  |
| TensorFlow 2.0  | 3.6.                            | TensorFlow 2.0.0 + Keras 2.3.1  |
| TensorFlow 1.15 | 3.6.                            | TensorFlow 1.15.0 + Keras 2.3.1 |
| TensorFlow 1.14 | 3.6.                            | TensorFlow 1.14.0 + Keras 2.2.5 |
| TensorFlow 1.13 | 3.6.                            | TensorFlow 1.13.0 + Keras 2.2.4 |
| TensorFlow 1.12 | 3.6.                            | TensorFlow 1.12.0 + Keras 2.2.4 |
| 2.X             | TensorFlow 1.12.0 + Keras 2.2.4 |                                 |
| TensorFlow 1.11 | 3.6.                            | TensorFlow 1.11.0 + Keras 2.2.4 |
| 2.X             | TensorFlow 1.11.0 + Keras 2.2.4 |                                 |
| TensorFlow 1.10 | 3.6.                            | TensorFlow 1.10.0 + Keras 2.2.0 |
| 2.X             | TensorFlow 1.10.0 + Keras 2.2.0 |                                 |
| TensorFlow 1.9  | 3.6.                            | TensorFlow 1.9.0 + Keras 2.2.0  |
| 2.X             | TensorFlow 1.9.0 + Keras 2.2.0  |                                 |
| TensorFlow 1.8  | 3.6.                            | TensorFlow 1.8.0 + Keras 2.1.6  |
| 2.X             | TensorFlow 1.8.0 + Keras 2.1.6  |                                 |
| TensorFlow 1.7  | 3.6.                            | TensorFlow 1.7.0 + Keras 2.1.6  |
| 2.X             | TensorFlow 1.7.0 + Keras 2.1.6  |                                 |
| TensorFlow 1.5  | 3.6.                            | TensorFlow 1.5.0 + Keras 2.1.6  |
| 2.X             | TensorFlow 1.5.0 + Keras 2.0.8  |                                 |
| TensorFlow 1.4  | 3.6.                            | TensorFlow 1.4.0 + Keras 2.0.8  |
| 2.X             | TensorFlow 1.4.0 + Keras 2.0.8  |                                 |
| TensorFlow 1.3  | 3.6.                            | TensorFlow 1.3.0 + Keras 2.0.6  |
| 2.X             | TensorFlow 1.3.0 + Keras 2.0.6  |                                 |

## 二、tensorflow 和 keras 安装流程

这里安装 **python=3.8，tensorflow=2.4.0，keras=2.4.3****（segnet 是我做的\**语义分割\**项目的虚拟环境）**，若需要将创建的虚拟环境添加到 **jupyter lab/notebook** 中使用，则**需要第 3 - 6 步**，否则不用**：**

```python
# 1. Anaconda 创建虚拟环境
conda create -n segnet python=3.8
# 2. 激活并进入虚拟环境
activate segnet
# 3. 安装 ipykernel 
pip install ipykernel -i https://pypi.tuna.tsinghua.edu.cn/simple/
# 4. 安装ipykernel，将虚拟环境加入 jupyter 内核中
python -m ipykernel install --name segnet --display-name segnet
# 5. 检查新虚拟环境是否成功加入内核
jupyter kernelspec list
# 6. 从指定文件夹里进入 jupyter
jupyter lab
# 7. 安装 tensorflow、keras 等软件包
pip install tensorflow=2.4.0 -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install keras=2.4.3 -i https://pypi.tuna.tsinghua.edu.cn/simple

pip install matplotlib=3.4.3 -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install numpy=1.19.2 -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install pillow=10.2.0 -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install scipy=1.7.3 -i https://pypi.tuna.tsinghua.edu.cn/simple
```