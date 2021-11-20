# 替换 (Replaces)

本页将说明替换配置文件中 `Replaces` 部分的配置项.

```yaml
Replaces: 
  Common:
    - Original: '原文本1'
      Replacement: '新文本1'
    - Original: '原文本2'
      Replacement: '新文本2'
  Json:
    - Original: '{"text":"原文本1"}'
      Replacement: '{"text":"新文本1"}'
    - Original: '{"text":"原文本2"}'
      Replacement: '{"text":"新文本2"}'
```

在 `Replaces` 部分中有两个 Object List, 一个为 `Common`, 一个为 `Json`. `Common` 中替换的是 PSR 从 Json 中提取出来的子字符串, 并且 PSR 会在所有替换都完成后将其重新放入 Json 中. 然而 `Common` 只能够修改字符串, 不能更改格式, 所以我们建议使用 `Json` 替换, 此模式不仅可以修改格式, 而且替换精确度更高, 配合 Equal 匹配模式可以避免一切误处理的情况. 您可以在 [此链接](https://wiki.vg/Chat#Current\_system\_.28JSON\_Chat.29) 中了解有关 Minecraft 的 Chat Json 信息.

{% hint style="info" %}
以下监听类型不支持使用 Json 替换, 因为它们原本就不是 Json:

* ItemStack (除了 Spigot 1.12 及以上版本的书内容, 每一页为一个 Json)
* ScoreBoard (除了 Spigot 1.12 及以上版本的计分板标题)
* Console
{% endhint %}

您可以针对您的需要使用任意模式, 如果您不需要其中的一个模式可以将其设为 _null_ (直接删除) 或者设为空列表 (\[] 或 {}). PSR 会忽略掉此模式的替换.

在 List 中的每一个 Object 都必须包含两个键: `Original` 和 `Replacement`, 并且每个键需对应一个字符串. `Original` 对应原字符串, `Replacement` 对应替换后的新字符串. PSR 会在每一个字符串中搜索 `Original` 中的字符串, 并用与其相对应的 `Replacement` 来替换.

简单点说, `Original` 代表服务器上的文本, `Replacement` 为客户端上将显示的文本.

此功能会受到 [匹配模式](Options/Match-Mode.md) 的控制. 欲了解更多, 请参阅 [替换流程](../Advanced-Docs/ti-huan-liu-cheng.md).
