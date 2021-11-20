# 监听类型 (Listen-Types)

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
      - Console
```

此设定项 `Filter.Listen-Types` 用于控制此替换配置文件的过滤功能, 筛选替换的数据包类型. 我们十分建议您只在此处填写您需要处理的数据包类型, 以避免不必要的资源占用和处理延迟.

#### Chat

数据包为 [Chat Message](https://wiki.vg/Protocol#Chat\_Message\_.28clientbound.29). 代表聊天框内的文本信息和快捷栏上的 Action Bar 信息 .

#### Sign

Minecraft 1.10 及以上, 数据包为 [Chunk Data](https://wiki.vg/Protocol#Chunk\_Data) 和 [Block Entity Data](https://wiki.vg/Protocol#Block\_Entity\_Data); Minecraft 1.10 以下, 数据包为 [Update Sign](https://wiki.vg/index.php?title=Protocol\&oldid=7959#Update\_Sign). 代表告示牌上的四行文本.

#### Title

Minecraft 1.17 及以上, 数据包为 [Set Title Text](https://wiki.vg/Protocol#Set\_Title\_Text) 和 [Set Title SubTitle](https://wiki.vg/Protocol#Set\_Title\_SubTitle); Minecraft 1.17 以下, 数据包为 [Title](https://wiki.vg/index.php?title=Protocol\&oldid=16681#Title). 代表显示于屏幕中央的标题和副标题文本信息.

#### Entity

数据包为 [Entity Metadata](https://wiki.vg/Protocol#Entity\_Metadata). 代表实体的显示名称, 以及物品展示框中的物品.

#### Boss-Bar

数据包为 [Boss Bar](https://wiki.vg/Protocol#Boss\_Bar). 代表 BOSS 血量条上方的文本.

#### ItemStack

数据包为 [Window Items](https://wiki.vg/Protocol#Window\_Items) 和 [Set Slot](https://wiki.vg/Protocol#Set\_Slot). 代表玩家背包、容器界面中的物品.

#### Window-Title

数据包为 [Open Window](https://wiki.vg/Protocol#Open\_Window). 代表容器的标题文本.

#### ScoreBoard

数据包为 [Scoreboard Objective](https://wiki.vg/Protocol#Scoreboard\_Objective) 和 [Update Score](https://wiki.vg/Protocol#Update\_Score). 代表右侧计分板的标题, 以及计分板中每一项目的名字 (对于玩家为用户名, 反则为实体 UUID).

#### Console

特殊监听类型, 没有数据包. 代表显示于控制台中的文本信息.

如果您在 1.12 及以上的版本运行此插件, 那么请注意 Console 监听类型的原字符串开头都包含时间戳和日志级别 (如 `[12:00:00 INFO]: `), 末尾都会有一个换行符 (\n). 一般为此类型使用 Regex 替换, 而不是 Equal.
