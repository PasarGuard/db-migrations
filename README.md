# PasarGuard Database Migration Tool

Simple database migration tool for PasarGuard data between PostgreSQL, MySQL/MariaDB, and SQLite.

## Prerequisites

- Python 3.8+
- `uv` (https://github.com/astral-sh/uv)

Install `uv` (Linux/macOS):

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
source $HOME/.local/bin/env
```

## Recommended Flow (Step-by-Step)

1. Back up the source database.
2. Install and run PasarGuard on the target database with the same app version as source.
3. Wait until PasarGuard completes its own DB migrations.
4. Prepare migration tool:

```bash
git clone https://github.com/PasarGuard/db-migratons.git
cd db-migratons
uv sync
chmod +x migrate.sh
```

5. Run interactive migration:

```bash
./migrate.sh
```

6. In wizard: choose source, enter target DB URL, review summary, confirm with `yes`.
7. Verify users, groups, settings, and subscriptions in panel/API.

## Alternative Run Modes

Config file mode:

```bash
cp config.example.yml config.yml
uv run migrations/universal.py --config config.yml
```

Direct CLI mode:

```bash
./migrate.sh <source> --to <type> --db <target_url> [--exclude-tables <tables>]
```

## URL Formats

PostgreSQL:

```text
postgresql+asyncpg://username:password@host:port/database
```

MySQL/MariaDB:

```text
mysql+pymysql://username:password@host:port/database
```

SQLite:

```text
sqlite:///path/to/database.db
```

## Important Files

- Full config template: [config.example.yml](config.example.yml)
- MySQL -> PostgreSQL example: [config.mysql-to-postgres.yml](config.mysql-to-postgres.yml)
- PostgreSQL -> MySQL example: [config.postgres-to-mysql.yml](config.postgres-to-mysql.yml)
- Migrator script: [migrations/universal.py](migrations/universal.py)

## Notes

- Migration clears target data after interactive confirmation.
- Use `--exclude-tables` for log/history tables if needed.

## Support

- GitHub: https://github.com/PasarGuard/db-migratons
- Telegram: https://t.me/PasarGuardGP

## Other Languages

- Russian: [docs/README.ru.md](docs/README.ru.md)
- Chinese: [docs/README.zh.md](docs/README.zh.md)
- Persian (Farsi): [docs/README.fa.md](docs/README.fa.md)
