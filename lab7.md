# 南昌大学实验报告
---


姓名：__刘泽迪__
	
学号：____6130116201____

邮箱地址：__zediliu@outlook.com__

专业班级：__计算机166__

实验日期：__2019-5-10__
    
课程名称：__云计算技术实验__
 
## 实验项目名称
 Hadoop and MapReduce

## 实验目的
- Understanding the concept of MapReduce Model 
-  Building a file system in a distributed way that store large data trunks 
-  Merging all things together into a docker image 
-  Writing some sample demo on running MapReduce models

## 实验基础
- Os: Window10
- Tool：Vmware pro15
- Os on tool: Ubuntu 18.04.1
- cpu ：8th i5 2核
- 内存 ： 3G
- Docker: Version 18.09.5

## 实验步骤
### 1. 自己制作hadoop镜像
主要的思路  
(1) 先使用Docker构建一个Hadoop运行环境的镜像        
(2) 然后使用这个镜像分别启动3个容器：1个Master节点，两个Slave节点       
(3) 在Master节点上配置Slave节点信息         
(4) 在Master上启动Hadoop            

#### 1. 使用Docker构建一个Hadoop运行环境的镜像        
1.  从Docker hub上拉取Ubuntu镜像到本地
```
docker pull ubuntu
```
2. 在个人文件下创建一个目录，用于向Docker内部的Ubuntu系统传输文件
```
cd ~
mkdir build
```
3. 在Docker上运行Ubuntu系统
```
docker run -it -v /home/hadoop/build:/root/build --name ubuntu ubuntu
```
4. Ubuntu系统初始化
- 更新系统
```
apt-get update
```
- 安装vim
```
apt-get install vim
```
- 安装sshd
```
apt-get install ssh
```
- 把启动sshd服务器
```
/etc/init.d/ssh start
```
- 把启动命令写进~/.bashrc文件
```
vim ~/.bashrc
```
最后一行添加如下内容        

    /etc/init.d/ssh start
- 配置sshd  
安装好sshd之后，我们需要配置ssh无密码连接本地sshd服务，如下命令:
```
ssh-keygen -t rsa #一直按回车键即可
cat id_dsa.pub >> authorized_keys
```
- 安装JDK 
```
apt-get install default-jdk
```
- 我们需要配置环境变量，打开~/.bashrc文件，在最后输入如下内容
```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/
export PATH=$PATH:$JAVA_HOME/bin
```
- 执行如下命令使~/.bashrc生效
```
source ~/.bashrc
```

## 实验数据或结果



## 实验思考



## 参考资料



