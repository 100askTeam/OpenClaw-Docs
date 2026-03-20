---
sidebar_position: 1
---

# OpenClaw快速开始指南

## 硬件要求

### 盒子里包括的内容

当您购买了一套全新的OpenClaw AI主机套件时，包装盒内会有：

1. OpenClaw 龙虾AI主机
2. 一套电源适配器

### 盒子中不包含的内容

您可能需要额外的：

- USB键盘和USB鼠标



## 连接电源启动

1. 按照图1所示，找到OpenClaw AI主机和电源适配器。
2. 按照图2所示，找到OpenClaw AI主机头顶处的TypeC的电源接口。
3. 按照图3所示，将电源适配器的TypeC接口，接入OpenClaw AI主机，电源适配器接到220V家庭电源上。
4. 上电成功后，观察OpenClaw AI主机套件上方的显示屏会显示开机LOGO。

![image-20260316111822204](images/image-20260316111822204.png)





## 第一次启动

系统启动成功后，可以到屏幕显示如下界面：

![image-20260316115517879](images/image-20260316115517879.png)

等待OpenClaw系统启动，启动成功后会弹出OpenClaw Web UI界面。

![image-20260316115805442](images/image-20260316115805442.png)

此时可通过触摸屏点击OpenClaw Web UI界面上的`Overview`查看OpenClaw系统状态。

![image-20260316120327755](images/image-20260316120327755.png)

## 连接外设

由于第一次启动可能需要键盘鼠标控制主机的操作，可以通过主机的USB口连接USB键盘、USB鼠标等外设。

![image-20260316120538353](images/image-20260316120538353.png)

## 系统操作指南

### 访问浏览器

点击左上角的按钮，选择下方的**FireFox**应用，点击打开即可。

![image-20260316144054704](images/image-20260316144054704.png)

可点击**OpenClaw Control**访问OpenClaw Web UI。

![image-20260316144331417](images/image-20260316144331417.png)

如果默认界面不是上图所示，可点击`+`号，重新打开一个标签页。

![image-20260316145205933](images/image-20260316145205933.png)

### 访问命令行终端

点击左上角的按钮，选择下方的**Terminator**应用，点击打开即可。

![image-20260316144526928](images/image-20260316144526928.png)

在这个界面可输入命令，可用于查看OpenClaw运行状况，增加OpenClaw Skills等

![image-20260316144707178](images/image-20260316144707178.png)

### 访问文件资源管理器

点击左上角的按钮，选择下方的**Files**应用，点击打开即可。

![image-20260316144929737](images/image-20260316144929737.png)

在这个页面里可以存放后续需要给OpenClaw处理的文件。

![image-20260316144955693](images/image-20260316144955693.png)

## 后续文档阅读顺序

1. 阅读《网络连接指南》给OpenClaw主机进行网络配置。如果有需要远程程序和文件传输可继续阅读《远程登录指南》和《文件传输指南》
2. 阅读《接入大模型平台API Key》给OpenClaw主机提供使用Token的途径。
3. 阅读《对接飞书机器人》可以通过飞书APP与OpenClaw主机进行对话养虾。
4. 最后《Skill生态》是给OpenClaw增加更多的技能，其中《安装Clawhub》为必做，其他部分Skill可以根据您具体的养虾场景而选择。



## 常见问题

1.无法访问OpenClaw Web UI，启动界面显示 **Unable to conect**。

原因：OpenClaw系统没有完全启动，导致Web UI界面无法显示。

解决办法：

1.点击**Try Again**，尝试重新访问OpenClaw Web UI。如果还是一样可等待一分钟后继续尝试点击。

![image-20260316152221984](images/image-20260316152221984.png)

2.如果多次点击，并且等待了一段时间后，再次点击还是无法正常查看OpenClaw Web UI可重新启动Open Claw系统，访问命令行终端，输入以下内容：

```
openclaw gateway restart
```

![image-20260316152727730](images/image-20260316152727730.png)

重启服务后，再次打开浏览器访问OpenClaw Web UI。

2.OpenClaw盒子的用户密码和root密码
用户名：openclaw
密码：openclaw
root超级用户密码：root


## 【拓展】连接HDMI屏幕

如果想连接拓展屏幕，可使用HDMI线连接拓展屏幕。

![image-20260316142127082](images/image-20260316142127082.png)

注意：默认使用HDMI连接的屏幕为拓展屏幕，主界面openclaw主机上方的显示屏。

当接入HDMI 显示屏后，可看到拓展屏幕上也会显示桌面，如果想设置HDMI界面为主界面，可在系统桌面上点击**右键**，选择**Display Setting**（显示设置）。

![image-20260316143145609](images/image-20260316143145609.png)

下面为显示设置界面，其中**显示屏1**为主机上方小屏幕，**显示屏2**为HDMI拓展屏幕。

![image-20260316143319603](images/image-20260316143319603.png)

点击下方红色箭头处，可选择显示的主屏幕。

![image-20260316143444992](images/image-20260316143444992.png)

选择**屏幕2**，点击`Apply`应用。

![image-20260316143534908](images/image-20260316143534908.png)

选择Keep Changes保存修改即可。

![image-20260316143619495](images/image-20260316143619495.png)

重启系统后，默认的OpenClaw Web UI就会显示在拓展HDMI显示屏上。

![image-20260316143900418](images/image-20260316143900418.png)
