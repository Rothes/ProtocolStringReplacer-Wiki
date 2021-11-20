# 屏蔽 (Blocks)

本页将说明替换配置文件中 `Blocks` 部分的配置项.

```yaml
Replaces: 
  Common:
    - '文本1'
    - '文本2'
  Json:
    - '{"text":"文本1"}'
    - '{"text":"文本2"}'
```

在 `Blocks` 部分中也有两个 String List, 一个为 `Common`, 一个为 `Json`. `Common` 中为的是 PSR 从 Json 中提取出来的子字符串. 我们建议使用 `Json` 替换, 因为其匹配精确度更高, 配合 Equal 匹配模式可以避免一切误处理的情况. 您可以在 [此链接](https://wiki.vg/Chat#Current\_system\_.28JSON\_Chat.29) 中了解有关 Minecraft 的 Chat Json 信息.

{% hint style="info" %}
以下监听类型不支持使用 Json 替换, 因为它们原本就不是 Json:

* ItemStack (除了 Spigot 1.12 及以上版本的书内容, 每一页为一个 Json)
* ScoreBoard (除了 Spigot 1.12 及以上版本的计分板标题)
* Console
{% endhint %}

您可以针对您的需要使用任意模式, 如果您不需要其中的一个模式可以将其设为 _null_ (直接删除) 或者设为空列表 (\[] 或 {}). PSR 会忽略掉此模式的屏蔽.

在 List 中的每一个 String 均为服务器上的文本. PSR 会搜索这些字符串, 如果在一个数据包内匹配到任意一条字符串, 则 PSR 会为用户屏蔽掉这**一整个数据包**, 而不是那一个字符串. 如果您只需要移除一个指定的字符串, 请使用 [替换](Replaces.md) 功能将其替换为空字符串 (`''`). 您必须明确这一机制, 以防止非预期的修改.

此功能会受到 [匹配模式](Options/Match-Mode.md) 的控制. 欲了解更多, 请参阅 [替换流程](../Advanced-Docs/ti-huan-liu-cheng.md).
