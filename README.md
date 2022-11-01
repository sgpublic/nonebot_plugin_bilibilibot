<p align="center">
  <a href="https://v2.nonebot.dev/"><img src="https://v2.nonebot.dev/logo.png" width="200" height="200" alt="nonebot"></a>
</p>

<div align="center">

# nonebot-plugin-bilibilibot

👾 _NoneBot bilibili通知插件_ 👾
<p>version: 2.3.0</p>
    
</div>

# 简介
基于[Nonebot2](https://github.com/nonebot/nonebot2)的bilibili通知插件，可将up主投稿视频,主播开播,番剧的更新以及用户更新动态推送到QQ

**已支持v2.0.0-beta.5**
## 依赖
- 适配器: onebot v11
- [go-cqhttp](https://github.com/Mrs4s/go-cqhttp)
- 插件:
    - [nonebot_plugin_apscheduler](https://pypi.org/project/nonebot-plugin-apscheduler/)

# 特色功能
- 可通过在B站客户端分享用户主页进行关注up主（私聊）

- 可通过在B站客户端分享直播间进行关注主播（私聊）

- 可通过分享番剧播放页面进行关注番剧（私聊）

- 超级用户可对普通用户进行广播

- 将机器人加入群组，向群友及时同时直播或更新消息

# 安装方式
- ` nb plugin install nonebot-plugin-bilibilibot`

# 配置项
配置方式: 请在nonebot的全局配置文件中添加如下配置项。
## SUPERUSERS
- 类型: List[str]
- 说明: 超级用户的列表
> SUPERSUSERS = ["your qq id"]

# 注意事项
- 将机器人加入群组后，只有**管理员\群主\超级管理员**才能对机器人进行操作
- 未避免误触发，群组中不能使用分享链接来关注的功能
- 由于需要同时处理群消息和私聊消息，建议在非调试环境中使用，否则日志将会出现很多的ignore消息
- 如果需要修改公告内容，请修改file/source/announcement.json文件

# 示例
## 获取帮助
![help](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/docs/help2.jpg?raw=true)
## 视频更新推送
![videopush](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/docs/updatepush.jpg?raw=true)
## 番剧更新推送
![videupdate](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/docs/videopush.jpg?raw=true)
## 直播开播推送
![streampuah](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/docs/streampush.jpg?raw=true)
## 动态更新推送
![dynamicpuah](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/docs/dynamic.jpg?raw=true)

## 通过B站客户端分享进行关注
![follow](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/docs/follow.jpg?raw=true)
## 查询关注列表
![list](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/docs/list.jpg?raw=true)


# 更新日志
[完整日志](https://github.com/TDK1969/nonebot_plugin_bilibilibot/blob/main/file/source/ChangeLog.md)
- **ver 2.3.0**
```
1. 增加对动态更新推送的功能
2. 修改了文件目录结构
```

- **ver 2.2.2**
```
1. 解决由于sqlite版本不同导致的bug
2. 解决番剧更新重复推送的问题
```

- **ver 2.2.1**
```
1. 对应用层和数据库层进行解耦
```

- **ver 2.2.0**
```
1. 修改某些B站的接口,减少被接口风控的风险
2. 可以使用ep_id, season_id和media_id对番剧进行关注,需要携带前两个字符
3. 本次更新需要重置数据库,因此会丢失旧版本的关注数据,需要重新关注
```
ep_id: https://www.bilibili.com/bangumi/play/ep433947, 中的**ep433947**

season_id: https://www.bilibili.com/bangumi/play/ss39431, 中的**ss39431**

media_id: https://www.bilibili.com/bangumi/media/md28235123, 中的**md28235123**


- **ver 2.1.0**
```
1. 将文件存储方式修改为数据库,取代原来的JSON文件存储,解决编码或异步的问题
2. 适配Nonebot v2.0.0-beta.5
```


# 特别鸣谢
- 感谢[@0w0w0](https://github.com/a0w0w0)帮助测试
