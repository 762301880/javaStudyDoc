# 讲解





# 安装

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

