---
description: 插件命令列表。
---

# 命令 Command

### 主命令

> 插件主命令

* 名称: `trchat` `trc`
* 权限: `trchat.access`


* **reload**

> 手动重载所有插件配置 权限: `trchat.command.reload`

* **controlPanel**

> 打开玩家控制面板 权限: `trchat.command.controlpanel`

* **chatFilter**

> 打开过滤器界面 权限: `trchat.command.chatFilter`

* ~~mirror~~ (不推荐)

> 查看性能消耗 权限: `trchat.command.mirror`

* **spy**

> 切换监听玩家私聊模式 权限: `trchat.command.spy`

* **vanish**

> 开启后此玩家无法用命令补全, 也无法被@ 权限: `trchat.command.vanish`

* **removemessage**

> 撤回玩家消息 权限: `trchat.command.removemessage`

* **color**

> 选择发送消息颜色 权限: `trchat.command.color`

### 回复

> 回复刚刚向你发送私聊的玩家

* 名称: `reply` `r`
* 权限: `trchat.private`

### 禁言

> 禁止玩家发言

* 名称: 单人:`mute`
* 权限: `trchat.command.mute`
* 参数:
  * `-time <time>`: 禁言时间
  * `-reason <reason>`: 禁言原因
  * `--cancel`: 取消禁言

### 全员禁言

> 禁止全部玩家发言 (除有`trchat.bypass.globalmute`权限的玩家)

* 名称: `muteall` `globalmute`
* 权限: `trchat.command.muteall`

### 频道

> 切换聊天频道

* 名称: `channel` `chatchannel` `trchannel`
* 权限: `trchat.command.channel`

### 屏蔽

> 屏蔽特定玩家聊天

* 名称: `ignore`
* 权限: `trchat.command.ignore`
