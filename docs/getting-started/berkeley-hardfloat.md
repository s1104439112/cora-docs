
# Berkeley Hard-Float 解析

---

Berkeley hard-float作为浮点运算单元，被cora使用。

更详细的英文版本链接[在这里](http://www.jhauser.us/arithmetic/HardFloat-1/doc/HardFloat-Verilog.html)

Berkeley HardFloat 是二进制浮点运算的硬件实现，符合 IEEE 浮点运算标准。
HardFloat 支持多种浮点格式，使用模块参数独立确定指数字段和有效位字段的
宽度。可能的格式集包括 16 位半精度、32 位单精度、64 位双精度和 128 位四精
度的标准格式。一些历史扩展格式，如英特尔的老 80 位双扩展精度浮点，不直
接支持。（但是，HardFloat 可以用于实现这些和其他基于 IEEE 的格式，并添加
了在编码之间转换的模块。）
Float Point 有三种主要的形式，IEEE 标准形式(简称 fN)，Recoder 形式，Raw
Deconstructions。

## IEEE 标准形式(fN)

需要满足条件

\begin{equation}
p \leq 2^{w-2} + 3
\end{equation}

其中 w 为 expWidth，p 为 sigWidth，一个 IEEE 标准形式浮点数长度为 w+p，
其中 p 中包含一位符号位。

常见的 IEEE 浮点格式如下

|       | expWidth(w) | sigWidth(p) |
| ----------- | ----------- | ----------- |
|16-bits half-precision | 5 | 11 |
|32-bits single-precision | 8 | 24 |
|64-bits double-precision | 11 | 53 |
|128-bits quadruple | 15 | 113 |


## Recoded Formats(RecFN)

对于每种标准形式，HardFloat 都定义了一个对应的 recoded format，以稍微
不同的表示形式对同一组值进行了编码。RecFN 和标准形式一样具有符号位、指
数位和有效数字位，其中指数位扩展了一位，因此标准的 32bit 但精度浮点数的
RecFN 形式是 33 位，1 个符号位、9 个指数位(扩展一位)和 23 个有效数字位。
RecFN 能够在一些方面简化浮点数运算，但是最重要的方面是 RecFN 能够将
subnormal 类型的数值正规化，因此可以将这类数值当作正规浮点数进行处理。
下表总结了 recoding


|       | Standard format | | |  Hardfloat's recoded format | | |
|       | sign | exponent | significand | sign | exponent | significand |
| ----------- | ----------- | ----------- |----------- | ----------- | ----------- |
| zeros | ----------- | ----------- |
|Subnormal numbers | 5 | 11 |
|Normal numbers| 8 | 24 |
|infinities | 11 | 53 |
|NaNs | 15 | 113 |

















