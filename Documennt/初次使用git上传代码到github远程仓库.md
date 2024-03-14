## **一、新建代码库**

注册好github登录后，首先先在网页上新建代码库。

点击右上角“＋”→New repository

![img](https://pic4.zhimg.com/80/v2-450469f26e45cded35c80e6bf9ad6493_1440w.webp)

进入如下页面：按照要求填写完成后，点击按钮创建代码库创建成功。

![img](https://pic1.zhimg.com/80/v2-37213db5a58c565860c7ce85a3b67580_1440w.webp)

接下来我们查看一下刚刚创建好的代码库，点击右上角的头像→Settings→左侧菜单栏Repositories菜单，可查看到刚刚新建好的代码库。

![img](https://pic2.zhimg.com/80/v2-767f301cbd1280687761696639451ec9_1440w.webp)

## **二、添加SSH公钥**

为了把本地的仓库传到github，还需要配置ssh key，说白了就是为了把本地的代码上传到github。

### **1、前置准备**

本地需要安装git：[https://git-scm.com/download/](https://link.zhihu.com/?target=https%3A//git-scm.com/download/)。

安装完成以后从桌面或开始菜单打开Git工具{点击Git bash 打开}，下图。

![img](https://pic4.zhimg.com/80/v2-72ca23c1a9dbf3c99f405b7105800097_1440w.webp)

### **2、Git基本信息设置**

在git命令行内输入以下代码：引号内的填写你注册github时的用户名和电子邮件。

```text
git config --global user.name "your name"

git config --global user.email "your_email@163.com"
```

### **3、添加SSH Key**

首先在本地创建ssh key。在刚刚新建好的文件夹内点击右键Git Bash Here进入git命令行。

```text
ssh-keygen -t rsa -C "your_email@163.com"
```

“your_email@163.com”改成自己注册github时的邮箱，此处不一定要用163邮箱。

回车之后会要求确认路径和输入密码，直接一路回车就行。

成功的话会在~/下生成.ssh文件夹，进去打开id_rsa.pub，复制里面的key。

```text
cat ~/.ssh/id_rsa.pub
```

直接在命令行内输入上面的代码，就会出现key，右键复制key。

![img](https://pic2.zhimg.com/80/v2-e5ed8dcfd9b6f7f6016de9a297826675_1440w.webp)

从ssh-rsa开始，复制好后回到网页，点击右上角的setting，左侧菜单切换到SSH and GPG keys，点击New SSH key。默认是没有SSH key的，下方的my_key是我之前添加的。

![img](https://pic4.zhimg.com/80/v2-9e738c533c069640bd3f1f7d317e5853_1440w.webp)

点击New SSH key后，会出现如下页面：

![img](https://pic4.zhimg.com/80/v2-dcfbf21b48d540d7aba624244d32deaf_1440w.webp)

为了验证是否成功，在git bash下输入：ssh -T git@github.com

如果是第一次的会提示是否continue，输入yes就会看到：

You’ve successfully authenticated, but GitHub does not provide shell access。

这就表示已成功连上github了。

## **三、把本地仓库传到github**

初次使用首先需要做一些初始化的工作。

### **1、建立本地仓库并初始化**

在本地电脑的一个盘里面新建一个文件夹，然后在文件夹上点击 右键---Git bash here，下图所示：

![img](https://pic4.zhimg.com/80/v2-473bdbb62d47d48ee59838c2dbb5ed0f_1440w.webp)

## **2、初始化仓库**

在Git命令窗口输入：

```text
git init
```

## **3、**建立本地与github上新建项目连接

找到github上新建项目的地址链接

![img](https://pic3.zhimg.com/80/v2-963ed301bcc3ed2ff45e4204bcdcd8de_1440w.webp)

在Git上输入以下命令建立本地与github上新建项目连接：

```text
git remote add origin git@github.com:fang-king/Selenium.git
```

git remote add origin 固定，后面的内容是复制github上新建项目的ssh网址。

## **4、同步github新建项目到本地**

使用以下命令

```text
git pull origin master
```

## **5、添加本地文件到缓存区**

将需要上传的代码或文件拷贝到新建文件夹里。

在Git里输入以下代码回车

```text
git add .
```

注意add与“.”之间有一个空格。

## **6、为上传文件添加注释**

等待缓存完毕，输入命令：

```text
git commit -m "first push"
```

其中的first push为注释的内容，请自定义填写。

## **7、提交本地文件到github新建项目中**

等待上步完成，继续输入执行命令：

```text
git push origin master
```

## **四、后续上传代码步骤**

- git init 将文件夹设置为本地仓库，只有这样才可以把本地的文件传入github仓库
- git remote add origin [git@github.com](mailto:git@github.com):fang-king/Selenium.git 将本地仓库与github仓库进行关联
- git pull origin master 将GitHub上仓库的内容pull到本地仓库，两者保持一致
- git add 需要上传的文件 添加文件到本地库
- git commit -m “*****” 提交文件到本地库
- git push origin master 上传文件

如果要上传的文件是在一个新的文件夹里，那么就需要执行前3步，将新文件夹作为本地仓库与github关联；

如果要上传的文件是在之前的文件夹里，那么之前已经关联过了，只需要直接执行后3步就可以了。

## **五、删除远程仓库里的文件**

进入本地仓库：

- git pull origin master 本地同步远程仓库，将远程仓库里的内容拉下来
- git rm -r --cached 文件名 删除文件
- git commit -m “delete dir” 提交并添加说明
- git push origin master 将本次更改更新到github项目上去

## 六、**遇到的问题**

可能遇到以下问题：

## **1、将github上的代码库克隆到本地的时候遇到报错**

原因是没有输入yes，由于之前一直一路回车，就以为克隆的时候也是一直回车即可，然后就报错了。

![img](https://pic1.zhimg.com/80/v2-59fc5faefc40ade20813b9ba7e5b9524_1440w.webp)

![img](https://pic3.zhimg.com/80/v2-d2b246d5bc535a4cf785ee6a666f2f1a_1440w.webp)

在add一个文件的时候总是出现如下警告，看着会不舒服。在命令行使用git config --global core.autocrlf false来禁用自动转换 ，就不会出现下方的警告了。

![img](https://pic3.zhimg.com/80/v2-ab6402eca451fc6aa67a7e85d25d418a_1440w.webp)

连接远程仓库
**git remote add origin 仓库地址**

查看[远程连接](https://so.csdn.net/so/search?q=远程连接&spm=1001.2101.3001.7020)
**git remote -v**

git取消与远程仓库的连接
**git remote remove origin**