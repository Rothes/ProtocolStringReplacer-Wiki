# ItemStack

```yaml
Options:
  Filter: # Dictionary
    ItemStack: # Dictionary
      Window-Title: null # String List
      Ignore-Inventory-Title: false # Boolean
```

此设定项 `Filter.User.ItemStack` 用于控制此替换配置文件的过滤功能, 筛选此替换配置文件处理有关物品监听类型的条件.

### Window-Title

设定项 `Filter.ItemStack.Window-Title`. 代表替换要求的窗口标题.  默认值为 null. 如果设定此设定项, 则 PSR 将获取用户目前打开的窗口(即容器)的标题 Json, 只有其与此设定的列表中的任意一项完全相同时, 此替换配置文件才会为其处理. 如果保留为 null, 则 PSR 会跳过此过滤功能.

您可以使用 [捕获](../../../zhi-ling/bu-huo.md) 指令捕获 Window-Title 监听类型来获取窗口标题 Json.

### Ignore-Inventory-Title

设定项 `Filter.ItemStack.Ignore-Inventory-Title`. 代表是否为玩家库存(即背包)中的物品替换忽略 `Window-Title` 的限制. 只有设定了 `Window-Title` 后, 才需要设定.
