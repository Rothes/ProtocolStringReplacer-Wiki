# 用户 (User)

```yaml
Options:
  Filter: # Dictionary
    User: # Dictionary
      Permission: null # String
```

此设定项 `Filter.User` 用于控制此替换配置文件的过滤功能, 筛选此替换配置文件处理的用户.

### 权限 (Permission)

设定项 `Filter.User.Permission`. 默认值为 null. 如果设定此设定项, 则用户必须拥有该权限节点, 此替换配置文件才会为其处理. 如果保留为 null, 则 PSR 会跳过此过滤功能.

通过此设定项, 您可以给予玩家可个性化的选项, 例如, 要添加多语言功能, 您可以创建两个替换配置文件, 其中一个设定 `Options.Filter.User.Permission` 为 `protocolstringreplacer.lang.chinese`, 另外一个设定为  `protocolstringreplacer.lang.japanese`, 然后分别为其设定替换项, 即可达到效果. 您也可以通过此设定项来允许玩家自行开关此替换配置文件.
