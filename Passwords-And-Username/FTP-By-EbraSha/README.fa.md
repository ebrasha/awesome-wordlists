<!-- 
**********************************************************************
 Project Name : FTP Penetration Testing Wordlists
 File Name    : README.fa.md
 Maintainer   : Ebrahim Shafiei (EbraSha)
 Email        : Prof.Shafiei@Gmail.com
 Created On   : 2026-05-25 08:00:46
 Description  : Persian (Farsi) documentation for the FTP penetration
                testing wordlists (usernames & passwords) crafted for
                authorized FTP / FTPS / SFTP security assessments.
**********************************************************************
-->

<div align="right">

> 🌐 **مطالعه به زبان شما:** 🇬🇧 [English](README.md) | 🇮🇷 [فارسی](README.fa.md)

</div>

<p align="right">
  <img src="shot.png" alt="پیش‌نمایش وردلیست FTP" align="right" />
</p>

<div dir="rtl">

# 📂 وردلیست تست نفوذ FTP — محتمل‌ترین نام‌های کاربری و رمزهای عبور برای Brute Force روی vsftpd، ProFTPD، Pure-FTPd، FileZilla Server، IIS FTP و هاستینگ اشتراکی

### 👤 ابراهیم شفیعی (EbraSha) 🇮🇷

یک پک وردلیست دقیق، واقع‌گرا و با سیگنال بالا، طراحی‌شده به‌طور اختصاصی برای تست نفوذ **مجاز** سرویس‌های **FTP، FTPS و SFTP** روی پورت `21` (و `990`، `2121` و پورت‌های دلخواه). این وردلیست بر اساس دیتاست‌های لو رفته، پسوردهای پیش‌فرض وندورها، الگوهای پنل‌های هاستینگ اشتراکی، قراردادهای Anonymous Login و رایج‌ترین عادت‌های Webmaster و SysAdmin در محیط‌های Production ساخته شده است.

---

## 📌 چرا این پروژه ساخته شد؟

اکثر وردلیست‌های عمومی **بسیار بزرگ و عمومی** هستند و ویژگی‌های منحصربه‌فرد FTP را در نظر نمی‌گیرند:

- **Anonymous Login** از نظر تاریخی یک پسورد شبه-ایمیل می‌خواهد، نه یک رشتهٔ پسورد معمولی.
- **هاستینگ اشتراکی** (cPanel، Plesk، DirectAdmin، ISPConfig) کاربران FTP را با اسم‌های قابل پیش‌بینی مرتبط با دامنه می‌سازد.
- **fail2ban + CSF** روی اکثر هاست‌های Production پس از چند تلاش ناموفق، IP منبع را Ban می‌کنند.
- **Webmasterها** از مجموعهٔ کوچک و قابل پیش‌بینی از الگوهای مرتبط با سایت/دامنه/سال استفاده می‌کنند.

این پروژه **دو فایل کوچک، دقیق و با احتمال موفقیت بالا** ارائه می‌دهد — شانس موفقیت در هر درخواست را به حداکثر و احتمال شناسایی و Ban شدن را به حداقل می‌رساند.

---

## ✨ ویژگی‌ها و قابلیت‌ها

- 🎯 **اختصاصی FTP**: تنظیم‌شده برای vsftpd، ProFTPD، Pure-FTPd، FileZilla Server، Microsoft IIS FTP، WS_FTP، Serv-U.
- 🕵️ **آمادهٔ Anonymous Login**: شامل الگوهای کلاسیک `anonymous` / `anonymous@`، `IEUser@` و `mozilla@example.com`.
- 🌐 **اکانت‌های هاستینگ اشتراکی**: cPanel، WHM، Plesk، DirectAdmin، ISPConfig، Vesta، Webuzo، Ajenti.
- 🛒 **اکانت‌های اختصاصی CMS**: WordPress، Joomla، Drupal، Magento، OpenCart، PrestaShop، TYPO3، Moodle، Nextcloud، ownCloud، Seafile.
- 👥 **Webmaster و نقش‌محور**: `webmaster`, `webadmin`, `www-data`, `public_html`, `upload`, `backup`, `mirror`, `share`.
- 🏢 **الگوهای سازمانی**: رمزهای فصلی (`Summer2025!`)، فصلی-سه‌ماهه (`Q1@2026`) و ماهانه (`June2026`) از سیاست‌های Rotation.
- 🔣 **الگوهای Leetspeak و جایگزینی کاراکتر**: `P@55w0rd`, `4dm1n@123`, `r00t@123`.
- ⌨️ **رمزهای Keyboard-walk**: `1qaz2wsx`, `qweasdzxc`, `zaq1!QAZ`.
- 🌍 **اعتبارنامه‌های بومی‌سازی‌شده**: شامل رمزهای مرتبط با Iran/Tehran/Persia و الگوهای رایج اسامی فارسی.
- 📧 **Payloadهای دامنه‌محور**: الگوهای `admin@example.com`, `ftp@domain.com` که معمولاً به‌صورت پیش‌فرض اعمال می‌شوند.
- 📝 **سازگار با ابزارها**: کامنت‌ها با `#` شروع می‌شوند تا توسط Hydra، Medusa، NetExec، Patator و Ncrack نادیده گرفته شوند.

---

## 📁 فایل‌های این پک

| فایل | کاربرد |
|---|---|
| `ftp_usernames_by_ebrasha.txt` | اکانت‌های Anonymous، وندوری، پنل هاستینگ، CMS، نقش‌محور و ادمین |
| `ftp_passwords_by_ebrasha.txt` | رمزهای با احتمال بالای واقع‌گرا (شامل Payloadهای ایمیل‌مانند برای Anonymous) |

---

## 🚀 نحوهٔ استفاده

> ⚠️ **توقف**: این وردلیست‌ها را **فقط** علیه سیستم‌هایی استفاده کنید که **مالک آن‌ها هستید** یا **مجوز کتبی صریح** دارید.

### 🐉 Hydra (توصیه‌شده برای FTP)

</div>

```bash
hydra -L ftp_usernames_by_ebrasha.txt -P ftp_passwords_by_ebrasha.txt ftp://<target> -t 4 -W 5
```

<div dir="rtl">

### 🛡️ Ncrack

</div>

```bash
ncrack -vv --user ftp_usernames_by_ebrasha.txt -P ftp_passwords_by_ebrasha.txt ftp://<target>:21
```

<div dir="rtl">

### 🔧 Medusa

</div>

```bash
medusa -h <target> -U ftp_usernames_by_ebrasha.txt -P ftp_passwords_by_ebrasha.txt -M ftp
```

<div dir="rtl">

### 🧪 Patator (برای FTPS و پورت‌های دلخواه)

</div>

```bash
patator ftp_login host=<target> port=21 user=FILE0 password=FILE1 0=ftp_usernames_by_ebrasha.txt 1=ftp_passwords_by_ebrasha.txt -x ignore:mesg='Login incorrect'
```

<div dir="rtl">

### 🕵️ بررسی سریع Anonymous Login

</div>

```bash
nmap -p 21 --script ftp-anon <target>
```

<div dir="rtl">

### 💧 استراتژی توصیه‌شده

۱. **همیشه ابتدا Anonymous را تست کنید** — بسیاری از سرورهای FTP در محیط Production هنوز آن را قبول می‌کنند.  
۲. به جای Brute Force عمودی، از **Password Spraying** (یک پسورد روی همهٔ یوزرها) استفاده کنید.  
۳. در صورت مشکوک بودن به fail2ban، **حداقل ۵ ثانیه تأخیر** بین تلاش‌ها بگذارید.  
۴. روی هاستینگ اشتراکی، نام کاربری‌های مشتق از **نام دامنه** را در اولویت قرار دهید (مثل `example`, `exampleftp`, `example_user`).  
۵. کار را با **پیش‌فرض‌های وندورها و رمزهای فصلی** شروع کنید — بالاترین نرخ موفقیت را دارند.

---

## ⚠️ تذکر قانونی و اخلاقی

این وردلیست صرفاً برای تست امنیتی **مجاز**، عملیات Red Team، ارزیابی آسیب‌پذیری و پژوهش‌های آموزشی ارائه شده است. استفاده از آن بدون **مجوز کتبی صریح**، **غیرقانونی** است و ممکن است قوانین محلی، ملی و بین‌المللی را نقض کند.

با استفاده از این فایل، شما موافقت می‌کنید که:

۱. برای هر هدف، مجوز کتبی صریح در اختیار دارید.  
۲. مسئولیت کامل قانونی و اخلاقی استفاده را می‌پذیرید.  
۳. نگه‌دارنده (ابراهیم شفیعی) **هیچ‌گونه مسئولیتی** در قبال سوءاستفاده ندارد.

---

## 🐛 گزارش مشکلات

اگر با مشکلی مواجه شدید یا در پیکربندی مشکل دارید، لطفاً از طریق ایمیل Prof.Shafiei@Gmail.com با ما در تماس باشید. همچنین می‌توانید مشکلات را در GitHub گزارش دهید.

## ❤️ حمایت مالی

اگر این پروژه برای شما مفید بود و مایل به حمایت از توسعهٔ بیشتر هستید، لطفاً در نظر داشته باشید که کمک مالی کنید:

- [اینجا اهدا کنید](https://t.me/AbdalDonationBot)

## 🤵 نگه‌دارنده

با عشق ایجاد و نگهداری شده توسط **ابراهیم شفیعی (EbraSha)**

- **ایمیل**: Prof.Shafiei@Gmail.com
- **تلگرام**: [@ProfShafiei](https://t.me/ProfShafiei)

</div>
