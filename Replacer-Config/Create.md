# 创建

如果需要创建一个替换配置文件, 只需要在 `plugins\ProtocolStringReplacer\Replacers` 目录中创建一个 .yml 后缀的文件, 并拷贝 [简述](jian-shu.md) 中的配置文件即可.

以下的文件可以被 PSR 加载:

* `plugins\ProtocolStringReplacer\Replacers\替换配置A.yml`
* `plugins\ProtocolStringReplacer\Replacers\我的一些替换配置\替换配置B.YML`

但是以下的文件不会被 PSR 加载:

* `plugins\ProtocolStringReplacer\替换配置C.yml` (没有放置于 Replacers\ 目录中)
* `plugins\ProtocolStringReplacer\Replacers\替换配置D.yml.a` (文件后缀名不为 .yml )
