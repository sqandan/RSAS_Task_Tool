<h1 align="center">RSAS_Task_Tool</h1>

<div align="center">

绿盟极光远程安全评估系统(RSAS)_Python-GUI_批量添加扫描任务、批量下载扫描报告等一系列动作自动化的工具

[![Author](https://img.shields.io/badge/Author-sqandan-green)](https://github.com/sqandan)
[![version](https://img.shields.io/badge/version-1.0-brightgreen)](https://github.com/sqandan/RSAS_Task_Tool)
[![language](https://img.shields.io/badge/language-Python-green)](https://github.com/sqandan/RSAS_Task_Tool)
[![python](https://img.shields.io/badge/python-3.6%20%7C%203.7%20%7C%203.8-blue)](https://github.com/sqandan/RSAS_Task_Tool)
[![GitHub star](https://img.shields.io/github/stars/sqandan/RSAS_Task_Tool)](https://github.com/sqandan/RSAS_Task_Tool)
[![GitHub forks](https://img.shields.io/github/forks/sqandan/RSAS_Task_Tool)](https://github.com/sqandan/RSAS_Task_Tool)
[![GitHub ISSUE](https://img.shields.io/github/issues/sqandan/RSAS_Task_Tool)](https://github.com/sqandan/RSAS_Task_Tool/issues)

</div>

[English](./README.en.md) | 简体中文

## 0x01 简介

Python+pyqt5编写，界面与逻辑分离，采用requests模拟请求的方式实现，非官方数据接口，所有扫描器都能用。

------
#### 功能

* [x] 主机扫描（批量）
* [x] web扫描（批量）
* [ ] 扫描任务管理
* [ ] 扫描报告下载（批量）
------
## 0x02 使用

### 安装Python3依赖：

```
pip3 install -r requirements.txt
```

首次打开软件需配置扫描器地址和端口，并在当前目录生成对应扫描模块资产文件夹（Assets_URL和Assets_Host）

### 运行程序：

```
python3 main.py
```

### 任务界面使用：

#### 扫描任务名称填写：

**资产文件夹下txt文件名需即为扫描任务名称**

可点击`加载目录资产名称`按钮直接从对应资产文件夹下加载要扫描txt文件名，方便批量立即扫描

```code
[任务名称|扫描时间]
任务名称1		#系统名称和设定的扫描时间，只填系统名称是立即扫描
任务名称2|2021-1-1 00:00:00
任务名称3|2021-1-2 10:30:00
```

#### 主机扫描：

Assets_Host文件夹下txt文件名需与任务名称相匹配，txt里的IP地址是一行一个，这样的：

```code
192.168.0.1
192.168.1.1-254
192.168.1.1/24
192.168.1.*
192.168.1-10.*
!10.16.10.1
!10.16.10.2-222
```

> **待优化：如果txt里的ip存在"、"或其他暂未发现会报错字符：`1.1.1.22-23、25-26`，可能会提示找不到任务资产。**

#### WEB扫描：

Assets_URL文件夹下txt文件名需与任务名称相匹配，txt里的url是一行一个，这样的：

```
http://127.0.0.1
http://localhost:8080
https://github.com/
```

因绿盟限制，单次任务扫描目标最多为15个，此程序下任务时会对单个任务扫描目标大于15个进行拆分。

![](https://github.com/sqandan/RSAS_Task_Tool/blob/master/images/Snipaste_002.png)

> **待优化：绿盟在建立任务时会对扫描的每个URL地址进行站点访问测试，不可达的站点使用此程序下载任务时会失败。**

![](https://github.com/sqandan/RSAS_Task_Tool/blob/master/images/Snipaste_001.png)

#### 任务列表：



#### 网页登录：

这里暂时使用了`Selenium`打开浏览器自动填充账号密码登录扫描，`WebDriver驱动`使用了`Microsoft Edge (Chromium)` ，后续可能会改用其他方法。

如果你点击这个按钮报错了，请自行下载本机`Microsoft Edge`版本对应的`WebDriver驱动`并替换此程序目录下的`msedgedriver.exe`

Microsoft Edge（Chromium）的驱动msedgedriver 下载地址：https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/

------
## 0x03 演示

<div align=center><img src="https://github.com/sqandan/RSAS_Task_Tool/blob/master/images/login.png" width = "50%" /></div>

<div align=center><img src="https://github.com/sqandan/RSAS_Task_Tool/blob/master/images/Host_Task.png" width = "70%" /></div>

<div align=center><img src="https://github.com/sqandan/RSAS_Task_Tool/blob/master/images/Web_Task.png" width = "70%" /></div>

------
## 0x04 更新
- 2021/02/23 更新列表：	1、新增Selenium网页自动化登录	2、修复一些小问题	3、发现一些小问题

- 2021/01/29 更新列表：	1、新增WEB扫描	2、新增目录资产读取功能	3、预留任务列表展示功能	4、发现一些小问题

- 2021/01/22 更新列表：	1、重构登录界面和任务界面	

- 2020/12/25	上传RSAS_Task_Tool

------
## 0x05 备注

https://github.com/sqandan/RSAS_Task_Tool

------

------
