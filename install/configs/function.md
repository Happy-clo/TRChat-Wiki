---
description: 插件功能配置文件。
---

# 功能

### function.yml

<pre class="language-yaml"><code class="lang-yaml"># 一般功能
General: 
  # 控制命令模块
  Command-Controller: 
    # 是否启用
    Enabled: true 
    List: 
    # condition->需要的条件(kether)
    # exact->命令是否需要一摸一样
    # cooldown->执行冷却时间(ms)
    # reflect->跳转命令组(用{}传参,用;分隔)
    - 'arasple{exact: true}{condition: perm *trchat.admin}' 
    - 'ver(sion)?(s)?{condition: perm *trchat.admin}' 
    - 'help(s)?{condition: perm *trchat.admin}' 
    - 'shout{cooldown: 3}' 
  # 物品展示
  Item-Show:
    # 是否启用 
    Enabled: true
    # 使用权限
    Permission: 'none'
    # 展示冷却 
    Cooldown: '30s'
    # 是否展示原名
    Origin-Name: false 
    # 如果使用展示物品的时候踢人，设置为true即可
    Compatible: false 
    # 多个触发展示物品格式
    Keys: 
      - "%i%" 
      - "%i" 
      - "%item%" 
      - "%item" 
      - "[i]" 
      - "[item]" 
    # 触发后执行 Kether 动作
    Actions: [ ]
  # 艾特功能模块
  Mention: 
    # 是否启用
    Enabled: true
    # 使用权限
    Permission: 'none'
    # 是否能艾特自己
    Self-Mention: false 
    # 艾特冷却 
    Cooldown: '30s'
    # 是否通知玩家，默认true 
    Notify: true
    # 触发后执行 Kether 动作
    Actions: [ ]
  # 艾特全体玩家
<strong>  Mention-All:
</strong><strong>    # 是否启用
</strong>    Enabled: true
    # 使用权限
    Permission: 'trchat.function.mentionall'
    # 冷却时间
    Cooldown: '5m'
    # 是否通知玩家,默认true
    Notify: true
    Keys:
      - "@all"
      - "@everyone"
      - "@everybody"
      - "@所有人"
      - "@全体成员"
    # 触发后执行kether动作
    Actions: [ ]
  # 展示玩家自己的背包
  Inventory-Show:
    # 是否启用 
    Enabled: true
    # 使用权限
    Permission: 'none'
    # 展示冷却 
    Cooldown: '30s' 
    # 展示背包触发格式
    Keys: 
    - '[inv]'
    - '[inventory]'
  EnderChest-Show:
    # 是否启用 
    Enabled: true
    # 使用权限
    Permission: 'none'
    # 展示冷却 
    Cooldown: '30s'
    # 展示末影箱触发格式
    Keys:
      - '[ender]'
      - '[enderchest]'
    # 触发后执行 Kether 动作
    Actions: [ ]
  # 展示图片
  Image-Show:
    # 是否启用
    Enabled: true
    # 使用权限
    Permission: 'trchat.function.imageshow'
    # 冷却
    Cooldown: '1m'
    # 正则表达式(![描述])(url))
    Key: '!\[([^;]*)\]\(([a-zA-Z]+://[^\s]*)\)'
    Actions: [ ]

# 自定义指定聊天内容格式
Custom:
  # 示例 —— 网站分享
  shareUrl: 
    # 正则,无需修改
    pattern: '((https|http|ftp|rtsp|mms)?://)[^\s]+' 
    display: 
      # 显示格式内容
      text: '&#x26;8[&#x26;f&#x26;l网站&#x26;8]' 
      # 悬浮框
      hover: 
      - '' 
      - '&#x26;3网站: {0}' 
      - '' 
      - '&#x26;7点击进入!' 
      - '&#x26;8[&#x26;c!&#x26;8] &#x26;7谨防任何诈骗' 
      # 点击后打开的链接,无需修改
      url: '{0}'

# 示例 —— QQ 分享
  shareQQ: 
    condition: ~ 
    priority: 100 
    # 匹配表达式 
    # 示例模块的表达式部分来自互联网 
    pattern: 'QQ( )?1-9' 
    # 变量 {0} 是按下方表达式提取后的内容, 可以不配置此项 
    text-filter: '1-9' 
    # 自定义显示 JSON 组件 
    display: 
      text: '&#x26;8[&#x26;3&#x26;lQQ&#x26;8]' 
      hover: 
      - '' 
      - '&#x26;3QQ: &#x26;b{0}' 
      - '' 
      - '&#x26;7这是一个 QQ 账号,' 
      - '&#x26;7你可以点击此项快速打开聊天' 
      - '' 
      - '&#x26;8[&#x26;c!&#x26;8] &#x26;7请勿进行任何金钱交易' 
      - '&#x26;8[&#x26;c!&#x26;8] &#x26;7交友需谨慎' 
      url: 'https://wpa.qq.com/msgrd?v=3&#x26;uin{0}&#x26;site=qq&#x26;menu=yes'

# 示例 —— B站视频 分享
  shareBilibili: 
    pattern: 'BV( )?.{10}' 
    text-filter: '.{12}' 
    # 自定义显示 JSON 组件 
    display: 
      text: '&#x26;8[&#x26;f&#x26;lBilibili&#x26;8]' 
      hover: 
      - '' 
      - '&#x26;7这可能是一个 Bilibili 视频,' 
      - '&#x26;7点击即可访问' 
      - '' 
      - '&#x26;3BV号: &#x26;b{0}' 
      url: 'https://www.bilibili.com/video/BV{0}'

# 示例 —— 防止玩家暴露、分享真实手机号
  hidePhoneNumber: 
    pattern: '((13[0-9])|(14[0-9])|(15[0-9])|(17[0-9])|(18[0-9]))\d{8}' 
    display: 
      text: '&#x26;8[&#x26;c&#x26;m-&#x26;8]' 
      hover: 
      - '&#x26;7该内容疑似为手机号码,' 
      - '&#x26;7已自动屏蔽隐藏.' 
      - '' 
      - '&#x26;8[&#x26;c!&#x26;8] &#x26;7请勿分享任何隐私信息'

# 示例 —— 隐藏身份证
  hideIDCardNumber: 
    pattern: '([1-9]\d{5}[12]\d{3}(0[1-9]|1[012])(0[1-9]|[12][0-9]|3[01])\d{3}[0-9xX])' 
    display: 
      text: '&#x26;8[&#x26;c&#x26;m-&#x26;8]' 
      hover: 
      - '&#x26;7该内容疑似为身份证号,' 
      - '&#x26;7已自动屏蔽隐藏.' 
      - '' 
      - '&#x26;8[&#x26;c!&#x26;8] &#x26;7请勿分享任何隐私信息' 
      - '&#x26;7严重者可能处于禁言/封禁'

# 示例 —— 高亮 IP
  glowIP: 
    pattern: '(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d).(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d).(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d).(25[0-5]|2[0-4]\d|[0-1]\d{2}|[1-9]?\d)' 
    display: 
      text: '&#x26;e&#x26;n{0}' 
      hover: 
      - '&#x26;7这是一个 IP地址' 
      - '&#x26;7点击复制!' 
      copy: '{0}'

  # 示例 —— 高亮邮箱
  glowEmail: 
    pattern: '\w[-\w.+]*@([A-Za-z0-9][-A-Za-z0-9]+.)+[A-Za-z]{2,14}' 
    display: 
      text: '&#x26;e&#x26;n{0}' 
      hover: 
      - '&#x26;7这是一个邮箱' 
      - '&#x26;7点击复制!' 
      copy: '{0}'
</code></pre>
