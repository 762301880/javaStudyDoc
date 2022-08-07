# linux安装idea

**参考资料**

| 名称               | 地址                                                       |
| ------------------ | ---------------------------------------------------------- |
| jetbrains-idea下载 | [link](https://www.jetbrains.com/idea/download/other.html) |



## 安装

### **安装jdk**

```shell
# 下载jdk
wget https://repo.huaweicloud.com/java/jdk/8u151-b12/jdk-8u151-linux-x64.tar.gz
# 移动并解压
tar -zxvf jdk-8u151-linux-x64.tar.gz -C /usr/local/
# ------------配置环境变量---------------
# 打开文件
vim /etc/profile
# 设置环境变量-以下全部需要添加到/etc/profile文件夹内
 JAVA_HOME=/usr/local/jdk解压的文件夹       # 例子 /usr/local/jdk1.8.0_151
 PATH=$JAVA_HOME/bin:$PATH
 CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib.tools.jar
 export JAVA_HOME CLASSPATH PATH
```

**重新加载`/etc/profile`配置文件**

> 环境变量修改后执行source命令，使得配置生效

```shell
source /etc/profile
```

## 安装idea

> 请自行从网络上下载安装包解压到喜欢的目录
>
> `IntelliJ IDEA Community Edition`  下载社区版本

```shell
# 下载压缩包
wget https://download.jetbrains.com/idea/ideaIC-2020.3.4.tar.gz?_gl=1*ke1j45*_ga*MjA0OTkwMTM4NS4xNjUzNTcwMDYy*_ga_9J976DJZ68*MTY1OTg0MDcwNC4yLjEuMTY1OTg0MDc3OS4w&_ga=2.161598524.1605099853.1659840745-2049901385.1653570062

# 找到解压目录的bin目录下的idea.sh
idea.sh

# 启动idea
./idea.sh        #我们只需要关注这个shell脚本即可
```

### **设置别名命令启动**

> **>> /dev/null 2>&1 **      表示启动屏蔽输出
>
> &          仔细看最后面单独设置了一个& 表示后台启动不占用当前终端

```shell
yaoliuyang@yaoliuyang-PC:~$ vim .bashrc         # 用户家目录下编辑别名
# 设置命令
alias phpstorm='sh you_idea_save_path/bin/idea.sh >> /dev/null 2>&1 &'

# 刷新添加的别名
source ~/.bashrc
```

**启动idea**

```shell
# 直接终端输入命令phpstorm即可
yaoliuyang@yaoliuyang-PC:~$ idea.sh
[1] 21823
```

### **创建桌面图标启动**

**参考资料**

| 名称     | 地址                                                         |
| -------- | ------------------------------------------------------------ |
| 网络博客 | [link](https://blog.csdn.net/wfk2975019671/article/details/107641756?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-107641756-blog-82495099.pc_relevant_multi_platform_whitelistv1_exp2&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-107641756-blog-82495099.pc_relevant_multi_platform_whitelistv1_exp2&utm_relevant_index=1) |

**示例**

> **Exec**执行的shell脚本地址
>
> **Icon** 指向图标地址

```shell
[Desktop Entry]
Type=Application
Version=2020.3
GenericName=Idea2020
Name=idea
Comment=phpstorm ide
Exec="/you_idea_save_path/bin/idea.sh/bin/phpstorm.sh"
Icon=/you_idea_save_path/bin/idea.sh/bin/phpstorm.svg
Terminal=false
Categories=Development;IDE;
StartupNotify=true
```

