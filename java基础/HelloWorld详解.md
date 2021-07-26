#  说明

> 平时我们编写代码第一句写的就是helloword输出语句表示我们来了,
>
> java中的helloworld我们今天来深究一下，java文件运行的时候会首先
>
> 进行编译成**.class**文件，然后在交给我们的虚拟机**jvm**执行

# HelloWorld

## 1.随便新建一个文件夹，存放代码

## 2.新建一个java文件。文件后缀名为，javaHello.java

> 【注意点】系统可能没有显示文件后缀名，我们需要手动打开

## 3.编写代码

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("HelloWorld");  //控制台数据语句
    }
}
```

## 4.编译javac java文件，会生成一个class文件!

> 请在此电脑项目的地址栏中之前加入cmd
>
> 例子 cmd E:\javaProject\JavaDemo\src
>
> 或则直接win+R 输入cmd 然后cd 切换到项目目录

- cmd编译java文件

  ```java
  javac HelloWorld.java //此命令会在同级目录下编译生成HelloWorld.class文件
  ```

  

## 5.运行class文件，java

```java
java HelloWorld //直接执行编译的HelloWorld.class 这里忽略后缀

E:\javaProject\JavaDemo\src>javac HelloWorld.java

E:\javaProject\JavaDemo\src>java HelloWorld
HelloWorld    
```



