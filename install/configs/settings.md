---
description: 插件设置配置文件。
---

# 设置

### settings.yml

```yaml
# 选项
Options:
  # 记录Normal聊天格式到plugins/TrChat/logs目录下
  Log-Normal: '[{0}] {1}: {2}'
  # 记录私聊聊天格式到plugins/TrChat/logs目录下
  Log-Private: '[{0}] {1} -> {2}: {3}'
  # 强制变量扩展
  Depend-Expansions: ['player', 'server', 'vault']
  # 玩家是否可以用tab补全,默认false,true即禁止
  Prevent-Tab-Complete: false
  # 插件依赖(用来处理插件冲突问题)
  ChatEvent-Hooks: ['AmazingBot', 'ChatBubbles', 'PlayMoreSounds', 'QuestCreator']
  # 是否跨服,默认自动(无法跨服则看核心选择最后两个)
  # AUTO, NONE, BUNGEE, VELOCITY
  Proxy: AUTO
  # 1.19一下修改为玩家或者系统信息(个人感觉鸡肋无用)
  # CHAT, SYSTEM
  Send-Message-Method: CHAT


# 数据库
Database:
  # 数据库类型(SQLite,SQL)
  Method: SQLite
  SQLite:
    # 储存数据文件目录
    file: '{plugin_folder}/data/data.db'
    # 数据库表名
    table: trchat
  SQL:
    # 数据库地址
    host: localhost
    # 数据库端口
    port: 3306
    # 数据库用户名
    user: root
    # 数据库密码
    password: root
    # 数据库名
    database: trchat
    # 数据库表名
    table: trchat

# 多bc工具(可以跨bc同步聊天信息和数据,目前只能聊天信息)
Redis:
  # 开关
  enabled: false
  # 将数据发送到指定频道
  channel: ''
  # 接收指定频道的数据
  subscribe: []
  # ip地址
  host: localhost
  # 端口
  port: 6379
  # 密码
  auth: ~
  # 连接时长(s)
  connect: 32
  # 连接超时(ms)
  timeout: 1000

# 聊天功能
Chat:
  # 内容相似度
  Anti-Repeat: 0.75
  # 聊天间隔冷却
  Cooldown: '2s'
  # 最大聊天长度
  Length-Limit: 100

# 开启颜色转换
Color:
  # 聊天颜色
  Chat: false
  # 牌子颜色
  Sign: false
  # 铁砧颜色
  Anvil: false
  # 书本颜色
  Book: false

# 默认频道
Channel:
  Default: 'Normal'
```
