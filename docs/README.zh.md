# PasarGuard 迁移步骤（中文）

最简流程：

1. 先备份源数据库。
2. 在目标数据库运行 PasarGuard（应用版本与源端一致）。
3. 等待 PasarGuard 在目标库完成自身迁移。
4. 准备迁移工具：

```bash
git clone https://github.com/PasarGuard/db-migratons.git
cd db-migratons
uv sync
chmod +x migrate.sh
```

5. 执行迁移：

```bash
./migrate.sh
```

6. 在向导中：选择 source、填写 target URL、确认摘要、输入 `yes`。
7. 在面板/API 校验数据。

高级选项（`exclude_tables`、`table_order`、`enum_defaults`）见: [../README.md](../README.md)
