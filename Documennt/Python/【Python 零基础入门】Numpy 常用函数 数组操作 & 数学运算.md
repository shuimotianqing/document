# 【Python 零基础入门】Numpy 常用函数 数组操作 & 数学运算

- [概述](https://blog.csdn.net/weixin_46274168/article/details/134151573#_1)
- [Numpy 数组创建](https://blog.csdn.net/weixin_46274168/article/details/134151573#Numpy__5)
- - [np.asarray](https://blog.csdn.net/weixin_46274168/article/details/134151573#npasarray_7)
  - [np.arange](https://blog.csdn.net/weixin_46274168/article/details/134151573#nparange_40)
  - [np.linspace](https://blog.csdn.net/weixin_46274168/article/details/134151573#nplinspace_74)
- [数组操作](https://blog.csdn.net/weixin_46274168/article/details/134151573#_119)
- - [reshape](https://blog.csdn.net/weixin_46274168/article/details/134151573#reshape_122)
  - [flatten](https://blog.csdn.net/weixin_46274168/article/details/134151573#flatten_164)
  - [concatenate](https://blog.csdn.net/weixin_46274168/article/details/134151573#concatenate_195)
  - [split](https://blog.csdn.net/weixin_46274168/article/details/134151573#split_242)
  - [vstack](https://blog.csdn.net/weixin_46274168/article/details/134151573#vstack_307)
  - [hstack](https://blog.csdn.net/weixin_46274168/article/details/134151573#hstack_343)
- [数学运算](https://blog.csdn.net/weixin_46274168/article/details/134151573#_380)
- - [add 相加](https://blog.csdn.net/weixin_46274168/article/details/134151573#add__381)
  - [subtract 相减](https://blog.csdn.net/weixin_46274168/article/details/134151573#subtract__399)
  - [multiply 相乘](https://blog.csdn.net/weixin_46274168/article/details/134151573#multiply__422)
  - [divide 相除](https://blog.csdn.net/weixin_46274168/article/details/134151573#divide__445)

## Numpy 数组创建

### np.asarray

`np.assarray`可以将输入转换为 ndarray 数组.

格式:

```
import numpy as np

array = np.asarray(a, dtype=None, order=None)
```

参数:

- a: 待转换的数据, 可以为列表, 元组等
- dtype: 数据类型

例子:

```
# 创建数组
list1 = [1, 2, 3]

# 转换为 ndarray
ndarray1 = np.array(list1)
ndarray2 = np.array(list1, dtype=np.float32)

# 调试输出
print(list1)
print(ndarray1)
print(ndarray2)
```

输出结果:

```
[1, 2, 3]
[1 2 3]
[1. 2. 3.]
```

### np.arange

`np.arange`是一个非常实用的函数, 用于创建一系列的值, 类似于 Python 中的`range`内置函数, 但是返回的是一个数组.

格式:

```
import numpy as np

array = np.arange(start, stop, step)
```

参数:

- start: 数组开始值 (含), 默认为 0
- stop: 数组结束值 (不含)
- step: 数组步长

例子:

```
# 0-9
array1 = np.arange(10)
print(array1)

# 1-10
array2 = np.arange(1, 11)
print(array2)

# 1-10 奇数
array3 = np.arange(1, 11, 2)
print(array3)
```

输出结果:

```
[0 1 2 3 4 5 6 7 8 9]
[ 1  2  3  4  5  6  7  8  9 10]
[1 3 5 7 9]
```

### np.linspace

`np.linspace`可以帮助我们创建一个等差数列.

格式:

```
import numpy as np

array = np.linspace(start, stop, num, endpoint)
```

参数:

- start: 数组起始值
- stop: 数组结束值
- num: 生成的眼本书, 默认为 50
- endpoint: 布尔值, 如果为 True, 则 “stop” 是最后一个样本, 否则不包括 “stop”, 默认为 True

例子:

```
# 包括 50
array1 = np.linspace(0, 50)
print(array1)

# 不包括 50
array1 = np.linspace(0, 50, endpoint=False)
print(array1)

# 样本为 10
array1 = np.linspace(5, 50, 10)
print(array1)
```

输出结果:

```
[ 0.          1.02040816  2.04081633  3.06122449  4.08163265  5.10204082
  6.12244898  7.14285714  8.16326531  9.18367347 10.20408163 11.2244898
 12.24489796 13.26530612 14.28571429 15.30612245 16.32653061 17.34693878
 18.36734694 19.3877551  20.40816327 21.42857143 22.44897959 23.46938776
 24.48979592 25.51020408 26.53061224 27.55102041 28.57142857 29.59183673
 30.6122449  31.63265306 32.65306122 33.67346939 34.69387755 35.71428571
 36.73469388 37.75510204 38.7755102  39.79591837 40.81632653 41.83673469
 42.85714286 43.87755102 44.89795918 45.91836735 46.93877551 47.95918367
 48.97959184 50.        ]
[ 0.  1.  2.  3.  4.  5.  6.  7.  8.  9. 10. 11. 12. 13. 14. 15. 16. 17.
 18. 19. 20. 21. 22. 23. 24. 25. 26. 27. 28. 29. 30. 31. 32. 33. 34. 35.
 36. 37. 38. 39. 40. 41. 42. 43. 44. 45. 46. 47. 48. 49.]
[ 5. 10. 15. 20. 25. 30. 35. 40. 45. 50.]
```

## 数组操作

![](C:\Users\sharon\Desktop\使用文档\Python\数组操作示例.png)

### reshape

`reshape`方法用于改变数组形状而不改变其数据.

格式:

```
import numpy as np

reshaped_array = reshape(a, newshape)
```

参数:

- a: 原始数组
- newshape: 新的形状

例子:

```
array = np.arange(6)
reshaped_arrary = array.reshape(2, 3)

# 调试输出
print("原始数组:", array, sep="\n")
print("改变形状后的数组:", reshaped_arrary, sep="\n")

array = np.array([[0, 1, 2], [3, 4, 5]])
reshaped_arrary = array.reshape(-1)

# 调试输出
print("原始数组:", array, sep="\n")
print("改变形状后的数组:", reshaped_arrary, sep="\n")

```

输出结果:

```
原始数组:
[0 1 2 3 4 5]
改变形状后的数组:
[[0 1 2]
 [3 4 5]]
原始数组:
[[0 1 2]
 [3 4 5]]
改变形状后的数组:
[0 1 2 3 4 5]
```

### flatten

`flatten()`可以帮助我们将多维数组降为 1 维数组.

格式:

```
import numpy as np

flattend_array = array.flatten()
```

例子:

```
# 创建原始 ndarray
array = np.array([[0, 1, 2], [3, 4, 5], [7, 8, 9]])

# 降为 1 维
flattened_array = array.flatten()

# 调试输出
print("原始数组:", array, sep="\n")
print("降为 1 维的数组:", flattened_array, sep="\n")
```

输出结果:

```
原始数组:
[[0 1 2]
 [3 4 5]
 [7 8 9]]
降为 1 维的数组:
[0 1 2 3 4 5 7 8 9]
```

### concatenate

`concatenate`可以帮助我们沿着指定轴连接相同形状的两个或多个数组.

格式:

```
import numpy as np

concatenated_array = np.concatenate((a1, a2, ...), axis=0, out=None)
```

格式:

- a1, a2: 需要连接的数组
- axis: 连接轴, 默认为 0, 即纵向拼接, 如果为 1 则横向拼接
- out: 放置结果的可选参数, 默认为 None

例子:

```
# 创建原始数组
array1 = np.array([[1, 2], [3, 4]])
array2 = np.array([[5, 6], [7, 8]])

# 纵向拼接
v_concatenated_array = np.concatenate((array1, array2))  # axis 默认为 0

# 横向拼接
h_concatenated_array = np.concatenate((array1, array2), axis=1)

# 调试输出
print("纵向拼接:", v_concatenated_array, sep="\n")
print("横向拼接:", h_concatenated_array, sep="\n")

```

输出结果:

```
array 1:
[[1 2]
 [3 4]]
array 2:
[[5 6]
 [7 8]]
纵向拼接:
[[1 2]
 [3 4]
 [5 6]
 [7 8]]
横向拼接:
[[1 2 5 6]
 [3 4 7 8]]
```

### split

`split`函数可以帮助我们将一个数组分割为多个子数组.

格式:

```
import numpy as np

splitted_arrays = np.split(array, indices_or_sections, axis=0)
```

参数:

- a: 带分割的数组
- indices_or_sections: 如果是一个整数, 就将该数平均切分, 如果是数组, 为沿轴切分的位置 (左开有闭)
- axis: 沿着哪个维度进行切分, 默认为 0

例子:

```
# # 创建原始数组
array = np.arange(9)

# 分割数组为 3 等分
splitted_arrays = np.split(array, 3)

# 调试暑促
print("原始数组:", array)
print("分割后的数组:", splitted_arrays)

# 创建原始数组
array = np.arange(9)

# 以索引 2, 5 分割数组
splitted_arrays = np.split(array, [2, 5])

# 调试暑促
print("原始数组:", array)
print("分割后的数组:", splitted_arrays)

# 创建原始数组
array = np.arange(9).reshape(3, 3)

# 横向 3 等分
splitted_arrays = np.split(array, 3, axis=1)

# 调试暑促
print("原始数组:", array, sep="\n")
print("分割后的数组:", splitted_arrays, sep="\n")
```

输出结果:

```
原始数组: [0 1 2 3 4 5 6 7 8]
分割后的数组: [array([0, 1, 2]), array([3, 4, 5]), array([6, 7, 8])]
原始数组: [0 1 2 3 4 5 6 7 8]
分割后的数组: [array([0, 1]), array([2, 3, 4]), array([5, 6, 7, 8])]
原始数组:
[[0 1 2]
 [3 4 5]
 [6 7 8]]
分割后的数组:
[array([[0],
       [3],
       [6]]), array([[1],
       [4],
       [7]]), array([[2],
       [5],
       [8]])]
```

### vstack

`vstack`可以帮助我们将数组进行垂直堆叠.

格式:

```
import numpy as np

stacked_array = np.vstack((a1, a2, ...))
```

参数:

- a1, a2: 需要迭代的数组
- 返回: 纵向堆叠的数组

例子:

```
# # 原始数组
array1 = np.array([1, 2, 3])
array2 = np.array([4, 5, 6])

# 纵向堆叠
stacked_array = np.vstack((array1, array2))

# 输出结果
print("array1:", array1)
print("array2:", array2)
print("纵向堆叠数组:", stacked_array, sep="\n")
```

输出结果:

```
array1: [1 2 3]
array2: [4 5 6]
纵向堆叠数组:
[[1 2 3]
 [4 5 6]]
```

### hstack

`hstack`可以帮我们将数组进行水平堆叠.

格式:

```
import numpy as np

stacked_array = np.hstack((a1, a2, ...))
```

参数:

- a1, a2: 需要迭代的数组
- 返回: 横向堆叠的数组

例子:

```
# 原始数组
array1 = np.array([1, 2, 3])
array2 = np.array([4, 5, 6])
array3 = np.array([7, 8, 9])

# 横向堆叠
stacked_array = np.hstack((array1, array2, array3))

# 输出结果
print("array1:", array1)
print("array2:", array2)
print("array3:", array3)
print("横向堆叠数组:", stacked_array, sep="\n")
```

输出结果:

```
array1: [1 2 3]
array2: [4 5 6]
array3: [7 8 9]
横向堆叠数组:
[1 2 3 4 5 6 7 8 9]
```

## 数学运算

### add 相加

相加

例子:

```
# 原始数组
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# 相加
add_result = np.add(a, b)

# 调试输出
print("数组 a:", a)
print("数组 b:", b)
print("相加结果:", add_result)
```

### subtract 相减

相减

例子:

```
# 原始数组
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# 相减
subtract_result = np.subtract(a, b)

# 调试输出
print("数组 a:", a)
print("数组 b:", b)
print("相减结果:", subtract_result)
```

输出结果:

```
数组 a: [1 2 3]
数组 b: [4 5 6]
相减结果: [-3 -3 -3]
```

### multiply 相乘

相乘

例子:

```
# 原始数组
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# 相乘
multiply_result = np.multiply(a, b)

# 调试输出
print("数组 a:", a)
print("数组 b:", b)
print("相乘结果:", multiply_result)
```

输出结果:

```
数组 a: [1 2 3]
数组 b: [4 5 6]
相乘结果: [ 4 10 18]
```

### divide 相除

相除

例子:

```
# 原始数组
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# 相除
divide_result = np.divide(a, b)

# 调试输出
print("数组 a:", a)
print("数组 b:", b)
print("相除结果:", divide_result
```

输出结果:

```
数组 a: [1 2 3]
数组 b: [4 5 6]
相除结果: [0.25 0.4  0.5 ]
```