# 如何把Excel的数据导入python？

## Python数据分析——excl导入数据的简单方法（xlrd）

本文的初衷是发现网上很多Excel导入Python都没有结合具体Excel文档进行讲解，所以这篇文档将会呈现一个简单快速的Excel+Python的入门方法。

**开发环境**
Prerequisites:
在开始用Python导入Excel之前，要配置好自己的开发环境，最好有IDE（terminal也可）+安装相应的数据分析包。

1. **IDE** ：pycharm，vscode，etc
2. **数据分析包**：**matplotlib**，**xlrd**，numpy，etc

### 导入数据

1.import第三方库

```
import matplotlib.pyplot as plt  #画图用
import numpy as np
import matplotlib
import xlrd  				#读Excel数据用
```

2.找到Excel的路径，举个栗子

```
file_location = "C:\Users\sharon\Desktop\毕业论文\test (version 1).xlsx"
data = xlrd.open_workbook(file_location)
#	data是Excel里的数据
```

3.选择读取哪个sheet

![](C:\Users\sharon\Desktop\使用文档\Python\excel_Example.png)

比如我们读取sheet1的内容：

```
sheet = data.sheet_by_index(0)  
#	根据索引读取
#	就是说data里有很多sheet
#	data.sheet_by_index（0）是sheet1，以此类推
```

4.读个数据玩玩： 用sheet.cell_value（）
举个栗子：

```
print(sheet.cell_value(0,0))  #读最左上角的数据 [0][0]
							  #和C语言的二维数组很类似
print(sheet.nrows)			  #返回row（行）的数目
					
print(sheet.ncols)			  #返回column（列）的数目
```

看看运行结果（Excel是上面的图哦）

```
Cement (component 1)(kg in a m^3 mixture)  # [0][0]元素
1031					# 1031行 （rows）
9						# 9列 （columns）
```

5.为了进行数据处理中，我们会加入一些遍历的语句，使得某个行或者列可以被读在某个数组里。
举个栗子：现在想要某一行的所有值

```
for col in range(sheet.ncols):
    print(sheet.cell_value(0,col))
```

看看输出是什么？（第一行的所有值哦）

```
Cement (component 1)(kg in a m^3 mixture)
Blast Furnace Slag (component 2)(kg in a m^3 mixture)
Fly Ash (component 3)(kg in a m^3 mixture)
Water  (component 4)(kg in a m^3 mixture)
Superplasticizer (component 5)(kg in a m^3 mixture)
Coarse Aggregate  (component 6)(kg in a m^3 mixture)
Fine Aggregate (component 7)(kg in a m^3 mixture)
Age (day)
Concrete compressive strength(MPa, megapascals)
```

再举个栗子：我要第7列的所有值

```
days = [sheet.cell_value(r,7) for r in range(1,sheet.nrows)]
```

再来一个：所有行所有列的值

```
stats = [[sheet.cell_value(r,c) for c in range(sheet.ncols)] for r in range(sheet.nrows)]
```

### OK，到这里就完了，你学会了吗？

再看看代码，知道每行都是什么功能了吗？

```
import matplotlib.pyplot as plt
import numpy as np
import matplotlib
import xlrd

file_location = "F:\desktop\Assignment\Concrete_Data.xls"
data = xlrd.open_workbook(file_location)

sheet = data.sheet_by_index(0)

print(sheet.cell_value(0,0))

print(sheet.nrows)

print(sheet.ncols)

for col in range(sheet.ncols):
    print(sheet.cell_value(0,col))

# for col in range(sheet.ncols):
#     print(sheet.cell_value(2,col))

# data stores all information in the excel
data = [[sheet.cell_value(r,c) for c in range(sheet.ncols)] for r in range(sheet.nrows)]

# print the attribute 'Days' out
# for row in range(1,sheet.nrows):
#     print(data[row][7])

days = [sheet.cell_value(r,7) for r in range(1,sheet.nrows)]
```

