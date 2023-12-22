
# 数据集名称

第三届中文空间语义理解评测数据集（Spatial Cognition Evaluation, SpaCE）

## 第三届中文空间语义理解评测（SpaCE2023）

- **task1**: 中文空间语义异常文本识别任务，识别给定的中文文本中存在空间信息异常的片段。
- **task2**: 中文空间语义角色标注任务，基于给定的空间语义角色标注规范，标注给定的中文文本中所含的空间信息。空间语义角色共15个，包括：空间实体、参照实体、事件、事实性、时间、处所、起点、终点、方向、朝向、部件处所、部位、形状、路径、距离。
- **task3**: 中文空间场景异同判断任务，判断给定的两个形式相似的中文文本是否可以描述相同的空间场景，并说明判断理由。

评测网站：https://2030nlp.github.io/SpaCE2023/
数据集网址：https://github.com/2030NLP/SpaCE2023


# 数据规模

| **数据集名称**     | **子任务** | **训练集** | **验证集** | **测试集** | **合计** |
|:-------------:|:-------:|:-------:|:-------:|:-------:|:------:|
| **SpaCE2021** | task1   | 4237    | 806     | 794     | 5837   |
|                     | task2   | 5989    | 2088    | 1952    | 10029  |
|                     | task3   | 0       | 1203    | 1167    | 2370   |
| **SpaCE2022** | task1   | 10993   | 1602    | 3152    | 15747  |
|                     | task2   | 4966    | 700     | 1402    | 7068   |
|                     | task3   | 1529    | 207     | 396     | 2132   |
| **SpaCE2023** | task1   | 4962    | 700     | 1385    | 7047   |
|                     | task2   | 1529    | 207     | 427     | 2163   |
|                     | task3   | 10      | 0       | 100     | 110    |
| **合计**            | -       | 34215   | 7513    | 10775   | 52503  |


# 数据格式介绍

## 第三届中文空间语义理解评测（SpaCE2023）

### task1

文件格式：jsonl
字段说明：
- **qid**: 试题编号。
- **context**: 文本材料。
- **results**: 一个数组，包含若干个异常的空间信息。每一个信息由若干个文本片段组成，每一个文本片段由角色（role）、文本内容（text）和字序数组（idxes）组成：
  - role: 角色，包括S1、P1、E1、S2、P2、E2。
  - text: 文本内容。
  - idxes: 文本内容的每一个字在文本材料中的位置索引。文本材料的位置索引从0开始，如[1,2,3]表示文本内容是文本材料的第2~4个字。

### task2

文件格式：jsonl
字段说明：
- **qid**: 试题编号。
- **context**: 文本材料。
- **corefs**: 同指信息。
- **non_corefs**: 同形不同指信息。
- **results**: 一个数组，包含若干个空间信息的语义角色标注结果。每一个标注结果包含若干个有标注的语义角色。来源于文本材料的标注结果，由角色（role）和文本片段（fragment）组成。来源于特定标签的标注结果，由角色（role）和标签内容（label）组成：
    - role: 角色，包括空间实体、参照实体、事件、事实性、时间、处所、起点、终点、方向、朝向、部件处所、部位、形状、路径、距离。
    - fragment: 文本片段。
      - text: 文本内容。
      - idxes: 文本内容的每一个字在文本材料中的位置索引。文本材料的位置索引从0开始，如[1,2,3]表示文本内容是文本材料的第2~4个字。
    - label: 标签内容。

### task3

文件格式：jsonl
字段说明：
- **qid**: 试题编号。
- **context1**: 文本材料1。
- **context2**: 文本材料2。
- **results**: 判断结果（judge）和判断理由（reason）：
  - **judge**: 对文本材料1和文本材料2是否可以描述同一个空间场景的判断。**1**表示可以，**0**表示不可以。
  - **reason**: 用自然语言陈述的判断理由。本任务依赖人工对判断理由进行打分，由于没有唯一的理由，测试题（task3_test.jsonl）不设reason字段。

