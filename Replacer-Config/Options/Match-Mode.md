# 匹配模式 (Match-Mode)

```yaml
Options:
  Match-Mode: 'Contain' # String
```

此设定项 `Match-Mode` 用于控制此替换配置文件的匹配模式. 可选值为:

* `Contain` - 替换字符串中任何原字符串匹配的部分.
* `Equal` - 只在字符串与设定的原字符串完全相同时替换.
* `Regex` - 使用 Java 提供的正则表达式功能.

该设定项对替换效率影响较大, 有关更多信息请参阅 [替换效率](../../Advanced-Docs/ti-huan-xiao-shuai.md).

欲了解更多, 请参阅 [替换流程](../../Advanced-Docs/ti-huan-liu-cheng.md).

### 包含匹配 (Contain)

替换字符串中任何原字符串匹配的部分. 例如, `§6正在传送到 Rothes 处.` 可以被 `传送` 和 `Rothes` 匹配.

### 完全匹配 (Equal)

在字符串与设定的原字符串完全相同时替换. 例如, `§6正在传送到 Rothes 处.` 只能被完全相同的字符串 `§6正在传送到 Rothes 处` 替换. 使用该模式要求您也同时加上色彩符号, 否则不会替换. 如果您需要帮助获取色彩符号, 请参阅 [捕获](../../Commands/Capture.md) 指令.

### 正则表达式 (Regex)

使用 Java 提供的正则表达式功能. PSR 会使用 #find() 函数, 因此其会为字符串内任何匹配正则表达式的部分替换. 例如, `§6Teleporting to Rothes.` 可以使用原字符串`§6Teleporting to ([\s\S]+).` 替换为新字符串 `§6正在传送到 $1 处.`

如您所见, 此模式非常适合使用于包含未知参数的字符串中, 替换精准度高.
