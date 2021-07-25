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

```
%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;
```
<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517120107121-471997434.png' width='600px' heigth='400px' title='示例'>

<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517120330160-1457725008.png' width='600px' heigth='400px' title='示例'>

### 检测是否安装成功

打开**cmd** 输入命令`java -version`检测安装是否配置成功

<img src='https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/1922055-20200517120534391-1284611657.png' width='600px' heigth='400px' title='示例'  >

