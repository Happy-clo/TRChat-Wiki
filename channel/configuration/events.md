---
description: 聊天频道的事件——更高级的需求
---

## Process

> 传递`TrChatEvent`后，构建Component前触发

#### 返回值:

- Boolean类型: true发送, false取消（使用动作`exit`可达成同样效果）
- String类型: 更改发送内容为返回值
- 其他类型: 无效果

#### 变量:

- `message`: 玩家发送的消息
- `forward`: 是否实际发送（聊天预览时触发但不发送）

---

## Send

> 发送给每个玩家时，依次触发

#### 返回值:

- Boolean类型: true发送, false取消（使用动作`exit`可达成同样效果）
- 其他类型: 无效果

#### 变量:

- `receiver`: 消息接收者
- `message`: 玩家发送的消息

---

## Join

> 玩家加入时触发

---

## Quit

> 玩家退出时触发