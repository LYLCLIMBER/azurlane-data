# Azur Lane Data

国服《碧蓝航线》舰船配置表的非官方 JSON 快照。数据按运行时资源版本分目录保存，发布后不再修改。

三张表的 JSON 记录结构、字段名与取值语义，与 [AzurLaneTools/AzurLaneData](https://github.com/AzurLaneTools/AzurLaneData) 发布的 `CN/sharecfgdata` 对应文件兼容；按该 schema 解析的消费方无需改字段映射即可读取。目录布局不同，不能按该仓库的路径直接替换。

本仓库与游戏官方无关，不提供客户端、账号或资源下载。

## 目录

```text
versions/
└── <resource_version>/
    ├── version.json
    ├── ship_data_statistics.json
    ├── ship_data_template.json
    └── ship_skin_template.json
```

## 表

每张表都是以记录 ID 为键的 JSON object。

- `ship_data_statistics.json`：舰船基础属性与展示信息
- `ship_data_template.json`：舰船模板与分组
- `ship_skin_template.json`：皮肤与所属舰船组

`version.json` 提供资源版本、每张表的记录数和 `json_sha256`。

## 使用

从 `versions/` 中按点分数字版本选取最新目录，并在一次读取任务中固定使用该目录。不要混用不同版本的文件。
