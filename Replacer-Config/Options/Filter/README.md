# 过滤器 (Filter)

```yaml
Options:
  Filter: # Dictionary
    Listen-Types: # String List
      - Chat
      - Sign
      - Title
      - Entity
      - Boss-Bar
      - ItemStack
      - Window-Title
      - ScoreBoard
    ScoreBoard: # Dictionary
      Replace-Title: false # Boolean
      Replace-Entity-Name: false # Boolean
    ItemStack: # Dictionary
      Window-Title: null # String
    User:
      Permission: null # String
```

此设定项 `Filter` 用于控制此替换配置文件的过滤功能, 用于指定此替换配置文件替换字符串的条件.  Filter 设定项是一个 YAML 对象(Dictionary), 如果替换配置文件中上述任何键为 null (或未定义) 则会使用上面的默认值. 目前过滤器功能还有待完善, 如您有任何建议添加的过滤项, 欢迎在 GitHub 上提交议题.

该设定项对替换效率影响较大, 有关更多信息请参阅 [替换效率](../../../Advanced-Docs/ti-huan-xiao-shuai.md).
