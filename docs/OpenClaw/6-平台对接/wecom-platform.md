---
sidebar_position: 1
---

# 接入企业微信机器人

- 参考资料：https://work.weixin.qq.com/nl/index/openclaw



## 1.创建智能机器人

打开[企业微信](https://work.weixin.qq.com/)，找到工作台中的智能机器人。

![image-20260312153736032](./images/image-20260312153736032.png)



选择**创建机器人**

![image-20260312153814378](./images/image-20260312153814378.png)

选择**手动创建**。

![image-20260312153943455](./images/image-20260312153943455.png)

往下找到**API模型创建**。

![image-20260312154013591](./images/image-20260312154013591.png)

选择连接方式为：**使用长连接**，并**点击获取Secret**。

![image-20260312154157697](./images/image-20260312154157697.png)

请记住获取的Bot ID和Secret，后续我们会使用到。

![image-20260312154409876](./images/image-20260312154409876.png)

最后可修改机器人名称完成后，点击保存。

![image-20260312154608707](./images/image-20260312154608707.png)

保存完成后可以看到如下界面。

![image-20260312154748272](./images/image-20260312154748272.png)



## 2.OpenClaw配置

1.在本地搜索打开终端，输入以下命令，安装企微插件。

```
openclaw plugins install @wecom/wecom-openclaw-plugin
```

![image-20260312154959048](./images/image-20260312154959048.png)

2.重启OpenClaw

```
openclaw gateway restart
```

![image-20260312155110589](./images/image-20260312155110589.png)



3.添加企业微信通道

```
openclaw channels add
```

![image-20260312155206668](./images/image-20260312155206668.png)

选择**Yes**，现在配置聊天通道。

![image-20260312155239343](./images/image-20260312155239343.png)

使用方向键选择**企业微信(WeCom)**，选择完成后按下回车键。

![image-20260312155433076](./images/image-20260312155433076.png)

填入刚刚再创建智能机器人的Bot ID。

![image-20260312155620379](./images/image-20260312155620379.png)

填入刚刚再创建智能机器人的Secret。

![image-20260312155659226](./images/image-20260312155659226.png)

最后选择**Finished**。

![image-20260312155739343](./images/image-20260312155739343.png)

选择**No**,使用Pairing的方式，即配对码的方式。

![image-20260312155815619](./images/image-20260312155815619.png)

选择**No**。



## 3.测试

在智能机器人界面，点击 **去使用**。

![image-20260312160016340](./images/image-20260312160016340.png)

点击**发信息**：

![image-20260312160114442](./images/image-20260312160114442.png)

发送信息，例如：你好

如果配置成功，OpenClaw会给您回复配对码，即Pairing code后的配对码。

![image-20260312160401526](./images/image-20260312160401526.png)

复制OpenClaw发给您的最后一行，前往OpenClaw执行。这里我复制的是：

```
openclaw pairing approve wecom 3G9LLFHN
```

![image-20260312160528669](./images/image-20260312160528669.png)

再次发送信息，如果配置成功，会收到OpenClaw的回复。

![image-20260312160627156](./images/image-20260312160627156.png)

