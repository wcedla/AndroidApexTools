[中文](README.md) | [English](README_en.md)

# AndroidApexTools

一个帮助解包android的apex包，并支持重新打包成apex的工具

> 项目地址：https://github.com/wcedla/AndroidApexTools

## 功能说明

> <font style="color:red">当前仅支持linux和wsl子系统，测试环境为win10的wsl2的ubuntu 22.04</font>

### 1. 安装python3及依赖项

首先赋予文件夹执行权限

```shell
cd 当前脚本存放位置
chmod -R a+x .
```

然后安装python3

```shell
sudo apt-get update
sudo apt-get install python3
```
再安装python3-pip

```shell
sudo apt-get install python3-pip
```
接着安装protobuf
```shell
pip3 install protobuf==3.17.3
sudo pip3 install protobuf==3.17.3
```

### 2. 解包

```shell
cd 当前脚本存放位置
python3 ./deapexer.py extract ./foo.apex
```

解包后会在当前脚本路径生成manifest和payload两个文件夹，manifest文件夹里面的内容一般不需要修改，payload就是原apex里面img解包后的文件，可以修改

### 3. 打包

```shell
cd 当前脚本存放位置
python3 ./apexer.py --api 33 ./bar.apex
```

确保当前路径存在manifest和payload文件夹，api参数表示这个apex的android api版本，是必填项


> 注意：重新打包后的apex签名和系统签名不一致，需要核心破解