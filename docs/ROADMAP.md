# نقشه راه پیشنهادی

## فاز صفر: تثبیت نیازمندی‌ها

- تعیین مدل دقیق MCU، W25Q، LCD و سخت‌افزار صوت
- تعیین سیستم‌عامل هدف و زبان نرم‌افزار ویندوز
- تعیین حداکثر تعداد/اندازه تصویر، صوت و فونت
- تعیین نیاز به Update میدانی و بازیابی قطع برق

## فاز یک: مشخصات فایل‌ها

- تعریف نسخه ۱ قالب `assets.bin`
- تعریف Header، Entry Table، Alignment و CRC
- تعریف قرارداد `asset_ids.h`
- تعریف Manifest بسته `.w25pack`
- ساخت نمونه و ابزار Inspect/Dump

## فاز دو: کتابخانه STM32

- درایور W25Qxx با Read/Write/Erase/JEDEC ID
- Parser جدول منابع
- جست‌وجو با ID
- خواندن Stream/Block
- نمایش RGB565
- Decoder صوت انتخاب‌شده
- Renderer فونت Bitmap
- خطاها، CRC و تست روی سخت‌افزار

## فاز سه: Media Converter

- تبدیل و Preview تصویر
- تبدیل، ضبط و Preview صوت
- تبدیل فونت و انتخاب محدوده Unicode
- CLI اولیه برای تست‌پذیری
- UI ویندوز پس از تثبیت هسته

## فاز چهار: Asset Builder

- مدیریت Project و Asset ID پایدار
- Layout خودکار و گزارش ظرفیت
- تولید `assets.bin`، Header و Library Config
- ساخت `.w25pack`
- اعتبارسنجی متقابل خروجی‌ها

## فاز پنج: پروگرامر

- نمونه اولیه UART + STM32 واسط
- Erase/Page Program/CRC/Progress/Retry
- ارتقا به USB CDC در صورت نیاز
- پشتیبانی CH341A و کنترل تداخل SPI روی برد
- فرمان «Program Complete Device» برای Firmware و Assets

## فاز شش: بهینه‌سازی و انتشار

- Update تفاضلی و سکتوری
- Double buffering
- Recovery در قطع برق
- Log و Diagnostics
- Installer، مستند کاربر و نمونه پروژه
- تست با چند مدل W25Q و STM32

