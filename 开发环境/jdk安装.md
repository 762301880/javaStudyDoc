# 资料

| name                       | url                                                          |
| -------------------------- | ------------------------------------------------------------ |
| w3school-Java 开发环境配置 | [link](https://www.w3cschool.cn/java/java-environment-setup.html) |
| linux手动安装-第三方博客   | [link](https://www.zhihu.com/tardis/sogou/art/35064156)      |

# linux-[jdk手动安装](https://www.cnblogs.com/samcn/archive/2011/03/16/1986248.html)

**查询java是否安装**

## [下载openjdk](https://jdk.java.net/)

点击进入[oracle](https://developer.oracle.com/java/)官网,选择导航栏的Downloads,再选择**[OpenJDK](https://jdk.java.net/)**

```shell
#点击数字8
Reference implementations: Java SE 17, 16, 15, 14, 13, 12, 11, 10, 9, 8, & 7     
```

<img src="https://i.loli.net/2021/11/18/bDoCT5pi6AhUQRm.png" alt="1637196245(1).jpg" style="zoom:50%;" />

```shell
wget https://download.java.net/openjdk/jdk8u41/ri/openjdk-8u41-b04-linux-x64-14_jan_2020.tar.gz
# 位置看个人习惯
tar -zxvf openjdk-8u41-b04-linux-x64-14_jan_2020.tar.gz -C /usr/local/
```

## 配置环境变量

> **变量详解**
>
> JAVA_HOME：指明JDK安装路径，此路径下包括lib，bin，jre等文件夹（tomcat等服务运行都需要依赖此变量)
>
> CLASSPATH：为java加载类(class or lib)路径，只有类在classpath中，java命令才能识别。
>
> PATH使得系统可以在任何路径下识别java命令，设为：JAVA HOME/bin:PATH
>
> **其他详解**
>
> linux下用冒号“:”来分隔路径
>
> $PATH / $CLASSPATH / $JAVA_HOME 是用来引用原来的环境变量的值
> 在设置环境变量时特别要注意不能把原来的值给覆盖掉了，这是一种
> 常见的错误。
>
> CLASSPATH中当前目录“.”不能丢,把当前目录丢掉也是常见的错误。
> export是把这三个变量导出为全局变量。
>
> 大小写必须严格区分。

```shell
# 打开文件
 vim /etc/profile
# 设置环境变量-以下全部需要添加到/etc/profile文件夹内
 JAVA_HOME=/usr/local/jdk解压的文件夹
 PATH=$JAVA_HOME/bin:$PATH
 CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib.tools.jar
 export JAVA_HOME CLASSPATH PATH
```

**重新加载`/etc/profile`配置文件**

> 环境变量修改后执行source命令，使得配置生效

```shell
source /etc/profile
```

**查看java版本**

```shell
[root@101fe8e80378 ~]# java -version
openjdk version "1.8.0_41"
OpenJDK Runtime Environment (build 1.8.0_41-b04)
OpenJDK 64-Bit Server VM (build 25.40-b25, mixed mode)

```



# linux命令安装jdk

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

## Ubuntu安装jdk

```shell
sudo apt install openjdk-8-jdk
```

- 安装完成之后查看是否安装成功

```shell
java -version 
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

