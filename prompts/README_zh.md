# 评测提示词清单

分类与分割评测的每个数据集包含 `prompts1.json`、`prompts2.json` 和 `prompts3.json`，分别对应论文附录中的 Prompt 1、Prompt 2 和 Prompt 3。各方法应在同一组文件下比较。检索评测使用 IR-TD 字幕，不使用这些类别提示词。

| 数据集目录 | 类别数 | 每类每组提示词数 | JSON 结构 |
| --- | ---: | ---: | --- |
| `M3FD` | 6 | 10 | 顶层 `prompts` 字段 |
| `SMOD` | 4 | 10 | 顶层 `prompts` 字段 |
| `flirv1` | 4 | 10 | 顶层 `prompts` 字段 |
| `flirv2` | 12 | 10 | 顶层 `prompts` 字段 |
| `llvip` | 2 | 10 | 顶层 `prompts` 字段 |
| `JU-VNT-T` | 20 | 10 | 顶层 `prompts` 字段 |
| `MFNet` | 8 | 10 | 类别名直接作为顶层键 |
| `PST900` | 4 | 10 | 类别名直接作为顶层键 |
| `CART` | 10 | 50 | 顶层 `prompts` 字段 |
| `SemanticRT` | 13 | 50 | 顶层 `prompts` 字段 |

MFNet 的类别键为 `bike`、`bump`、`car`、`carstop`、`colorcone`、`curve`、`guardrail`、`person`。PST900 的类别键为 `backpack`、`fireextinguisher`、`handdrill`、`rescuerandy`。评测时应使用文件中的原始键和类别顺序，并与数据标注映射核对；本清单不替代评测代码中的类别索引映射。

本目录的三组文件在每个数据集内均包含不同的提示词文本。JSON 文件未记录 Kimi-K2.5 的调用参数、随机种子或生成时间，因此仅凭文件无法证明生成调用的统计独立性，也无法独立验证评测脚本如何聚合每类多条描述。论文只将三组结果作为不同提示词集合下的观测，不据此声称已排除全部提示词随机性。
