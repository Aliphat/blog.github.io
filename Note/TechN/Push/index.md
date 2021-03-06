# 推送到手机能力

## 需要搭建的推送

### 1. [WePush_Gitee](https://gitee.com/zhoubochina/WePush)：专注批量推送的小而美的工具

[WePush_Github](https://github.com/rememberber/WePush)

> 1. 支持自定义消息内容并批量推送
> 2. 支持变量消息（可实现根据发送目标用户不同每条消息内容不一样）
> 3. 支持消息编辑、预览、消息管理
> 4. 支持通过文件导入用户（txt、csv、excel）
> 5. 支持通过MySQL导入用户
> 6. 支持微信公众号全员推送
> 7. 支持微信全家桶消息（公众号、小程序、企业号）
> 8. 支持各种粒度的定时推送
> 9. 支持推送历史管理和失败重新推送
> 10. 支持多账号管理和切换（微信）
> 11. 支持各种搜索、导入、导出
> 12. 小而美的可视化界面，支持亮暗多种外观风格
> 13. 支持全局字体字号设置
> 14. 支持推送结果邮件通知

### 2.[Wecom酱](https://github.com/easychen/wecomchan)

> - [Server酱Turbo](https://sct.ftqq.com/)：支持企业微信、微信服务号、钉钉、飞书群机器人等多通道的在线服务，无需搭建直接使用，每天有免费额度
> - [Wecom酱](https://github.com/easychen/wecomchan)：通过企业微信推送消息到微信的消息推送函数和在线服务方案，开源免费，可自己搭建。支持多语言。
> - [PushDeer](https://github.com/easychen/pushdeer)：可自行搭建的、无需安装APP的开源推送方案。同时也提供安装APP的降级方案给低版本/没有快应用的系统。支持作为Server酱的通道进行推送，所有支持Server酱的软件和插件都能直接整合PushDeer。

## 直接使用的推送

### 1.[方糖推送Server酱](https://sct.ftqq.com/)

> 「Server酱」，英文名「ServerChan」，是一款「手机」和「服务器」、「智能设备」之间的通信软件。
>
> 说人话？就是从服务器、路由器等设备上推消息到手机的工具。

### 2.[推加送](http://pushplus.plus/)

> 1. pushplus(推送加)是集成了微信、企业微信、钉钉、短信、邮件等渠道的信息推送平台
> 2. 只需要调用一个简单的API接口，即可帮助你迅速完成消息推送，使用简单方便
> 3. 我们的所做的一切只是为了让推送变的更简单

### 3.[WxPusher微信推送服务](https://wxpusher.zjiecode.com/docs/)

> **WxPusher** (微信推送服务)是一个使用微信公众号作为通道的，实时信息推送平台，你可以通过调用API的方式，把信息推送到微信上，无需安装额外的软件，即可做到信息实时通知。 你可以使用**WxPusher**来做服务器报警通知、抢课通知、抢票通知，信息更新提示等。

### 4.[安然小站Python推送接口](https://www.htm.fun/archives/python-flask-api-server-jiang.html)

[说明书地址](https://www.52pojie.cn/thread-1338005-1-1.html)

##### 卡片推送接口

> https://api.htm.fun/api/Wechat/text_card/?corpid=ww8397e3a2622743c1&corpsecret=aUXKe1SpiiN_kXH_8TLoN6ijarRy3LVB_Dz7wSfgQJg&agentid=1000002&title=title&description=%E6%8F%8F%E8%BF%B0&url=https://www.htm.fun/

##### 文本推送接口

> https://api.htm.fun/api/Wechat/text/?corpid=ww8397e3a2622743c1&corpsecret=aUXKe1SpiiN_kXH_8TLoN6ijarRy3LVB_Dz7wSfgQJg&agentid=1000002&text=123



### 5.[QQ推送](https://qmsg.zendee.cn/)

> 接口简单易用、即刻上手
> 使用QQ作为消息推送平台、全程免注册



### 6.[SmsForwarder-短信转发器](https://github.com/pppscn/SmsForwarder)

> 短信转发器——不仅只转发短信，备用机必备神器！
>
> 监控Android手机短信、来电、APP通知，并根据指定规则转发到其他手机：钉钉机器人、企业微信群机器人、飞书机器人、企业微信应用消息、邮箱、bark、webhook、Telegram机器人、Server酱、PushPlus、手机短信等。
>
> 包括主动控制服务端与客户端，让你轻松远程发短信、查短信、查通话、查话簿、查电量等。（V3.0 新增）

![img](index.assets/68747470733a2f2f696d616765732e67697465652e636f6d2f75706c6f6164732f696d616765732f323032322f303132362f3133333931365f63613936353435325f31363237332e706e67.png)

## 其他

[JavaServer酱简单实现什么值得买优惠信息推送到微信模版消息](https://www.52pojie.cn/thread-1327110-1-3.html)

