## pycharm生成Python项目所需要的依赖库/包文档：requirements.txt

平时我们在编写或者使用别人的Python项目时，往往会看到一个文档requirements.txt，该文档是描述一个Python项目中的第三方库的名称以及版本。本文介绍导出python当前项目依赖包requirements.txt的操作步骤。

方法一：如果每个项目有对应的虚拟环境，那么使用pycharm的终端里，在当前项目下，直接实现使用命令
```pip freeze > requirements.txt 
pip freeze > requirements.txt 
```

可以看到项目目录下生成了requirements.txt，内容如下：

![](https://img-blog.csdnimg.cn/direct/2ab31d1bc7944da4b2b7c780288e05d3.png)

每一行是依赖库的名称和版本号。注意：如果在python项目全局环境里直接使用 pip freeze > requirements.txt 会导出大量与该项目无关的依赖，包括很多个包信息，其实这里是把你当前 python 环境的所有包的相关信息导出来了。

例如：上图中pycharm使用的是conda环境，所以会生成环境中所有的依赖。

如果你也使用的是conda环境，那么请使用方法二生成requirements.txt

方法二：如果我们只需导出当前项目所需的依赖包，还可以采用另外一种方式，使用工具：pipreqs

安装pipreqs：
```
pip install pipreqs
```

安装完毕如下图所示：

![](https://img-blog.csdnimg.cn/direct/58122be94aaf4d2a9d5b50b46554b41d.png)

我是在conda环境下安装，如果你使用pycharm的虚拟环境，可以直接在方法一中展示的终端中安装。

然后在项目的根目录下输入命令：

```
pipreqs ./

```

如果出现上图所示的编码错误UnicodeDecodeError，则将指定编码为utf8：

```
pipreqs ./ --encoding=utf8
```

完成后如下图所示：

![](https://img-blog.csdnimg.cn/direct/50c0fc74ab6f411aaa7e40856aef415b.png)

并且会在项目根目录下生成requirments.txt。

一般情况下是不会生成上图中的警告的，这里我这个项目的PIL库有两个应用版本，所以出现上面的警告。

requirements.txt中：

![](https://img-blog.csdnimg.cn/direct/85237b3b6e5c4e6fb54abfa86c941d87.png)

这种方式获得的依赖文档requirements.txt仅包含项目所需要的依赖，而没有其他无关依赖。

这样，当该项目迁移到其他地方，需要安装依赖时，使用

```
pip install -r requirements.txt
```

或用镜像更快地安装

```
pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple/
```

即可安装项目所需的依赖。

PS：其实任何项目也可以运行后看报错，缺什么库就安装什么库，直到跑通。但是，可能会有库版本不兼容的问题。所以，当你在使用其他人的源码时，如果项目源码中有requirments.txt，则还是按照该文档安装。更何况，当你用pycharm打开一个陌生的项目时，会提示你按requirment.txt安装。

