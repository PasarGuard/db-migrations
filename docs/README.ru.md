# Пошаговая миграция PasarGuard (RU)

Минимальный сценарий:

1. Сделайте резервную копию исходной БД.
2. Запустите PasarGuard на целевой БД (та же версия приложения, что и на source).
3. Дождитесь завершения миграций PasarGuard на target.
4. Подготовьте инструмент:

```bash
git clone https://github.com/PasarGuard/db-migratons.git
cd db-migratons
uv sync
chmod +x migrate.sh
```

5. Запустите миграцию:

```bash
./migrate.sh
```

6. В wizard: выберите source, укажите target URL, проверьте сводку, подтвердите `yes`.
7. Проверьте данные в панели/API.

Для расширенных опций (`exclude_tables`, `table_order`, `enum_defaults`) смотрите: [../README.md](../README.md)
