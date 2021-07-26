# 资料

| name                       | url                                                          |
| -------------------------- | ------------------------------------------------------------ |
| w3school-Java 开发环境配置 | [link](https://www.w3cschool.cn/java/java-environment-setup.html) |
|                            |                                                              |



# linux安装jdk

## centos安装jdk

- 检索 `yum` 中有没有 `java1.8` 的包 

```shell
yum list java-1.8*
```

- 开始安装

```shell
 yum install java-1.8.0-openjdk* -y
```

- 检查是否安装成功

```shell
java -version
```

- 卸载java

```shell
yum remove java-*
```

# windows安装jdk

**jdk下载**[地址](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html)

## 环境变量配置

### 右击我的电脑–>属性–>高级系统设置–>环境变量：

<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517114144402-822635624.png' width='600px' heigth='400px' title='示例'>

### 设置JAVA_HOME环境变量（java的家：变量指向自己安装jdk的根目录）

<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517115757039-540431936.png' width='600px' heigth='400px' title='示例'>

### ClassPath环境变量

配置***pass***变量`输入命令(注意不要忘记了前面的 .`

```shell
.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar 
```

<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517115028001-1282145423.png' width='600px' heigth='400px' title='示例'>

### 找到系统的path变量（如果没有请自己建立一个path变量）：

**输入命令**

> 命令说明
>
> 1. % 表示引用的意思 **%JAVA_HOME%\bin** 意思是引用jdk下面的bin(主)目录
> 2. % 表示引用的意思 **%JAVA_HOME%\jre\bin** 意思是引用jre下面的bin(主)目录

```
%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;
```
<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517120107121-471997434.png' width='600px' heigth='400px' title='示例'>

<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517120330160-1457725008.png' width='600px' heigth='400px' title='示例'>								

### 检测是否安装成功

打开**cmd** 输入命令`java -version`检测安装是否配置成功

<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517120534391-1284611657.png' width='600px' heigth='400px' title='示例'  >

# Ubuntu安装jdk

## 使用命令安装

```shell
sudo apt install openjdk-8-jdk
```

- 安装完成之后查看是否安装成功

```shell
java -version 
```

## 手动安装

### 手动安装(建议)

> 将Linux版的jdk的安装包配置到环境变量即可,很简单方便
> oracle现在开始收费了,下载jdk8 的时候需要登录,最好下载一个jdk保存着,否则忘记账号很麻烦

- 获取安装包
  - 方法1:从网上找一个jdk8的tar.gz包,上传到Ubuntu
  - 方法2:或者从网上找到下载jdk8的Linux版本的链接,使用 `wget 下载链接`,将jdk下载到当前目录
- 解压安装包到指定位置



```
tar –xvf jdk-xxx.tar.gz –C /usr/local # 位置看个人习惯
```

- 修改配置环境



```
# 打开文件
sudo vim /etc/profile
# 设置环境变量
 JAVA_HOME=/usr/local/jdk解压的文件夹
 CLASSPATH=.:$JAVA_HOME/lib.tools.jar
 PATH=$JAVA_HOME/bin:$PATH
 export JAVA_HOME CLASSPATH PATH
```

- 重新加载`/etc/profile`配置文件



```
sudo source /etc/profile
```

- 查看java版本



```
java -version
```



