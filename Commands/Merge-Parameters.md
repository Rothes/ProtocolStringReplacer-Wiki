# 合并参数

PSR 支持在指令中使用含空格的参数使用双引号(")来控制一个参数的起始处和末尾处. 起始处的双引号之前必须有一个空格, 末尾处的双引号之后必须也有一个空格, 且末尾处的双引号数量需为奇数.

例如, 此指令: `/psr edit replace add common "This is a param" "这是一个参数"` 中的参数会被 PSR 解析为 `edit`  `replace` `add` `common` `This is a param` `这是一个参数`.&#x20;



您需要对双引号之后一个字符为空格的双引号, 或者位于参数末尾的双引号做一些处理, 以便 PSR 能够正确理解您的意思.

例如, 如果您需要合并此字符串为一个参数: `This is a param with ""quotation" marks"`, 则指令应该使用 `/psr ... "This is a param with ""quotation"" marks"""`.

如您所见, 我们需要对这两种情况的双引号在原有情况上双写, 最后在参数末尾加上一个双引号表示结束.
