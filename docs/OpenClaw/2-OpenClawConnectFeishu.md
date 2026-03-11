---
sidebar_position: 3
---
# OpenClaw对接飞书

- 参考资料：[https://docs.openclaw.ai/zh-CN/channels/feishu](https://docs.openclaw.ai/zh-CN/channels/feishu)


## 1.创建飞书机器人

### 1.1 访问飞书开发平台

访问飞书开发平台：[https://open.feishu.cn/app](https://open.feishu.cn/app)，登入飞书平台。

### 1.2 创建应用

![image-20260310153352072](images/image-20260310153352072.png)

选择创建企业自建应用。

![image-20260310153525228](images/image-20260310153525228.png)

1. 填写应用名称（可自定义，如OpenClaw龙虾）
2. 应用描述（可自定义）
3. 应用图标可自定义。
4. 填写完成后，选择创建

![image-20260310153733472](images/image-20260310153733472.png)

### 1.3 获取应用凭证

选择`凭证与基础信息`。

![image-20260310153835109](images/image-20260310153835109.png)

复制应用凭证`App ID`和`App Secret`，后面我们会用到这两个。

### 1.4 添加应用能力

选择`添加应用能力`

![image-20260310155026535](images/image-20260310155026535.png)

在`按能力添加`下，添加机器人。添加成功后可以看到机器人能力界面。

![image-20260310155146735](images/image-20260310155146735.png)

### 1.5 配置应用权限

选择`权限管理`，点击`批量导入\导出权限`。

![image-20260310155321558](images/image-20260310155321558.png)

点击 **批量导入** 按钮后，粘贴以下 JSON 配置一键导入所需权限：

```
{
  "scopes": {
    "tenant": [
      "aily:file:read",
      "aily:file:write",
      "application:application.app_message_stats.overview:readonly",
      "application:application:self_manage",
      "application:bot.menu:write",
      "cardkit:card:write",
      "contact:user.employee_id:readonly",
      "corehr:file:download",
      "docs:document.content:read",
      "event:ip_list",
      "im:chat",
      "im:chat.access_event.bot_p2p_chat:read",
      "im:chat.members:bot_access",
      "im:message",
      "im:message.group_at_msg:readonly",
      "im:message.group_msg",
      "im:message.p2p_msg:readonly",
      "im:message:readonly",
      "im:message:send_as_bot",
      "im:resource",
      "sheets:spreadsheet",
      "wiki:wiki:readonly"
    ],
    "user": ["aily:file:read", "aily:file:write", "im:chat.access_event.bot_p2p_chat:read"]
  }
}
```

填入完成后，点击`下一步，确认新增权限`。

![image-20260310155524152](images/image-20260310155524152.png)

在确认导入权限界面下，选择**申请开通**。

![image-20260310155601124](images/image-20260310155601124.png)

点击**确认**。

![image-20260310155646173](images/image-20260310155646173.png)

### 1.6 启用机器人能力

在 **应用能力** > **机器人** 页面，选择**如何开始使用**后的按钮。

![image-20260310155844969](images/image-20260310155844969.png)

在这里可以填写机器人对用户展示的名称。

![image-20260310160228134](images/image-20260310160228134.png)

（可选）自定义菜单界面

![image-20260310172838969](images/image-20260310172838969.png)

（可选）调整菜单状态

![image-20260310172855371](images/image-20260310172855371.png)



（可选）选择展示形式和菜单配置，可以自定义菜单界面。

![image-20260310173324338](images/image-20260310173324338.png)

（可选）自定义完成后点击**保存**。

![image-20260310173338602](images/image-20260310173338602.png)



### 1.7 创建版本并发布

选择上方的`创建版本`。

![image-20260310160837527](images/image-20260310160837527.png)

填写版本号`1.0.0`，填写更新说明(可自定义)。

![image-20260310161116401](images/image-20260310161116401.png)

最后选择**保存**。

![image-20260310161220775](images/image-20260310161220775.png)

选择`确认发布`。

![image-20260310161257678](images/image-20260310161257678.png)

发布成功结果如下：

![image-20260310161326576](images/image-20260310161326576.png)

## 2.OpenClaw接入

### 2.1 访问终端

打开终端，按下`Crtl`+`ALT`+`T`快捷键，或者也可以通过SSH的方式访问终端：

![image-20260310164206072](images/image-20260310164206072.png)

### 2.2 配置飞书会话通道

运行以下命令：

```
openclaw channels add
```

运行结果如下：

![image-20260310164257482](images/image-20260310164257482.png)

选择`yes`，按下回车键。

![image-20260310164332631](images/image-20260310164332631.png)

安装`FeiShu/Lark`飞书插件。

![image-20260310165141960](images/image-20260310165141960.png)

选择第一个，使用通过npm下载来获取安装。

### 2.3 配置应用凭证

飞书插件安装成功后，接下来就可以配置应用凭证。

![image-20260310170120767](images/image-20260310170120767.png)

选择`Enter App Secrrt`。接下来就可以填入`App Secret`，填写完成后按下回车键。

![image-20260310170326391](images/image-20260310170326391.png)

继续填写`App ID`，填写完成后按下回车键。

![image-20260310170408257](images/image-20260310170408257.png)

### 2.4 设置连接方式

设置**webSocket**的连接方式。

![image-20260310170621876](images/image-20260310170621876.png)

选择**WebSocket**，选择完成后，按下回车键。

![image-20260310170742743](images/image-20260310170742743.png)

根据您的地区选择域名，这里我选择**中国**。

### 2.5 群聊策略

![image-20260310170848798](images/image-20260310170848798.png)

为了响应所有群聊，选择**Open**。

最后会回到菜单选择界面。

![image-20260310171051244](images/image-20260310171051244.png)

使用方向键向下，找到**Finished**，选择完成。

### 2.6 私信访问策略

**DM access policies（私信访问策略）** 是控制谁可以通过私信（Direct Message）与你的 AI Agent 交互的安全机制。

![image-20260310171305672](images/image-20260310171305672.png)

我们选择`NO`，这样就可以在陌生人发送消息时会收到一个6位配对码，必须经你手动批准后才能交互。

### 2.7 添加显示名称

![image-20260310171425005](images/image-20260310171425005.png)

当 OpenClaw 检测到配置文件中的某些账号缺少 `displayName` 字段时，会给出这个建议。这是非严重警告，我们选择**NO**。

### 2.8 AI Agent实例关联

![image-20260310171639651](images/image-20260310171639651.png)

这里是询问是否立即将已配置的渠道账号绑定到 Agent？我们选择**Yes**。



### 2.9 分发Agent

![image-20260310171738742](images/image-20260310171738742.png)

将飞书（Feishu/Lark）账号的消息路由到默认 Agent，直接按下回车即可。



## 3.飞书机器人配置

### 3.1 添加配置

在飞书开发平台中， **事件订阅** 页面，选择订阅方式。

![image-20260310173801675](images/image-20260310173801675.png)

点击订阅方式后的按钮。

![image-20260310173925819](images/image-20260310173925819.png)

选择**使用长连接接收事件**后点击保存。

![image-20260310174034016](images/image-20260310174034016.png)

点击**添加事件**。搜索并添加以下事件：

- im.message.receive_v1- 接收消息
- im.message.message_read_v1- 消息已读回执
- im.chat.member.bot.added_v1- 机器人进群
- im.chat.member.bot.deleted_v1- 机器人被移出群

![image-20260310174534086](images/image-20260310174534086.png)

添加成功后，可看到如下界面：

![image-20260310174603397](images/image-20260310174603397.png)

添加成功即可，正常给OpenClaw发送信息。

重新发布版本

### 3.2 重新发布版本

选择上方的`创建版本`。

![image-20260310160837527](images/image-20260310160837527.png)

填写版本号`1.0.0`，填写更新说明(可自定义)。

![image-20260310161116401](images/image-20260310161116401.png)

最后选择**保存**。

![image-20260310161220775](images/image-20260310161220775.png)

选择`确认发布`。

![image-20260310161257678](images/image-20260310161257678.png)

发布成功结果如下：

![image-20260310161326576](images/image-20260310161326576.png)



## 3.启动与测试

### 3.1 查看通道

打开OpenClaw浏览器界面，选择**Channel**，可以看到下方Feishu已经在Running。

![image-20260310172207663](images/image-20260310172207663.png)

### 3.2 使用飞书测试

下载[飞书客户端](https://www.feishu.cn/download)或者使用手机APP均可以，打开APP后我们可以看到开发小助手的消息，当我们发布应用成功后，会提示我们。

![image-20260310174819656](images/image-20260310174819656.png)

点击**开发小助手**，在这个界面里我们可以打开创建的**OpenClaw龙虾**应用。

![image-20260310175055137](images/image-20260310175055137.png)

打开后可以看到OpenClaw的聊天框。

![image-20260310175140402](images/image-20260310175140402.png)

可以发送任意文本，等待OpenClaw的回复，会回复我们的用户ID和配对码，我们需要使用Pairing code后的**配对码**进行验证。



回到OpenClaw端侧，打开命令行界面，我们需要批准配对码，输入以下内容：

```
openclaw pairing approve feishu <配对码>
```

运行效果如下：

![image-20260310175541139](images/image-20260310175541139.png)

![image-20260310175547669](images/image-20260310175547669.png)

配对完成后，重新回到飞书客户端。

![image-20260310175655226](images/image-20260310175655226.png)

接下来重新发送文本，就可以看到OpenClaw的回复了，接下来你的养虾之旅就此开始啦！
