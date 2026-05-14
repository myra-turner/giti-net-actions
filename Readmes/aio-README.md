<p align="center">
  <h1 align="center">🌐 aio‑downloader</h1>
  <p align="center"><strong>All‑in‑One GitHub Actions Downloader — بدون فیلتر · بدون تحریم</strong></p>
</p>

<p align="center">
  ⭐ <strong>اگر این پروژه برایتان مفید است، لطفاً ستاره بدهید — به دیگران کمک می‌کند پیدایش کنند!</strong> ⭐
</p>

---

<div dir="rtl">

# 📖 راهنمای فارسی (Persian Guide)

> **پیش از هر چیز:** این مخزن را فورک کرده‌اید؟ **حتماً** ابتدا **پاک‌کننده جامع (AIO Cleaner)** را اجرا کنید تا تمام فایل‌های باقی‌مانده از مخزن اصلی (شامل بایگانی و رسانه‌های تلگرام) از بین بروند و شما از صفر شروع کنید. (توضیحات کامل در بخش ۸)

---

## 📋 فهرست

1. [پیش‌نیازها](#-پیشنیازها)
2. [فورک و راه‌اندازی اولیه](#-فورک-و-راهاندازی-اولیه)
3. [نحوه استخراج و افزودن کوکی‌ها](#-نحوه-استخراج-و-افزودن-کوکیها)
4. [راهنمای کامل هر گردش کار](#-راهنمای-کامل-هر-گردش-کار)
   - [۱. دانلودر یوتیوب (yt‑dlp ساده)](#۱-دانلودر-یوتیوب-yt-dlp-ساده)
   - [۲. دانلودر اینستاگرام](#۲-دانلودر-اینستاگرام)
   - [۳. دانلودر X (توییتر)](#۳-دانلودر-x-توییتر)
   - [۴. دانلودر مستقیم](#۴-دانلودر-مستقیم)
   - [۵. آرشیو کانال تلگرام](#۵-آرشیو-کانال-تلگرام)
   - [۶. ضبط وبسایت](#۶-ضبط-وبسایت)
   - [۷. لیچر (Leecher) – میانبر + دستورات خام](#۷-لیچر-leecher--میانبر--دستورات-خام)
   - [۸. پاک‌کننده جامع (AIO Cleaner)](#۸-پاککننده-جامع-aio-cleaner)
   - [۹. دانلودر گوگل پلی (APK)](#۹-دانلودر-گوگل-پلی-apk)
   - [۱۰. MHRV خروجی VPS (Exit Node)](#۱۰-mhrv-خروجی-vps-exit-node)
5. [محدودیت‌ها و هشدارهای مهم](#-محدودیتها-و-هشدارهای-مهم)
6. [فایل zoomusers.md چیست؟](#-فایل-zoomusersmd-چیست)

---

## ⚠️ پیش‌نیازها

| نیاز | توضیح |
|------|--------|
| 🟢 **حساب GitHub** | رایگان — همین کافیست |
| 🟠 **مرورگر + افزونه Get cookies.txt LOCALLY** | Chrome / Firefox / Edge |
| 🔵 **حساب اینستاگرام** | (اختیاری) برای استوری و محتوای خصوصی |
| 🔴 **حساب X (توییتر)** | **الزامی** برای دانلودر X |
| 🟣 **حساب Cloudflare** | (اختیاری) برای MHRV Exit Node — نیاز به **TUNNEL_AUTH_KEY** |
| 🟢 **تلگرام، ضبط وبسایت، و گوگل پلی** | هیچ چیز اضافی نیاز ندارند |

---

## 🚀 فورک و راه‌اندازی اولیه

### مرحله ۱: فورک کردن مخزن
روی دکمه **Fork** در بالای صفحه کلیک کنید.

### مرحله ۲: فعال‌سازی GitHub Actions
1. به مخزن فورک‌شده بروید → **Settings** → **Actions** → **General**
2. در بخش **Actions permissions** گزینه **Allow all actions and reusable workflows** را انتخاب کنید
3. روی **Save** کلیک کنید

### مرحله ۳: دادن دسترسی نوشتن (بسیار مهم!)
1. همان مسیر → **Workflow permissions**
2. گزینه **Read and write permissions** را انتخاب کنید
3. روی **Save** کلیک کنید

> ⚠️ **اگر این مرحله را انجام ندهید، تمام گردش‌کارها هنگام آپلود فایل‌ها با خطا مواجه می‌شوند!**

### مرحله ۴: پاک‌سازی اولیه (بسیار توصیه می‌شود!)
> 🧹 **مخزن فورک‌شده حاوی فایل‌های بایگانی و رسانه‌های تلگرام از مخزن اصلی است. برای شروع کاملاً تمیز، همین حالا پاک‌کننده جامع را برای تمام پلتفرم‌ها اجرا کنید.**  
> به **Actions** → **aio-cleaner** بروید، گزینه **Clean ALL platforms** را تیک بزنید و اجرا کنید.  
> با این کار همه چیز پاک می‌شود و می‌توانید از صفر شروع کنید.

### مرحله ۵ (اختیاری): تنظیم Secret برای MHRV Exit Node
> اگر قصد دارید از **MHRV VPS Exit Node** (بخش ۱۰) استفاده کنید، یک Secret به نام **`TUNNEL_AUTH_KEY`** بسازید و رمز PSK خود را در آن قرار دهید. این رمز باید دقیقاً با `psk` یا `auth_key` در فایل `config.json` پروژه **MasterHttpRelayVPN** شما یکسان باشد.

---

## 🍪 نحوه استخراج و افزودن کوکی‌ها

> ℹ️ **یوتیوب و اینستاگرام:** برای برخی محتواها به کوکی نیاز دارند.  
> 🔴 **X (توییتر): حتماً به کوکی نیاز دارد.**  
> 🟢 **تلگرام، ضبط وبسایت، گوگل پلی، و MHRV Exit Node:** بدون کوکی کار می‌کنند.

### ۱. استخراج کوکی‌ها — حتماً از پنجره ناشناس (Private/Incognito) استفاده کنید!

1. **یک پنجره جدید ناشناس/خصوصی (Private/Incognito)** در مرورگر خود باز کنید
2. افزونه **Get cookies.txt LOCALLY** را نصب کنید (Chrome Web Store یا Firefox Add‑ons)
3. در همان پنجره خصوصی، وارد **youtube.com** (برای یوتیوب)، **instagram.com** (برای اینستاگرام)، یا **x.com** (برای X) شوید
4. روی آیکون افزونه کلیک کنید و **Export** (فرمت Netscape) را انتخاب کنید
5. فایل `.txt` را در جای امنی ذخیره کنید
6. **پنجره خصوصی را کاملاً ببندید** — این کار اطمینان می‌دهد نشست صادرشده در جای دیگری باز نمی‌ماند

> 🔴 **چرا پنجره ناشناس؟** اگر در پنجره معمولی کوکی استخراج کنید و بعداً از آن سایت خارج شوید (Logout)، کوکی‌ها بی‌اعتبار می‌شوند. پنجره ناشناس را ببندید تا نشست بسته شود اما کوکی‌ها معتبر بمانند.

> ⚠️ **هشدار مهم درباره کوکی‌ها:** کوکی‌ها به مرور زمان منقضی می‌شوند یا توسط سرویس‌دهنده باطل می‌شوند. علائم خرابی کوکی:
> - خطای **Sign in to confirm you're not a bot** در دانلود یوتیوب
> - خطای **429 Too Many Requests** در دانلود اینستاگرام
> - دانلود موفق گزارش می‌شود اما فایلی در پوشه خروجی نیست
>
> در این موارد، کوکی جدید از پنجره ناشناس استخراج کرده و Secret مربوطه را به‌روزرسانی کنید.

### ۲. افزودن کوکی‌ها به GitHub Secrets

1. در مخزن فورک‌شده، به **Settings** → **Secrets and variables** → **Actions** بروید
2. روی **New repository secret** کلیک کنید
3. یک secret با نام **`YOUTUBE_COOKIES`** بسازید و محتوای فایل کوکی یوتیوب را در آن بچسبانید
4. یک secret با نام **`INSTAGRAM_COOKIES`** بسازید و محتوای فایل کوکی اینستاگرام را در آن بچسبانید
5. یک secret با نام **`X_COOKIES`** بسازید و محتوای فایل کوکی X را در آن بچسبانید

> 🔴 **هرگز فایل‌های کوکی را مستقیماً در مخزن commit نکنید!** گردش‌کار از Secrets استفاده می‌کند و کوکی‌ها در لاگ یا کد نمایش داده نمی‌شوند.

---

## 📦 راهنمای کامل هر گردش کار

### ۱. دانلودر یوتیوب (yt‑dlp + ۱۰ لایه پشتیبان) 🛡️

⚡ **مخزن‌تانک YouTube!** این گردش‌کار فراتر از یک yt‑dlp ساده است — با **۱۰ استراتژی پشتیبان (Fallback)** طراحی شده تا حتی اگر متد اصلی شکست خورد، خودبه‌خود راه‌های جایگزین را امتحان کند.

#### ✨ ویژگی‌های جدید و قدرتمند:

| ویژگی | توضیح |
|--------|--------|
| 🟢 **بدون نیاز به کوکی** | حتی اگر `YOUTUBE_COOKIES` را تنظیم نکرده باشید، گردش‌کار با yt‑dlp بدون کوکی و ۹ متد دیگر تلاش می‌کند |
| 🔄 **۱۰ لایه پشتیبان خودکار** | اگر دانلود اصلی شکست خورد، یکی‌یکی ۱۰ استراتژی مختلف را امتحان می‌کند (نیازی به دخالت شما نیست!) |
| 📊 **نمایش پیشرفت زنده** | درصد و حجم دانلود را در لحظه می‌بینید |
| 🎯 **انتخاب هوشمند کیفیت** | نزدیک‌ترین رزولوشن و FPS موجود را پیدا می‌کند (حتی اگر دقیقاً مقدار درخواستی وجود نداشته باشد) |
| 🔧 **Remux خودکار** | فایل‌های دانلودی با ffmpeg بازسازی می‌شوند تا قابل پخش باشند |
| 📦 **ZIP چندبخشی** | فایل‌های >۹۹MB خودکار تقسیم می‌شوند |
| 🌐 **لینک‌های غیر یوتیوب** | URLهای مستقیم (غیر یوتیوب) را نیز با wget دانلود می‌کند |

#### 🧠 ۱۰ لایه پشتیبان — اگر yt‑dlp معمولی جواب نداد:

| # | استراتژی | توضیح |
|---|-----------|--------|
| 1 | `yt-dlp اندروید` | با شبیه‌سازی کلاینت اندروید (player_client=android) |
| 2 | `yt-dlp iOS` | با شبیه‌سازی کلاینت iOS |
| 3 | `yt-dlp بدون کوکی` | تلاش بدون هیچ کوکی (حتی اگر کوکی تنظیم کرده باشید) |
| 4 | `youtube-dl` | ابزار کلاسیک youtube-dl |
| 5 | `pytube (best)` | کتابخانه pytube پایتون — بهترین کیفیت |
| 6 | `pytube (resolution)` | pytube با رزولوشن درخواستی |
| 7 | `API loader.to` | سرویس خارجی loader.to |
| 8 | `API vevioz` | سرویس خارجی api.vevioz.com |
| 9 | `cobalt.tools` | سرویس cobalt.tools (کیفیت 720p) |
| 10 | `yt-dlp IPv4 + retry` | yt‑dlp با اجبار IPv4 و ۱۰ تلاش مجدد |

> 💡 **یعنی چی؟** یعنی اگر یوتیوب متد اصلی را بلاک کند، گردش‌کار بی‌صدا ۱۰ راه مختلف را امتحان می‌کند تا فایل شما دانلود شود — بدون اینکه شما کاری انجام دهید. **این قوی‌ترین دانلودر یوتیوب رایگانی است که روی GitHub Actions خواهید دید!**

#### 📝 نحوه استفاده (مثل قبل):

1. به **Actions** → **youtube-downloader** بروید
2. روی **Run workflow** کلیک کنید
3. ورودی‌ها را وارد کنید. **فرمت:** `URL v/a رزولوشن fps` (fps اختیاری)

**مثال‌ها:**
```
https://www.youtube.com/watch?v=dfdXGw1xY9A v 480
https://www.youtube.com/watch?v=dfdXGw1xY9A v 1080 60
https://www.youtube.com/watch?v=dfdXGw1xY9A a max
https://www.youtube.com/watch?v=VIDEO_ID v 4k, https://www.youtube.com/watch?v=VIDEO_ID a 128
```

- `v` = ویدیو، `a` = صدا
- رزولوشن: `max`, `min`, `1080`, `2k`, `4k` و غیره
- FPS: اختیاری (مثلاً `60`, `30`)
- اگر `v/a` را وارد نکنید، پیش‌فرض **حداکثر کیفیت ویدیو** انتخاب می‌شود
- برای حداکثر کیفیت صدا (`a max`) خروجی به صورت `.opus` ذخیره می‌شود

4. روی **Run workflow** کلیک کنید → خروجی در پوشه **`youtube/`** (با ZIP چندبخشی برای فایل‌های بزرگ)

> 🟢 **کوکی اختیاری است!** اگر `YOUTUBE_COOKIES` را در Secrets تنظیم نکرده باشید، گردش‌کار بدون آن و با ۱۰ لایه پشتیبان کار می‌کند. البته افزودن کوکی شانس موفقیت در لایه‌های ۱ و ۲ را افزایش می‌دهد.

---

### ۲. دانلودر اینستاگرام

دانلود تمام رسانه‌ها (عکس، ویدیو، استوری، Highlight، Carousel).

1. به **Actions** → **instagram-downloader** بروید
2. روی **Run workflow** کلیک کنید
3. لینک‌های اینستاگرام را با کاما، فاصله یا خط جدید جدا کنید

**مثال:**
```
https://www.instagram.com/p/DX2y7oLDFOb/, https://www.instagram.com/reel/DVRXhn0gjL3/, https://www.instagram.com/p/DX6US4uCNGb/
```

4. روی **Run workflow** کلیک کنید → فایل ZIP در پوشه **`instagram/`** قرار می‌گیرد (تا ۱۰+ لینک در یک ZIP)

> ⚠️ **اخطار خطای ۴۲۹:** اگر خطای **429 Too Many Requests** دریافت کردید، به‌احتمال زیاد کوکی اینستاگرام شما منقضی یا محدود شده است. کوکی جدید از پنجره ناشناس استخراج کرده و `INSTAGRAM_COOKIES` را به‌روزرسانی کنید.

---

### ۳. دانلودر X (توییتر)

دانلود تمام رسانه‌ها (عکس، ویدیو) از توییت‌ها و پروفایل‌ها.

> 🔴 **کوکی `X_COOKIES` الزامی است!**

1. به **Actions** → **x-downloader** بروید
2. روی **Run workflow** کلیک کنید
3. لینک‌های X را با کاما، فاصله یا خط جدید جدا کنید

**مثال:**
```
https://x.com/username/status/123456789, https://x.com/otheruser/status/987654321
```

4. روی **Run workflow** کلیک کنید → ZIP در پوشه **`x/`** قرار می‌گیرد

---

### ۴. دانلودر مستقیم

دانلود **هر فایل** از لینک مستقیم با `aria2c` (۱۶ اتصال موازی — بسیار سریع).

1. به **Actions** → **direct-downloader** بروید
2. روی **Run workflow** کلیک کنید
3. لینک‌های مستقیم (`.zip`, `.mp4`, `.apk`, `.pdf` و غیره) را بچسبانید

**مثال:**
```
https://example.com/path/to/large-file.zip, https://example.com/another-file.mp4
```

4. روی **Run workflow** کلیک کنید → فایل‌ها در **`direct/`** (بزرگتر از ۹۹MB به ZIP چندبخشی تقسیم می‌شوند)

> ℹ️ **توجه:** برای جلوگیری از تداخل با دانلودهای قبلی، یک رشته ۵ حرفی تصادفی به نام فایل اضافه می‌شود. با این کار می‌توانید همان فایل را چندین بار بدون خطا دانلود کنید.

---

### ۵. آرشیو کانال تلگرام

کانال‌های **عمومی** تلگرام را اسکن کرده و پیام‌ها، عکس‌ها و ویدیوها را به صورت بایگانی Markdown ذخیره می‌کند.  
به‌صورت **خودکار (هر ۱۵ دقیقه)** یا **دستی** اجرا می‌شود.

> 📡 **مشاهده نمونه زنده:**  
> مخزن اصلی این پروژه، یک **بایگانی زنده از کانال‌های خبری تلگرام** را نگهداری می‌کند که هر **۱۰ دقیقه** به‌صورت خودکار به‌روزرسانی می‌شود.  
> برای دیدن آخرین اخبار و رسانه‌های آن، می‌توانید همین حالا این فایل را باز کنید:  
> **[telegram.md در مخزن اصلی](https://github.com/ProAlit/aio-downloader/blob/main/telegram.md)**  
> *این فایل در فورک شما به‌روزرسانی نمی‌شود؛ برای دریافت خودکار اخبار، اجرای گردش‌کار تلگرام را در فورک خود فعال کنید.*

> 🟢 **بدون نیاز به API Key یا کوکی!**

> ⏱️ **تأخیر زمان‌بندی خودکار:** GitHub ضمانت اجرای دقیق هر ۱۵ دقیقه را نمی‌دهد. ممکن است تأخیرهایی تا ۱ تا ۶ ساعت بین اجراها پیش بیاید. برای دریافت لحظه‌ای، اجرای دستی را انتخاب کنید یا اگر حرفه‌ای هستید، یک cronjob خارجی تنظیم نمایید.

#### نحوه کار (گام به گام)

1. خواندن لیست کانال‌ها از `telegram/channels.json`
2. راه‌اندازی مرورگر Chromium (Playwright) و بازدید از `https://t.me/s/`
3. اسکرول برای دریافت پیام‌های جدید
4. استخراج متن، زمان UTC، عکس‌ها (CSS background‑url)، ویدیوها و اسناد
5. دانلود رسانه‌ها در `telegram/content/`
6. تبدیل زمان‌ها به منطقه زمانی تهران و تقویم جلالی
7. مرتب‌سازی همه پیام‌ها از جدید به قدیم
8. نوشتن در `telegram.md` با فرمت Markdown (فونت Vazirmatn، راست‌به‌چپ)
9. ذخیره آخرین شناسه پیام در `telegram/last_ids.json`
10. Commit و push (با ۵ بار تلاش مجدد)

#### 📋 مشاهده بایگانی

فایل `telegram.md` را در مخزن باز کنید. GitHub مارک‌داون را نمایش می‌دهد — متن‌های نقل‌قول، تصاویر و لینک ویدیوها. تاریخ‌ها به تقویم جلالی با زمان تهران است.

#### ➕ افزودن/حذف کانال

فایل `telegram/channels.json` را ویرایش کنید (روی آیکون مداد ✏️ کلیک کنید).

> 🔴 **نام کانال‌ها را بدون @ وارد کنید!**
>
> ❌ `@channelname` — نادرست
> ✅ `channelname` — درست

**مثال:**
```
["VahidOOnLine", "mwarmonitor", "pm_afshaa", "iaghapour", "DEJradio", "mamlekate", "kianmeli1"]
```

> ⚠️ فقط کانال‌های **عمومی (Public)** کار می‌کنند. کانال‌های خصوصی قابل دسترسی نیستند.

#### ▶️ اجرای دستی

1. **Actions** → **telegram-fetcher**
2. **Run workflow** → **Run workflow**

---

### ۶. ضبط وبسایت

هر وبسایت **عمومی** را به یک فایل PDF واحد و باکیفیت تبدیل می‌کند. از **Playwright + Chromium** برای رندر کامل صفحات (جاوااسکریپت، CSS، تصاویر) استفاده می‌کند.

#### نحوه استفاده

1. به **Actions** → **website-capture** بروید
2. روی **Run workflow** کلیک کنید
3. آدرس کامل (حتماً با `https://` شروع شود) را وارد کنید

**مثال‌ها:**
```
https://example.com/article/my-post
https://developer.mozilla.org/en-US/docs/Web/JavaScript
https://github.com/ProAlit/aio-downloader
```

4. کلیک کنید → ظرف ۵–۱۰ دقیقه PDF در پوشه **`website/`** ظاهر می‌شود

> ⚠️ **محدودیت‌ها:**
> - فقط سایت‌های عمومی (بدون دیوار ورود)
> - حداکثر ۵۰۰ لینک داخلی استخراج می‌شود
> - مهلت ۳۰ دقیقه‌ای برای کل فرآیند
> - صفحات تک‌صفحه‌ای (SPA) مبتنی بر JavaScript سنگین ممکن است کامل رندر نشوند
> - بدون نیاز به کوکی

---

### ۷. لیچر (Leecher) – میانبر + دستورات خام

💥 **قدرتمندترین گردش‌کار این مخزن!**  
لیچر از `yt-dlp` پشتیبانی کامل می‌کند و تقریباً **هر لینکی** را می‌توانید به آن بدهید — از یوتیوب و توییتر گرفته تا اینستاگرام، تیک‌تاک، پینترست، ساندکلود، اسپاتیفای و **بیش از ۱۸۰۰ سایت دیگر**.  
در اینجا نه محدود به یوتیوب هستید، نه به گزینه‌های از پیش تعریف‌شده. **همه چیز در کنترل شماست.**

#### دو شیوه استفاده:

- **🟢 حالت میانبر (Shortcut):** درست مثل دانلودر یوتیوب — با فرمت `URL v/a رزولوشن fps` (راحت و سریع برای یوتیوب و چند سایت دیگر)
- **🔴 حالت خام (Raw):** قدرت بی‌نهایت — با قرار دادن `--` در انتهای URL، هر گزینه معتبر `yt-dlp` را مستقیماً پاس می‌دهید. این یعنی می‌توانید فرمت، کوکی، زیرنویس، آرشیو، پلی‌لیست، محدودیت نرخ و … را کاملاً دستی تنظیم کنید.

---

#### 🎯 مثال‌های جذاب از قدرت لیچر (حالت خام)

| پلتفرم | نمونه دستور (داخل ورودی‌های workflow) |
|--------|--------------------------------------|
| **یوتیوب** – ویدیو با کیفیت 1080p + زیرنویس انگلیسی | `https://youtube.com/watch?v=VIDEO_ID v 480/720/1080 // https://www.youtube.com/watch?v=VIDEO_ID -- --format "best[height<=1080]" --sub-lang en --write-subs` |
| **اینستاگرام** – دانلود پست یا ریل (با کوکی) | `https://www.instagram.com/p/CODE -- --cookies cookies.txt --output "%(title)s.%(ext)s"` |
| **تیک‌تاک** – دانلود ویدیو و ذخیره زیرنویس | `https://www.tiktok.com/@user/video/ID -- --write-subs --sub-lang en` |
| **توییتر / X** – بهترین کیفیت موجود | `https://x.com/user/status/ID -- --format best` |
| **پینترست** – دانلود تصویر | `https://www.pinterest.com/pin/ID -- --format best` |
| **ساندکلاد** – استخراج صدا با کیفیت اصلی | `https://soundcloud.com/artist/track -- --format bestaudio` |
| **اسپاتیفای** – (متادیتا) | `https://open.spotify.com/track/ID -- --print "%(title)s - %(artist)s"` |
| **ویــمئو** – دانلود ویدیو با رزولوشن دلخواه | `https://vimeo.com/ID -- --format "best[height<=720]"` |
| **دیلی‌موشن** – دانلود ویدیو | `https://www.dailymotion.com/video/ID -- --format best` |
| **تلگرام (لینک عمومی)** – دانلود فایل از کانال عمومی | `https://t.me/channel/12345 -- --format best` |
| **سایت‌های مستهجن** – دانلود از سایت‌های مستهجن | `لینک ویدئو v 480/720/1080` |

> ℹ️ **نکته:** برای سایت‌هایی مثل اینستاگرام و تیک‌تاک که به کوکی نیاز دارند، ابتدا کوکی‌ها را به Secrets اضافه کنید (مطابق بخش ۳) و سپس در دستور `--cookies /path/to/cookies.txt` را قرار دهید. لیچر فایل کوکی را از Secret می‌خواند و در مسیر استاندارد ذخیره می‌کند.

#### 🟢 حالت میانبر را فراموش نکنید:
```
https://www.youtube.com/watch?v=dfdXGw1xY9A v 1080
https://soundcloud.com/artist/track a 320
```

1. به **Actions** → **leecher** بروید
2. ورودی‌ها را وارد کنید (می‌توانید ترکیبی از لینک‌های میانبر و خام را با هم استفاده کنید)
3. خروجی‌ها به صورت زیپ شده در پوشه **`leecher/`** قرار می‌گیرند

---

### ۸. پاک‌کننده جامع (AIO Cleaner)

> 🔴 **اخطار: فضای مخزن GitHub محدودیت حدود ۵ گیگابایتی دارد! فایل‌های دانلودی به سرعت فضا را پر می‌کنند.**

این گردش کار به شما اجازه می‌دهد هر پلتفرم را با یک کلیک پاک کنید.

#### چه چیزهایی پاک می‌شوند:

| پلتفرم | آنچه حذف می‌شود |
|---------|-----------------|
| **تلگرام** | پوشه `telegram/content/` (رسانه‌ها) و فایل `telegram.md` (بایگانی) و `telegram/last_ids.json` |
| **یوتیوب / جهانی** | کل پوشه `youtube/` |
| **اینستاگرام** | کل پوشه `instagram/` |
| **X (توییتر)** | کل پوشه `x/` |
| **وبسایت** | کل پوشه `website/` |
| **لیچر** | کل پوشه `leecher/` |
| **گوگل پلی** | کل پوشه `google-play/` |
| **دانلود مستقیم** | کل پوشه `direct/` |

#### نحوه اجرا:

1. به **Actions** → **aio-cleaner** بروید
2. روی **Run workflow** کلیک کنید
3. چک‌باکس‌های مورد نظر را تیک بزنید (یا **Clean ALL platforms** برای همه)
4. روی **Run workflow** کلیک کنید

> 🔴 **حذف دائمی است!** مطمئن شوید فایل‌های مهم را قبلاً دانلود و ذخیره کرده‌اید.

---

### ۹. دانلودر گوگل پلی (APK)

📱 **فایل‌های APK اندروید را مستقیماً از گوگل پلی دانلود کنید!**  
این گردش‌کار از ابزار `gplay-apk-downloader` برای دانلود قانونی و رسمی بسته‌های نصبی (APK) از سرورهای گوگل استفاده می‌کند — بدون نیاز به دستگاه اندروید، بدون نیاز به اکانت گوگل، و کاملاً خودکار.

#### ✨ ویژگی‌ها:
- دانلود APK مستقیماً از سرورهای رسمی گوگل پلی
- پشتیبانی از معماری‌های **arm64** (پیش‌فرض) و **armv7**
- قابلیت ادغام خودکار APKهای Split (جداشده) در یک فایل نصبی واحد (merge_splits)
- فایل‌های بزرگتر از ۹۹MB به صورت ZIP چندبخشی ذخیره می‌شوند
- احراز هویت گوگل پلی به‌صورت خودکار توسط ابزار انجام می‌شود

#### 📝 نحوه استفاده:

1. به **Actions** → **google-play-downloader** بروید
2. روی **Run workflow** کلیک کنید
3. فیلدها را پر کنید:

| فیلد | توضیح | اجباری؟ |
|------|-------|---------|
| **app** | آدرس Google Play یا نام پکیج (مثلاً `com.google.android.youtube` یا `https://play.google.com/store/apps/details?id=org.telegram.messenger`) | ✅ بله |
| **architecture** | معماری دستگاه هدف: `arm64` (پیش‌فرض) یا `armv7` | ✅ بله |
| **merge_splits** | ادغام APKهای Split شده در یک فایل؟ (پیش‌فرض: فعال) | ❌ اختیاری |

**مثال‌ها:**
```
app: com.google.android.youtube
architecture: arm64
merge_splits: true
```

```
app: https://play.google.com/store/apps/details?id=com.spotify.music
architecture: armv7
merge_splits: false
```

4. روی **Run workflow** کلیک کنید → فایل‌های APK (ZIP شده) در پوشه **`google-play/`** قرار می‌گیرند

#### 🔍 چگونه نام پکیج یک برنامه را پیدا کنیم؟

1. به صفحه برنامه در **Google Play Store** بروید (مثلاً `play.google.com/store/apps/details?id=com.google.android.youtube`)
2. به بخش `id=` در URL نگاه کنید — همان نام پکیج است
3. یا از وب‌سایت‌هایی مثل [APKMirror](https://www.apkmirror.com) یا [APKPure](https://apkpure.com) نام پکیج را جستجو کنید

> ⚠️ **توجه:** گاهی مرحله احراز هویت گوگل پلی ممکن است چند دقیقه طول بکشد. اگر گردش‌کار در مرحله **generate random identifier** ماند، صبور باشید — این بخشی از فرآیند عادی است.

> ℹ️ این گردش‌کار فایل‌های APK را مستقیماً از سرورهای گوگل دریافت می‌کند، بنابراین نسخه‌های دریافتی رسمی و دست‌نخورده هستند.

---

### ۱۰. MHRV خروجی VPS (Exit Node) 🆕

🔐 **یک Exit Node کامل از نوع VPS برای پروژه MasterHttpRelayVPN روی GitHub Actions اجرا کنید!**

این گردش‌کار یک سرور رله HTTP روی پورت 8181 اجرا می‌کند، آن را با **cloudflared tunnel** از طریق **trycloudflare.com** به صورت امن در معرض اینترنت قرار می‌دهد، و یک URL عمومی موقت تولید می‌کند که می‌توانید مستقیماً در `config.json` پروژه **MasterHttpRelayVPN** به عنوان `exit_node` استفاده کنید.

#### ✨ ویژگی‌ها:
- 🐍 سرور رله Python کاملاً مستقل (بدون نیاز به VPS شخصی)
- 🔒 احراز هویت با **Pre-Shared Key (PSK)** — بدون رمز معتبر، هیچ درخواستی پردازش نمی‌شود
- 🌐 تونل امن Cloudflare با HTTPS رایگان (trycloudflare)
- ⏱️ اجرای ۶ ساعته (حداکثر زمان GitHub Actions)
- 🛡️ محافظت در برابر SSRF — فقط URLهای عمومی (http/https) قابل relay هستند
- 🔄 پراکسی کامل HTTP با پشتیبانی از تمام متدها و هدرهای استاندارد

#### 📝 نحوه استفاده:

##### گام اول: تنظیم Secret
1. به **Settings** → **Secrets and variables** → **Actions** بروید
2. یک **New repository secret** با نام **`TUNNEL_AUTH_KEY`** بسازید
3. یک **رمز قوی و طولانی** (PSK) به‌دلخواه خود وارد کنید (مثلاً: `MyStr0ng!RandomP@ssphrase2026`)

> 🔴 **مهم:** این رمز باید دقیقاً با `psk` (برای exit node) یا `auth_key` (در config.json) در پروژه **MasterHttpRelayVPN** شما یکسان باشد.  
> مسیر در config.json:  
> `"exit_node": { "enabled": true, "provider": "vps", "url": "URL_دریافتی_از_گردشکار", "psk": "همان_رمز_TUNNEL_AUTH_KEY" }`

##### گام دوم: اجرای گردش‌کار
1. به **Actions** → **mhrv-vps-exit-node-actions** بروید
2. روی **Run workflow** کلیک کنید
3. منتظر بمانید تا گردش‌کار اجرا شود (حدود ۲۰–۳۰ ثانیه)

##### گام سوم: دریافت URL
در لاگ گردش‌کار، خطی مشابه زیر ظاهر می‌شود:
```
https://random-name.trycloudflare.com
```
این URL خروجی نود شماست — آن را کپی کنید.

##### گام چهارم: تنظیم در MasterHttpRelayVPN

فایل `config.json` پروژه MasterHttpRelayVPN خود را باز کنید و بخش `exit_node` را به این صورت تنظیم کنید:

```
"exit_node": {
  "enabled": true,
  "provider": "vps",
  "url": "https://random-name.trycloudflare.com",
  "psk": "MyStr0ng!RandomP@ssphrase2026",
  "mode": "full",
  "hosts": ["chatgpt.com", "openai.com", "claude.ai", "anthropic.com"]
}
```

| فیلد | مقدار |
|-------|--------|
| `provider` | `"vps"` (چون این Exit Node از نوع VPS است) |
| `url` | همان URL که از لاگ گردش‌کار دریافت کردید |
| `psk` | **دقیقاً** همان رمزی که در Secret `TUNNEL_AUTH_KEY` تنظیم کردید |
| `mode` | `"full"` (همه ترافیک از exit node عبور کند) یا `"selective"` (فقط hostهای مشخص‌شده) |

#### ⚙️ معماری فنی (چه اتفاقی می‌افتد؟)

1. **python-exit-node.py** یک سرور HTTP روی `127.0.0.1:8181` راه‌اندازی می‌کند
2. **cloudflared** یک تونل امن بین سرور محلی و شبکه Cloudflare ایجاد می‌کند
3. یک URL موقت trycloudflare (HTTPS) به کاربر داده می‌شود
4. درخواست‌های MasterHttpRelayVPN به این URL می‌رسد، cloudflared آن را به پورت 8181 فوروارد می‌کند
5. سرور Python درخواست را احراز هویت کرده (با PSK) و به مقصد نهایی relay می‌کند

#### ⚠️ هشدارها و نکات مهم:

| نکته | توضیح |
|------|--------|
| 🔴 **مدت اعتبار** | حداکثر ۶ ساعت — بعد از آن نیاز به اجرای مجدد دارد |
| 🟡 **URL موقت** | trycloudflare URLها موقت هستند و هر اجرا یک URL جدید تولید می‌کند |
| 🔴 **امنیت PSK** | **هرگز** URL خروجی و PSK را با هم جایی عمومی منتشر نکنید |
| 🟡 **محدودیت پهنای باند** | GitHub Actions پهنای باند محدودی دارد — برای استفاده سنگین مناسب نیست |
| 🟢 **بدون نیاز به کوکی** | فقط به `TUNNEL_AUTH_KEY` نیاز دارد |

#### 🔧 رفع اشکال:

| خطا | علت احتمالی | راه حل |
|------|-------------|--------|
| `unauthorized` در لاگ | PSK اشتباه است | مطمئن شوید `psk` در config.json دقیقاً با `TUNNEL_AUTH_KEY` یکسان است |
| `server_psk_missing` | Secret تنظیم نشده | `TUNNEL_AUTH_KEY` را در Secrets بسازید |
| URL ظاهر نمی‌شود | cloudflared راه‌اندازی نشده | گردش‌کار را دوباره اجرا کنید |
| `bad_url` | URL نامعتبر یا خصوصی | فقط URLهای عمومی http/https قابل relay هستند |

---

## ⏱️ محدودیت‌ها و هشدارهای مهم

| هشدار | توضیح |
|-------|--------|
| 🔴 **محدودیت فضای مخزن** | حساب رایگان GitHub تا حدود **۵ گیگابایت** فضای نرم دارد. فایل‌های دانلودی (مخصوصاً ویدیوها و APKها) می‌توانند به سرعت فضا را پر کنند. فایل‌های خیلی بزرگ (مثلاً ۴.۳ گیگابایت) به ده‌ها پارت ZIP تبدیل می‌شوند و ممکن است push با خطا مواجه شود. **مرتباً از AIO Cleaner استفاده کنید و حجم مخزن را زیر ۵ گیگابایت نگه دارید!** |
| 🟠 **زمان اجرا** | حداکثر ۶ ساعت برای هر اجرا (مخازن عمومی دقیقه نامحدود دارند) |
| 🟡 **فایل‌های >۹۹MB** | به ZIP چندبخشی تقسیم می‌شوند — برای استخراج از 7‑Zip یا WinRAR استفاده کنید |
| 🟡 **دسته‌های بزرگ** | لینک‌های خیلی زیاد را به گروه‌های کوچکتر تقسیم کنید |
| 🔴 **دانلودر X** | **حتماً** به کوکی نیاز دارد |
| 🟢 **آرشیو تلگرام** | فقط کانال‌های **عمومی** — کانال‌های خصوصی قابل دسترسی نیستند |
| 🟢 **ضبط وبسایت** | فقط سایت‌های عمومی (بدون دیوار ورود) |
| 🔴 **نام کانال تلگرام** | **بدون @** وارد کنید |
| 🟠 **اجرای زمان‌بندی تلگرام** | ممکن است با تأخیر ۱ تا ۶ ساعت اجرا شود. برای دریافت سریع‌تر، اجرای دستی قابل اعتمادتر است |
| 🔴 **کوکی‌ها** | فقط از **پنجره ناشناس/خصوصی** استخراج کنید و بعد از استخراج، آن پنجره را کاملاً ببندید. کوکی‌های منقضی باعث خطای Sign in to confirm you're not a bot (یوتیوب) یا 429 Too Many Requests (اینستاگرام) می‌شوند |
| 🟢 **گوگل پلی** | بدون نیاز به اکانت گوگل — احراز هویت خودکار است |
| 🔴 **ساخت خودکار پوشه‌ها** | پوشه‌های خروجی (مثل `youtube/`, `leecher/`, `direct/` و غیره) بعد از اولین دانلود موفق **به‌صورت خودکار** ساخته می‌شوند. نیاز به ساخت دستی نیست! |
| 🟣 **MHRV Exit Node** | حداکثر ۶ ساعت — URL موقت trycloudflare — نیاز به `TUNNEL_AUTH_KEY` |

---

## 📄 فایل `zoomusers.md` چیست؟

فایل `zoomusers.md` یک راهنمای جداگانه برای **دور زدن تحریم‌ها و دسترسی به سرویس‌های گوگل** با استفاده از کلاینت **Clash Verge** (ویندوز و لینوکس) و **Clash Meta** (اندروید) است. این فایل شامل لینک‌های دانلود کلاینت، فایل‌های بکاپ کانفیگ، و آموزش گام‌به‌گام راه‌اندازی می‌باشد.

> ℹ️ این فایل ارتباطی با گردش‌کارهای دانلود ندارد و صرفاً یک راهنمای جانبی برای کاربران ایرانی است.

---

## 💬 پشتیبانی

**باگ یا پیشنهاد؟** یک [Issue](https://github.com/ProAlit/aio-downloader/issues) باز کنید. برای رسیدگی سریع‌تر، لطفاً این موارد را ذکر کنید:
- نام گردش کاری که اجرا کردید
- ورودی‌هایی که استفاده کردید (بدون کوکی‌هایتان!)
- پیام خطا یا لاگ (از تب Actions کپی کنید)

---

</div>

---

# 📖 English Guide

> **First things first:** If you just forked this repo, **strongly run the AIO Cleaner** to wipe any residual files (including Telegram archives and media from the original repo) and start completely fresh. (See section 8)

---

## 📋 Table of Contents

1. [Prerequisites](#-prerequisites-1)
2. [Fork & Initial Setup](#-fork--initial-setup-1)
3. [How to Extract & Add Cookies](#-how-to-extract--add-cookies-1)
4. [Complete Workflow Guide](#-complete-workflow-guide-1)
   - [1. YouTube Downloader (yt‑dlp Simple)](#1-youtube-downloader-yt-dlp--10-fallback-layers-)
   - [2. Instagram Downloader](#2-instagram-downloader-1)
   - [3. X (Twitter) Downloader](#3-x-twitter-downloader-1)
   - [4. Direct Downloader](#4-direct-downloader-1)
   - [5. Telegram Channel Archiver](#5-telegram-channel-archiver-1)
   - [6. Website Capture](#6-website-capture-1)
   - [7. Leecher – Shortcut + Raw Commands](#7-leecher--shortcut--raw-commands-1)
   - [8. AIO Cleaner](#8-aio-cleaner-1)
   - [9. Google Play APK Downloader](#9-google-play-apk-downloader-1)
   - [10. MHRV VPS Exit Node](#10-mhrv-vps-exit-node-)
5. [Limitations & Important Warnings](#-limitations--important-warnings-1)
6. [What is `zoomusers.md`?](#-what-is-zoomusersmd-1)

---

## ⚠️ Prerequisites

| Requirement | Description |
|-------------|-------------|
| 🟢 **GitHub Account** | Free — that's all you need |
| 🟠 **Browser + Get cookies.txt LOCALLY extension** | Chrome / Firefox / Edge |
| 🔵 **Instagram Account** | (Optional) for stories & private content |
| 🔴 **X (Twitter) Account** | **Mandatory** for the X downloader |
| 🟣 **Cloudflare Account** | (Optional) for MHRV Exit Node — needs **TUNNEL_AUTH_KEY** |
| 🟢 **Telegram, Website Capture, & Google Play** | Nothing extra needed — work without login or API keys |

---

## 🚀 Fork & Initial Setup

### Step 1: Fork the Repository
Click the **Fork** button at the top‑right of this page.

### Step 2: Enable GitHub Actions
1. Go to your forked repo → **Settings** → **Actions** → **General**
2. Under **Actions permissions**, select **Allow all actions and reusable workflows**
3. Click **Save**

### Step 3: Grant Workflow Write Permissions (CRITICAL!)
1. Same path → **Workflow permissions**
2. Select **Read and write permissions**
3. Click **Save**

> ⚠️ **If you skip this step, all workflows will fail when trying to upload files!**

### Step 4: Initial Cleanup (Highly Recommended!)
> 🧹 **Your forked repo contains Telegram archives and media from the original repo. To start with a clean slate, run the AIO Cleaner now for all platforms.**  
> Go to **Actions** → **aio-cleaner**, check **Clean ALL platforms**, and run it.  
> This will wipe everything so you can begin fresh.

### Step 5 (Optional): Set Secret for MHRV Exit Node
> If you plan to use the **MHRV VPS Exit Node** (section 10), create a Secret named **`TUNNEL_AUTH_KEY`** containing your PSK. This must match the `psk` or `auth_key` in your **MasterHttpRelayVPN** `config.json` exactly.

---

## 🍪 How to Extract & Add Cookies

> ℹ️ **YouTube & Instagram:** May require cookies for some content.  
> 🔴 **X (Twitter): Cookies are MANDATORY.**  
> 🟢 **Telegram, Website Capture, Google Play, & MHRV Exit Node:** No cookies needed.

### 1. Export Cookies from Your Browser – USE A PRIVATE/INCOGNITO WINDOW!

1. **Open a new Private/Incognito window** in your browser
2. Install the **Get cookies.txt LOCALLY** extension (Chrome Web Store or Firefox Add‑ons)
3. In that private window, log into **youtube.com** (for YouTube), **instagram.com** (for Instagram), or **x.com** (for X)
4. Click the extension icon and choose **Export** (Netscape format)
5. Save the `.txt` file somewhere safe
6. **Close the private window completely** — this ensures the exported session isn't kept open elsewhere

> 🔴 **Why a private window?** If you export cookies from a normal window and later log out, the cookies become invalid. Closing a private window ends the session while keeping the exported cookies valid.

> ⚠️ **Important Warning About Cookies:** Cookies expire or get invalidated over time. Signs of bad cookies:
> - **Sign in to confirm you're not a bot** error in YouTube downloads
> - **429 Too Many Requests** error in Instagram downloads
> - Download reports success but no file appears in the output folder
>
> In these cases, extract fresh cookies from a new private window and update the corresponding Secret.

### 2. Add Cookies as GitHub Secrets

1. In your forked repo, go to **Settings** → **Secrets and variables** → **Actions**
2. Click **New repository secret**
3. Create a secret named **`YOUTUBE_COOKIES`** and paste your YouTube `cookies.txt` content
4. Create a secret named **`INSTAGRAM_COOKIES`** and paste your Instagram `cookies.txt` content
5. Create a secret named **`X_COOKIES`** and paste your X (Twitter) `cookies.txt` content

> 🔴 **Never commit cookie files directly to the repository!** The workflow reads from secrets and cookies are never exposed in logs or code.

---

## 📦 Complete Workflow Guide

### 1. YouTube Downloader (yt‑dlp + 10 Fallback Layers) 🛡️

⚡ **Tank-mode YouTube!** This workflow is far more than a simple yt‑dlp call — it's built with **10 automatic fallback strategies** so if the primary method fails, it silently cycles through alternatives until something works.

#### ✨ New Powerful Features:

| Feature | Description |
|---------|-------------|
| 🟢 **Cookieless Operation** | Even without `YOUTUBE_COOKIES` set, the workflow tries yt‑dlp cookieless + 9 other methods |
| 🔄 **10 Automatic Fallbacks** | If the main download fails, it tries 10 different strategies one by one — no user intervention needed! |
| 📊 **Real-time Progress** | See download percentage and byte count as it downloads |
| 🎯 **Smart Quality Matching** | Finds the closest available resolution and FPS (even if your exact request doesn't exist) |
| 🔧 **Auto Remux** | Downloaded files are remuxed with ffmpeg for guaranteed playability |
| 📦 **Multi-part ZIP** | Files >99MB are automatically split into ZIP parts |
| 🌐 **Non-YouTube Links** | Direct URLs (non-YouTube) are also handled via wget |

#### 🧠 The 10 Fallback Layers — if plain yt‑dlp doesn't work:

| # | Strategy | Description |
|---|----------|-------------|
| 1 | `yt-dlp Android` | Simulates Android client (player_client=android) |
| 2 | `yt-dlp iOS` | Simulates iOS client |
| 3 | `yt-dlp No Cookies` | Attempts without any cookies at all |
| 4 | `youtube-dl` | Classic youtube-dl tool |
| 5 | `pytube (best)` | Python pytube library — best quality |
| 6 | `pytube (resolution)` | pytube with your requested resolution |
| 7 | `API loader.to` | External loader.to service |
| 8 | `API vevioz` | External api.vevioz.com service |
| 9 | `cobalt.tools` | cobalt.tools API (720p quality) |
| 10 | `yt-dlp IPv4 + retry` | yt‑dlp with forced IPv4 + 10 retries |

> 💡 **What does this mean?** If YouTube blocks the primary method, the workflow silently tries 10 completely different approaches until your file is downloaded — all without you lifting a finger. **This is the most resilient free YouTube downloader you'll see on GitHub Actions!**

#### 📝 How to Use (same as before):

1. Go to **Actions** → **youtube-downloader**
2. Click **Run workflow**
3. Enter your inputs. **Format:** `URL v/a resolution fps` (fps optional)

**Examples:**
```
https://www.youtube.com/watch?v=dfdXGw1xY9A v 480
https://www.youtube.com/watch?v=dfdXGw1xY9A v 1080 60
https://www.youtube.com/watch?v=dfdXGw1xY9A a max
https://www.youtube.com/watch?v=VIDEO_ID v 4k, https://www.youtube.com/watch?v=VIDEO_ID a 128
```

- `v` = video, `a` = audio
- Resolution: `max`, `min`, `1080`, `2k`, `4k`, etc.
- FPS: optional (e.g., `60`, `30`)
- If `v/a` is omitted, defaults to **video max quality**
- Maximum audio quality (`a max`) outputs in `.opus` format

4. Click **Run workflow** → output appears in **`youtube/`** folder (split ZIP for large files)

> 🟢 **Cookies are optional!** If you haven't set up `YOUTUBE_COOKIES` in Secrets, the workflow still works with cookieless yt‑dlp + all 9 other fallback layers. Adding cookies does improve success rates for layers 1 & 2 though.

---

### 2. Instagram Downloader

Downloads **all media** from posts, reels, stories, highlights, and profiles — including mixed carousels.

1. Go to **Actions** → **instagram-downloader**
2. Click **Run workflow**
3. Paste Instagram links — separated by commas, spaces, or newlines

**Example:**
```
https://www.instagram.com/p/DX2y7oLDFOb/, https://www.instagram.com/reel/DVRXhn0gjL3/, https://www.instagram.com/p/DX6US4uCNGb/
```

4. Click **Run workflow** → ZIP appears in the **`instagram/`** folder (up to 10+ links bundled in one ZIP)

> ⚠️ **Warning about 429 Error:** If you get a **429 Too Many Requests** error, your Instagram cookies are likely expired or rate-limited. Extract fresh cookies from a new private window and update `INSTAGRAM_COOKIES`.

---

### 3. X (Twitter) Downloader

Downloads **all media** (images, videos) from tweets and profiles.

> 🔴 **`X_COOKIES` secret is mandatory!**

1. Go to **Actions** → **x-downloader**
2. Click **Run workflow**
3. Paste X links — separated by commas, spaces, or newlines

**Example:**
```
https://x.com/username/status/123456789, https://x.com/otheruser/status/987654321
```

4. Click **Run workflow** → ZIP appears in the **`x/`** folder

---

### 4. Direct Downloader

Downloads **any file** from a direct URL using `aria2c` (16 parallel connections — ultra‑fast).

1. Go to **Actions** → **direct-downloader**
2. Click **Run workflow**
3. Paste direct download URLs (e.g., `.zip`, `.mp4`, `.apk`, `.pdf`), separated by commas, spaces, or newlines

**Example:**
```
https://example.com/path/to/large-file.zip, https://example.com/another-file.mp4
```

4. Click **Run workflow** → files appear in **`direct/`** (split into 99 MB parts if needed)

> ℹ️ **Note:** To prevent conflicts with previous downloads, a random 5-character suffix is added to each filename. This lets you re-download the same file without errors.

---

### 5. Telegram Channel Archiver

Scrapes **public Telegram channels** and stores messages, photos, videos, and documents as a Markdown archive.  
Runs **automatically every 15 minutes** or **manually on demand**.

> 📡 **Live Example:**  
> The original repository maintains a **live archive of Telegram news channels**, refreshed automatically **every 10 minutes**.  
> To view the latest news and media, open the file here:  
> **[telegram.md on the original repo](https://github.com/ProAlit/aio-downloader/blob/main/telegram.md)**  
> *This file is not updated in your fork unless you activate the Telegram workflow on your own copy.*

> 🟢 **No API key or cookies needed!**

> ⏱️ **Automatic cron delay:** GitHub does not guarantee exact 15‑minute intervals. Delays of 1 to 6 hours between runs are common. For real‑time updates, use manual trigger or set up an external cron job if you're experienced.

#### How It Works (Step by Step)

1. Reads your channel list from `telegram/channels.json`
2. Launches Chromium (Playwright) and visits `https://t.me/s/`
3. Scrolls to fetch new messages since the last check
4. Extracts message text, UTC times, photos (CSS background‑url), videos, and documents
5. Downloads all media into `telegram/content/`
6. Converts UTC times to Iran/Tehran timezone and Jalali (Hijri‑Shamsi) calendar
7. Sorts all messages from newest to oldest
8. Writes to `telegram.md` with Markdown formatting (Vazirmatn font, RTL)
9. Saves last message IDs in `telegram/last_ids.json`
10. Commits and pushes (with a 5‑retry loop)

#### 📋 Viewing Your Archive

Open `telegram.md` in your repository. GitHub renders Markdown natively — you'll see formatted text with quotes, embedded images, and clickable video links. Dates are in Jalali calendar with Tehran timezone.

#### ➕ Add or Remove Channels

Edit `telegram/channels.json` directly on GitHub (click the pencil icon ✏️).

> 🔴 **Channel names must be WITHOUT the @ symbol!**
>
> ❌ `@channelname` — incorrect
> ✅ `channelname` — correct

**Example:**
```
["VahidOOnLine", "mwarmonitor", "pm_afshaa", "iaghapour", "DEJradio", "mamlekate", "kianmeli1"]
```

> ⚠️ Only **public** channels work. Private channels cannot be accessed.

#### ▶️ Manual Trigger

1. **Actions** → **telegram-fetcher**
2. **Run workflow** → **Run workflow**

---

### 6. Website Capture

Turns any **public website** into a single, polished A4 PDF document. Uses **Playwright + Chromium** to render pages exactly like a real user — including JavaScript, CSS, images, and dynamic content.

#### How to Use

1. Go to **Actions** → **website-capture**
2. Click **Run workflow**
3. Enter the full URL (must start with `https://`)

**Examples:**
```
https://example.com/article/my-post
https://developer.mozilla.org/en-US/docs/Web/JavaScript
https://github.com/ProAlit/aio-downloader
```

4. Click **Run workflow** → within 5–10 minutes, the PDF appears in the **`website/`** folder

> ⚠️ **Limitations:**
> - Only public sites (no login walls)
> - Up to 500 internal links extracted
> - 30‑minute timeout for the entire process
> - JavaScript‑heavy single‑page apps may not render perfectly
> - No cookies needed!

---

### 7. Leecher – Shortcut + Raw Commands

💥 **The most powerful workflow in this repo!**  
Leecher fully harnesses `yt-dlp`, so you can throw almost **any link** at it — YouTube, Twitter, Instagram, TikTok, Pinterest, SoundCloud, Spotify, and **over 1,800 other sites**.  
You are not limited to YouTube, nor to predefined settings. **You're in full control.**

#### Two ways to use it:

- **🟢 Shortcut Mode:** Just like the YouTube downloader — using the format `URL v/a resolution fps` (quick and simple for YouTube and similar)
- **🔴 Raw Mode:** Limitless power — append `--` after the URL and pass any valid `yt-dlp` option directly. This means you can manually set formats, cookies, subtitles, archive, playlists, rate limits, and more.

---

#### 🎯 Examples showcasing Leecher's power (Raw mode)

| Platform | Example command (paste into workflow input) |
|----------|----------------------------------------------|
| **YouTube** – 1080p video + English subs | `https://www.youtube.com/watch?v=VIDEO_ID -- --format "best[height<=1080]" --sub-lang en --write-subs // https://www.youtube.com/watch?v=VIDEO_ID v 480/720/1080` |
| **Instagram** – Download post/reel (with cookies) | `https://www.instagram.com/p/CODE -- --cookies cookies.txt --output "%(title)s.%(ext)s"` |
| **TikTok** – Download video & captions | `https://www.tiktok.com/@user/video/ID -- --write-subs --sub-lang en` |
| **Twitter / X** – Best available resolution | `https://x.com/user/status/ID -- --format best` |
| **Pinterest** – Get the image | `https://www.pinterest.com/pin/ID -- --format best` |
| **SoundCloud** – Extract original audio | `https://soundcloud.com/artist/track -- --format bestaudio` |
| **Spotify** – (metadata) | `https://open.spotify.com/track/ID -- --print "%(title)s - %(artist)s"` |
| **Vimeo** – Download with custom resolution | `https://vimeo.com/ID -- --format "best[height<=720]"` |
| **Dailymotion** – Download video | `https://www.dailymotion.com/video/ID -- --format best` |
| **Telegram (public link)** – Grab file from public channel | `https://t.me/channel/12345 -- --format best` |
| **Porn Downloader** – All Porn Websites | `Link To Video v 480/720/1080` |

> ℹ️ **Note:** For sites like Instagram and TikTok that require cookies, first add your cookies to Secrets (section 3) and then include `--cookies /path/to/cookies.txt`. Leecher automatically reads the cookie secret and saves it in the expected location.

#### 🟢 Don't forget Shortcut Mode:
```
https://www.youtube.com/watch?v=dfdXGw1xY9A v 1080
https://soundcloud.com/artist/track a 320
```

1. Go to **Actions** → **leecher**
2. Enter your inputs (you can mix shortcut and raw links in the same run)
3. Outputs appear as ZIP files in the **`leecher/`** folder

---

### 8. AIO Cleaner

> 🔴 **Warning: GitHub repos have a ~5 GB soft limit! Downloaded files can eat up space fast.**

This workflow lets you wipe downloads for any platform with one click.

#### What Gets Cleaned:

| Platform | What Gets Deleted |
|----------|-------------------|
| **Telegram** | `telegram/content/` folder (media), `telegram.md` (archive), `telegram/last_ids.json` |
| **YouTube / Universal** | Entire `youtube/` folder |
| **Instagram** | Entire `instagram/` folder |
| **X (Twitter)** | Entire `x/` folder |
| **Website** | Entire `website/` folder |
| **Leecher** | Entire `leecher/` folder |
| **Google Play** | Entire `google-play/` folder |
| **Direct Download** | Entire `direct/` folder |

#### How to Run:

1. Go to **Actions** → **aio-cleaner**
2. Click **Run workflow**
3. Check the boxes you want (or **Clean ALL platforms** for everything)
4. Click **Run workflow**

> 🔴 **Deletion is permanent!** Make sure you've downloaded important files beforehand.

---

### 9. Google Play APK Downloader

📱 **Download Android APK files directly from Google Play!**  
This workflow uses the `gplay-apk-downloader` tool to legally fetch installable packages (APKs) from Google's official servers — no Android device needed, no Google account required, fully automated.

#### ✨ Features:
- Downloads APKs directly from Google's official servers
- Supports **arm64** (default) and **armv7** architectures
- Automatically merges Split APKs into a single installable file (`merge_splits`)
- Files larger than 99 MB are split into multi‑part ZIP archives
- Google Play authentication is handled automatically by the tool

#### 📝 How to Use:

1. Go to **Actions** → **google-play-downloader**
2. Click **Run workflow**
3. Fill in the fields:

| Field | Description | Required? |
|-------|-------------|-----------|
| **app** | Google Play URL or package name (e.g., `com.google.android.youtube` or `https://play.google.com/store/apps/details?id=org.telegram.messenger`) | ✅ Yes |
| **architecture** | Target device architecture: `arm64` (default) or `armv7` | ✅ Yes |
| **merge_splits** | Merge split APKs into one file? (default: enabled) | ❌ Optional |

**Examples:**
```
app: com.google.android.youtube
architecture: arm64
merge_splits: true
```

```
app: https://play.google.com/store/apps/details?id=com.spotify.music
architecture: armv7
merge_splits: false
```

4. Click **Run workflow** → APK files (zipped) appear in the **`google-play/`** folder

#### 🔍 How to Find an App's Package Name:

1. Go to the app's page on the **Google Play Store** (e.g., `play.google.com/store/apps/details?id=com.google.android.youtube`)
2. Look at the `id=` part in the URL — that's the package name
3. Alternatively, use sites like [APKMirror](https://www.apkmirror.com) or [APKPure](https://apkpure.com) to search for the package name

> ⚠️ **Note:** The Google Play authentication step may take a few minutes. If the workflow appears stuck at **generate random identifier**, be patient — this is part of the normal process.

> ℹ️ This workflow fetches APK files directly from Google's servers, so the downloads are official and unmodified.

---

### 10. MHRV VPS Exit Node 🆕

🔐 **Run a full VPS-type Exit Node for the MasterHttpRelayVPN project, right on GitHub Actions!**

This workflow starts an HTTP relay server on port 8181, exposes it securely to the internet via a **cloudflared tunnel** through **trycloudflare.com**, and produces a temporary public URL that you can plug directly into your **MasterHttpRelayVPN** `config.json` as an `exit_node`.

#### ✨ Features:
- 🐍 Fully self-contained Python relay server (no personal VPS needed)
- 🔒 **Pre-Shared Key (PSK)** authentication — no requests honored without the correct key
- 🌐 Secure Cloudflare tunnel with free HTTPS (trycloudflare)
- ⏱️ 6‑hour runtime (maximum GitHub Actions job duration)
- 🛡️ SSRF protection — only public http/https URLs can be relayed
- 🔄 Full HTTP proxy with support for all standard methods and headers

#### 📝 How to Use:

##### Step 1: Set the Secret
1. Go to **Settings** → **Secrets and variables** → **Actions**
2. Create a **New repository secret** named **`TUNNEL_AUTH_KEY`**
3. Set a **strong, random PSK** (e.g., `MyStr0ng!RandomP@ssphrase2026`)

> 🔴 **Critical:** This PSK must **exactly match** the `psk` (for exit node) or `auth_key` in your **MasterHttpRelayVPN** `config.json`.  
> Path in config.json:  
> `"exit_node": { "enabled": true, "provider": "vps", "url": "URL_FROM_WORKFLOW", "psk": "SAME_AS_TUNNEL_AUTH_KEY" }`

##### Step 2: Run the Workflow
1. Go to **Actions** → **mhrv-vps-exit-node-actions**
2. Click **Run workflow**
3. Wait for it to start (~20–30 seconds)

##### Step 3: Get Your URL
In the workflow log, you will see a line like:
```
https://random-name.trycloudflare.com
```
This is your exit node URL — copy it.

##### Step 4: Configure MasterHttpRelayVPN

Open your MasterHttpRelayVPN `config.json` and configure the `exit_node` section:

```
"exit_node": {
  "enabled": true,
  "provider": "vps",
  "url": "https://random-name.trycloudflare.com",
  "psk": "MyStr0ng!RandomP@ssphrase2026",
  "mode": "full",
  "hosts": ["chatgpt.com", "openai.com", "claude.ai", "anthropic.com"]
}
```

| Field | Value |
|-------|--------|
| `provider` | `"vps"` (because this exit node is of VPS type) |
| `url` | The URL you copied from the workflow log |
| `psk` | **Exactly** the same PSK you set in `TUNNEL_AUTH_KEY` |
| `mode` | `"full"` (all traffic via exit node) or `"selective"` (only listed hosts) |

#### ⚙️ Technical Architecture (What Happens)

1. **python-exit-node.py** starts an HTTP server on `127.0.0.1:8181`
2. **cloudflared** creates a secure tunnel between the local server and Cloudflare's edge
3. A temporary trycloudflare URL (HTTPS) is exposed to the world
4. MasterHttpRelayVPN requests arrive at this URL, cloudflared forwards them to port 8181
5. The Python server authenticates the request (via PSK) and relays it to the target destination

#### ⚠️ Warnings & Important Notes:

| Note | Description |
|------|-------------|
| 🔴 **Validity Period** | Max 6 hours — needs re-execution afterwards |
| 🟡 **Temporary URL** | trycloudflare URLs are ephemeral; each run produces a new one |
| 🔴 **PSK Security** | **Never** share the exit node URL together with a valid PSK |
| 🟡 **Bandwidth Limits** | GitHub Actions has limited bandwidth — not suitable for heavy usage |
| 🟢 **No Cookies Needed** | Only requires `TUNNEL_AUTH_KEY` |

#### 🔧 Troubleshooting:

| Error | Likely Cause | Fix |
|-------|-------------|-----|
| `unauthorized` in logs | Mismatched PSK | Ensure `psk` in config.json exactly matches `TUNNEL_AUTH_KEY` |
| `server_psk_missing` | Secret not set | Create `TUNNEL_AUTH_KEY` in Secrets |
| No URL appears | cloudflared didn't start | Re-run the workflow |
| `bad_url` | Invalid or private URL | Only public http/https URLs can be relayed |

---

## ⏱️ Limitations & Important Warnings

| Warning | Description |
|---------|-------------|
| 🔴 **Repository Size Limit** | GitHub free accounts have a ~5 GB soft limit. Downloaded files (especially videos and APKs) can fill this up quickly. Very large files (e.g., 4.3 GB) become dozens of ZIP parts and may fail to push. **Use AIO Cleaner regularly and keep total repo size under 5 GB!** |
| 🟠 **Runtime** | Max 6 hours per job (public repos have unlimited minutes) |
| 🟡 **Files >99 MB** | Split into multi‑part ZIPs — use 7‑Zip or WinRAR to extract |
| 🟡 **Large Batches** | Split very large batches into smaller groups |
| 🔴 **X Downloader** | **Requires** cookies — won't work without `X_COOKIES` |
| 🟢 **Telegram Archive** | Only **public** channels — private channels cannot be accessed |
| 🟢 **Website Capture** | Only public sites (no login walls) |
| 🔴 **Telegram Channel Names** | Must be **without @** |
| 🟠 **Telegram Cron** | May experience delays of 1–6 hours. Manual trigger is more reliable |
| 🔴 **Cookies** | Only export from a **Private/Incognito window** — close that window completely after exporting. Expired cookies cause **Sign in to confirm you're not a bot** (YouTube) or **429 Too Many Requests** (Instagram) |
| 🟢 **Google Play** | No Google account needed — authentication is automatic |
| 🔴 **Folder Auto-Creation** | Output folders (e.g., `youtube/`, `leecher/`, `direct/`, etc.) are **automatically created** after the first successful download. No need to create them manually! |
| 🟣 **MHRV Exit Node** | Max 6 hours — temporary trycloudflare URL — requires `TUNNEL_AUTH_KEY` |

---

## 📄 What is `zoomusers.md`?

The `zoomusers.md` file is a separate guide for **bypassing internet restrictions and accessing Google services** using the **Clash Verge** client (Windows & Linux) and **Clash Meta** (Android). It includes download links, config backup files, and step‑by‑step setup instructions.

> ℹ️ This file is unrelated to the download workflows — it's a bonus guide for Iranian users.

---

## 💬 Support

⭐ **If this project helps you, please star the repo — it helps others find it!**

**Bug or suggestion?** Open an [Issue](https://github.com/ProAlit/aio-downloader/issues). For faster resolution, please include:
- The workflow name you ran
- The inputs you used (without your cookies!)
- Error message or log (copy from the Actions tab)
