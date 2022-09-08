---
description: 插件开发者文档。
---

# API 使用

### 聊天监听
```java
public class Demo implements Listener {
    
    @EventHandler
    private void e(TrChatEvent e) {
        e.getChannel(); // 获取聊天频道
        e.getSession(); // 获取聊天会话
        e.setMessage("..."); // 改变聊天内容
        e.setCanceled(true); // 取消发送聊天
    }   
}
```
### TrchatAPI.kt
```kotlin 
interface TrChatAPI {

    fun getComponentManager(): ComponentManager

    fun getProxyManager(): ProxyManager

    fun getChannelManager(): ChannelManager

    fun getFilterManager(): FilterManager

    /**
     * 执行Kether脚本 (命名空间为trchat, trmenu, trhologram)
     */
    fun eval(sender: ProxyCommandSender, script: String, vararg vars: Pair<String, Any?>): CompletableFuture<Any?>

    /**
     * 执行Kether脚本 (命名空间为trchat, trmenu, trhologram)
     */
    fun eval(sender: ProxyCommandSender, script: List<String>, vararg vars: Pair<String, Any?>): CompletableFuture<Any?>

}
```
获取实例: 
```kotlin
TrChat.api()
```