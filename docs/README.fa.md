# راهنمای مهاجرت PasarGuard (FA)

مسیر حداقلی:

1. از دیتابیس مبدا بکاپ بگیرید.
2. PasarGuard را روی دیتابیس مقصد اجرا کنید (نسخه برنامه در مبدا و مقصد یکسان باشد).
3. صبر کنید مهاجرت‌های خود PasarGuard روی مقصد کامل شود.
4. ابزار مهاجرت را آماده کنید:

```bash
git clone https://github.com/PasarGuard/db-migratons.git
cd db-migratons
uv sync
chmod +x migrate.sh
```

5. مهاجرت را اجرا کنید:

```bash
./migrate.sh
```

6. در wizard: مبدا را انتخاب کنید، URL مقصد را وارد کنید، خلاصه را بررسی کنید، `yes` بزنید.
7. داده‌ها را در پنل/API بررسی کنید.

برای گزینه‌های پیشرفته (`exclude_tables`، `table_order`، `enum_defaults`) به فایل اصلی مراجعه کنید: [../README.md](../README.md)
