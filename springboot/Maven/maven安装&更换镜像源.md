# 资料&说明

## 说明

> maven(麦文)是 Apache 下的一个纯 Java 开发的开源项目。基于项目对象模型（缩写：POM）概念，Maven利用一个中央信息片断能管理一个项目的构建、报告和文档等步骤。
>
> Maven 是一个项目管理工具，可以对 Java 项目进行构建、依赖管理。
>
> Maven 也可被用于构建和管理各种项目，例如 C#，Ruby，Scala 和其他语言编写的项目。Maven 曾是 Jakarta 项目的子项目，现为由 Apache 软件基金会主持的独立 Apache 项目。

## 资料

| name                  | url                                                          |
| --------------------- | ------------------------------------------------------------ |
| maven官方地址         | [link](https://maven.apache.org/download.cgi)                |
| 菜鸟教程maven使用手册 | [link](https://www.runoob.com/maven/maven-tutorial.html)     |
| 阿里云开源镜像站      | [link](https://developer.aliyun.com/mirror/?spm=a2c6h.13651104.0.d1002.67f936a42n8Ond) |



# 安装

## windows 安装maven

### 下载压缩包

- 请在[官网](https://maven.apache.org/download.cgi)下载

![img](https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/750D721E-0624-4C16-AD4B-9EA5D7F6289A.png)

- 下载完成之后解压

|  系统   | 存储位置 (可根据自己情况配置) |
| :-----: | :---------------------------- |
| Windows | E:\Maven\apache-maven-3.3.9   |

### 配置环境变量

`右键-此电脑-属性-高级系统设置-环境变量`

- 在系统配置中配置MAVEN_HOME

```shell
# 变量名 MAVEN_HOME
# 变量值 项目路径
```



![image-20210719175048756](https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/image-20210719175048756.png)

- 编辑系统变量 **Path**，添加变量值：;%MAVEN_HOME%\bin

![image-20210719175253487](https://yaoliuyang-blog-images.oss-cn-beijing.aliyuncs.com/blogImages/image-20210719175253487.png)

### 测试是否安装成功

```shell
# mvn -v 命令查看是否输出对应的版本号
C:\Users\Administrator>mvn -v
Apache Maven 3.8.1 (05c21c65bdfed0f71a2f2ada8b84da59348c4c5d)
Maven home: E:\Maven\apache-maven-3.8.1\bin\..
Java version: 1.8.0_112, vendor: Oracle Corporation, runtime: D:\Program Files\Java\jdk1.8.0_112\jre
Default locale: zh_CN, platform encoding: GBK
OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"
```

##  linux安装maven

### 下载.tar.gz压缩文件

```shell
wget https://downloads.apache.org/maven/maven-3/3.8.1/binaries/apache-maven-3.8.1-bin.tar.gz
```

- 解压下载的压缩文件

```shell
 tar -zxvf apache-maven-3.8.1-bin.tar.gz
 # 移动解压的文件
 sudo mv -f apache-maven-3.8.1 /usr/local/
```

### 编辑 **/etc/profile** 

> 文件 **sudo vim /etc/profile**，在文件末尾添加如下代码：

```
export MAVEN_HOME=/usr/local/apache-maven-3.3.9
export PATH=${PATH}:${MAVEN_HOME}/bin
```

保存文件，并运行如下命令使环境变量生效：

```shell 
source /etc/profile
```

在控制台输入如下命令，如果能看到 Maven 相关版本信息，则说明 Maven 已经安装成功：

```shell
#mvn -v
```

# 更换maven镜像源

请在[阿里云官方镜像站](https://developer.aliyun.com/mirror/?spm=a2c6h.13651104.0.d1002.67f936a42n8Ond)找到[maven](https://developer.aliyun.com/mirror/maven?spm=a2c6h.13651102.0.0.74681b119zSMk3)

## 修改镜像源

- 找到`E:\Maven\apache-maven-3.8.1\conf\settings.xml`并打开

> 打开 Maven 的配置文件(windows机器一般在maven安装目录的conf/settings.xml)，在`<mirrors></mirrors>`标签中添加 mirror 子节点:

```xml
<mirror>
    <id>aliyunmaven</id>
    <mirrorOf>*</mirrorOf>
    <name>阿里云公共仓库</name>
    <url>https://maven.aliyun.com/repository/public</url>
</mirror>
```

