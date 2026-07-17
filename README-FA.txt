VynexApp v14.0.0 Frozen Deployer
================================

ویژگی‌ها:
- هسته پنل داخل worker.js به‌صورت Embedded قرار دارد.
- هیچ دریافت سورسی از Zeus، GitHub main یا CDN انجام نمی‌شود.
- هیچ آپدیت خودکاری وجود ندارد.
- آپدیت پنل‌های ساخته‌شده فقط از مسیر /updater و با توکن Cloudflare انجام می‌شود.
- هنگام آپدیت، D1 همان پنل حفظ می‌شود و کاربران پاک نمی‌شوند.
- خروجی سابسکریپشن دقیقاً ۶ کانفیگ است:
  1) Vynex | Irancell Turbo — NoTLS / 80
  2) Vynex | Irancell Backup — NoTLS / 8080
  3) Vynex | Irancell Stable — NoTLS / 80
  4) Vynex | Hamrah Turbo — TLS / 443
  5) Vynex | Hamrah Backup — TLS / 8443
  6) Vynex | Hamrah Stable — TLS / 2053

SHA-256 هسته Frozen:
2bbb270ee6b2ff5f2efe712135e72b9f17b1dedd604334a519e0cb011888058c

روش استفاده:
1) فایل‌های ZIP را در یک Repository قرار بده یا worker.js را در Cloudflare Worker آپلود کن.
2) در صورت استفاده از Git integration، Deploy command را npx wrangler deploy قرار بده.
3) آدرس Worker را باز کن.
4) برای ساخت پنل جدید توکن Cloudflare را وارد کن.
5) برای آپدیت دستی پنل‌ها وارد /updater شو.

Permissionهای لازم توکن:
- Account / Workers Scripts / Edit
- Account / D1 / Edit
- Account Settings / Read

امنیت:
- توکن در پنل‌های ساخته‌شده ذخیره نمی‌شود.
- فقط Binding دیتابیس D1 با نام DB روی پنل قرار می‌گیرد.
