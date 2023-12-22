
# 数据集名称

第一届中文空间语义理解评测数据集（Spatial Cognition Evaluation, SpaCE）


# 任务概述

## 第一届中文空间语义理解评测（SpaCE2021）

- **task1**: 中文空间语义正误判断任务，判断给定的中文文本中是否存在空间信息异常。
- **task2**: 中文空间语义异常归因合理性判断任务，判断给定的归因是否可以解释给定的中文文本中所存在的空间信息异常。
- **task3**: 中文空间语义判断与归因联合任务，判断给定的中文文本中是否存在空间信息异常，如果存在异常，再判断给定的归因类型是否可以解释这一异常。

评测网站：http://ccl.pku.edu.cn:8084/SpaCE2021/
数据集网址：https://github.com/2030NLP/SpaCE2021


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

## 第一届中文空间语义理解评测（SpaCE2021）

### task1

文件格式：json
字段说明：
- **qID**: 试题编号。
- **context**: 文本材料。
- **judge1**: 对文本是否存在空间信息异常的判断。true表示无异常，false表示有异常。

### task2

文件格式：json
字段说明：
- **qID**: 试题编号。
- **context**: 文本材料。
- **reason**: 对空间信息异常的归因。
- **judge2**: 对归因是否能够解释空间信息异常的判断。true表示归因成立，false表示归因不成立。

### task3

文件格式：json
字段说明：
- **qID**: 试题编号。
- **context**: 文本材料。
- **reason**: 对空间信息异常的归因。
- **judge1**: 对文本是否存在空间信息异常的判断。true表示无异常，false表示有异常。
- **judge2**: 对归因是否能够解释空间信息异常的判断。true表示归因成立，false表示归因不成立。

