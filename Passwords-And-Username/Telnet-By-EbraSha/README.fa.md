<!-- 
**********************************************************************
 Project Name : Telnet Penetration Testing Wordlists
 File Name    : README.fa.md
 Maintainer   : Ebrahim Shafiei (EbraSha)
 Email        : Prof.Shafiei@Gmail.com
 Created On   : 2026-05-25 08:00:46
 Description  : Persian (Farsi) documentation for the Telnet
                penetration testing wordlists (usernames & passwords)
                crafted for authorized IoT / router / camera / ICS /
                legacy Unix Telnet assessments.
**********************************************************************
-->

<div align="right">

> 🌐 **مطالعه به زبان شما:** 🇬🇧 [English](README.md) | 🇮🇷 [فارسی](README.fa.md)

</div>

<p align="right">
  <img src="shot.png" alt="پیش‌نمایش وردلیست Telnet" align="right" />
</p>

<div dir="rtl">

# 📡 وردلیست تست نفوذ Telnet — اعتبارنامه‌های با احتمال بالا برای Brute Force روی IoT، روتر، دوربین IP، DVR/NVR، ICS/SCADA، VoIP و Unix قدیمی

### 👤 ابراهیم شفیعی (EbraSha) 🇮🇷

یک پک وردلیست دقیق، واقع‌گرا و با سیگنال بالا، طراحی‌شده به‌طور اختصاصی برای تست نفوذ **مجاز** سرویس‌های **Telnet** روی پورت‌های `23`، `2323`، `4567`، `5555` و سایر پورت‌های Embedded. این وردلیست بر اساس **اعتبارنامه‌های Seed بات‌نت‌های Mirai / Mozi / Gafgyt**، دیتابیس پسوردهای پیش‌فرض وندورها، CVEهای عمومی و تست‌های نفوذ واقعی روی CPE مخابراتی، دوربین‌های IP، DVR/NVR، سوییچ‌ها، تلفن‌های VoIP، کنسول‌های ICS/SCADA و هاست‌های قدیمی Unix ساخته شده است.

---

## 📌 چرا این پروژه ساخته شد؟

Telnet **بزرگ‌ترین Attack Surface در دنیای IoT** است و رفتاری کاملاً متفاوت با SSH یا RDP دارد:

- **هیچ‌گونه رمزنگاری Transport** ندارد — اعتبارنامه‌ها به‌صورت Cleartext روی سیم منتقل می‌شوند.
- **بدون Lockout Native** روی اکثر فریمور Embedded — Brute Force محدودیتی ندارد اما می‌تواند **دستگاه را Crash کند** (DoS).
- **در معرض گستردهٔ پیش‌فرض‌های وندوری** — اکثر IoT/CPE/CCTV با Factory Creds ارسال می‌شود که هرگز تغییر نمی‌کند.
- **تاریخچهٔ بات‌نت‌ها** — بدافزارهای رده Mirai سال‌هاست همان ۶۰ جفت اعتبارنامه را سلاح‌سازی می‌کنند و هنوز در ۲۰۲۶ روی میلیون‌ها دستگاه کار می‌کنند.

این پروژه **دو فایل کوچک، دقیق و با احتمال موفقیت بالا** ارائه می‌دهد که از جدول `scanner.c` بدافزار Mirai، دیتابیس‌های پسورد پیش‌فرض (RouterPasswords، DefaultPassword.us، ICS-CERT) و تست‌های نفوذ واقعی جمع‌آوری شده‌اند.

---

## ✨ ویژگی‌ها و قابلیت‌ها

- 🎯 **اختصاصی Telnet**: تنظیم‌شده برای BusyBox Embedded، Cisco IOS، JunOS، MikroTik RouterOS، Huawei VRP، ZTE ZXR/ZXA، ZyXEL ZyNOS، OpenWrt و BSD/Unix قدیمی.
- 🦠 **اعتبارنامه‌های Seed بات‌نت‌ها**: `root:xc3511`, `root:vizxv`, `root:xmhdipc`, `root:juantech`, `root:jvbzd`, `root:7ujMko0admin`, `root:hi3518`, `root:hi3520`, `root:hi3531`, `root:hi3535`, `root:klv123`, `root:Zte521`, `root:zlxx` و ده‌ها مورد دیگر.
- 📡 **پیش‌فرض‌های CPE مخابراتی**: Huawei (HG532، HG658، HG8245، EchoLife)، ZTE (ZXHN، ZXDSL)، Calix، Sumitomo، Telkom، AdminTelecom؛ پسوردهای Rebrand رایج ISPها مثل `admin/admin@huawei.com`, `admin/W@ifi-default`, `admin/ALC#FGU`.
- 📷 **دوربین IP و DVR**: Hikvision، Dahua، Foscam، Axis، Mobotix، Bosch، Sony، Panasonic، Vivotek، Acti، GeoVision، TVT، HiSilicon، XMEye — تمام Factory Credهای شناخته‌شده.
- 🌐 **روتر/سوییچ/AP**: Cisco (شامل `enable secret`)، Juniper، MikroTik، Ubiquiti/UniFi، EdgeMAX، TP-Link، D-Link، Netgear، Linksys، ASUS، Belkin، TrendNet، ZyXEL، Buffalo.
- 🏭 **ICS / SCADA / OT**: Siemens (SIMATIC، S7)، Allen-Bradley/Rockwell، Modicon/Schneider، Omron، Mitsubishi، ABB، Honeywell، Yokogawa، GE، Emerson — فقط برای ارزیابی‌های **مجاز** OT.
- ☎️ **VoIP / IP Phones**: Polycom (`PlcmSpIp/PlcmSpIp`, `polycom/456`)، Yealink، Grandstream، Fanvil، Mitel، ShoreTel، Avaya، Asterisk، Elastix، FreePBX، FreeSWITCH، 3CX، ATA (PAP2T).
- 🔣 **الگوهای Leetspeak و جایگزینی**: `r00t@123`, `4dm1n@123`, `P@55w0rd`.
- 🌍 **اعتبارنامه‌های بومی‌سازی‌شده**: شامل رمزهای مرتبط با Iran/Tehran/Persia و الگوهای رایج اسامی فارسی.
- 📝 **سازگار با ابزارها**: کامنت‌ها با `#` شروع می‌شوند تا توسط Hydra، Medusa، NetExec، Patator و Ncrack نادیده گرفته شوند.

---

## 📁 فایل‌های این پک

| فایل | کاربرد |
|---|---|
| `telnet_usernames_by_ebrasha.txt` | اکانت‌های IoT، وندوری، CPE مخابراتی، دوربین، ICS، VoIP و Unix قدیمی |
| `telnet_passwords_by_ebrasha.txt` | اعتبارنامه‌های رده Mirai + پیش‌فرض‌های وندوری + پسوردهای واقعی Telnet |

---

## 🚀 نحوهٔ استفاده

> ⚠️ **توقف**: این وردلیست‌ها را **فقط** علیه سیستم‌هایی استفاده کنید که **مالک آن‌ها هستید** یا **مجوز کتبی صریح** دارید. بسیاری از دستگاه‌های Embedded ممکن است تحت Brute Force دچار Crash شوند (DoS) — قبل از شروع با مالک هماهنگ کنید.

### 🐉 Hydra (توصیه‌شده، آهسته و ایمن برای دستگاه)

</div>

```bash
hydra -L telnet_usernames_by_ebrasha.txt -P telnet_passwords_by_ebrasha.txt telnet://<target> -t 2 -W 3
```

<div dir="rtl">

### 🛡️ Ncrack

</div>

```bash
ncrack -vv --user telnet_usernames_by_ebrasha.txt -P telnet_passwords_by_ebrasha.txt telnet://<target>:23
```

<div dir="rtl">

### 🔧 Medusa

</div>

```bash
medusa -h <target> -U telnet_usernames_by_ebrasha.txt -P telnet_passwords_by_ebrasha.txt -M telnet
```

<div dir="rtl">

### 🧪 Patator

</div>

```bash
patator telnet_login host=<target> port=23 user=FILE0 password=FILE1 0=telnet_usernames_by_ebrasha.txt 1=telnet_passwords_by_ebrasha.txt persistent=0
```

<div dir="rtl">

### 🔍 بررسی سریع با Nmap NSE

</div>

```bash
nmap -p 23,2323,4567,5555 --script telnet-brute --script-args userdb=telnet_usernames_by_ebrasha.txt,passdb=telnet_passwords_by_ebrasha.txt <target>
```

<div dir="rtl">

### 💧 استراتژی توصیه‌شده

۱. **ابتدا Banner را بگیرید** (`nc <target> 23` یا `nmap -sV -p 23 <target>`) — Banner معمولاً وندور و مدل دقیق را نشان می‌دهد و به شما اجازه می‌دهد ۳ تا ۵ جفت اعتبارنامهٔ دقیق را به جای Brute Force کامل امتحان کنید.  
۲. از **`-t 1` یا `-t 2`** (تعداد Thread پایین) استفاده کنید — بسیاری از دستگاه‌های Embedded بالای ۴ Session هم‌زمان Crash می‌کنند.  
۳. همیشه قبل از اجرای لیست کامل، **جفت پیش‌فرض وندور** را تست کنید (مثل `root/xc3511`, `admin/admin`, `Polycom/456`).  
۴. Telnet اعتبارنامه‌ها را **به‌صورت Cleartext** منتقل می‌کند — فرض کنید هر اعتبارنامه‌ای که پیدا کرده‌اید قبلاً در دست مهاجمان است و فوراً آن را تغییر دهید.  
۵. روی اهداف ICS/SCADA **هرگز Brute Force نکنید** — فقط با تأیید صریح مهندس OT، یک یا دو جفت پیش‌فرض شناخته‌شده را اعتبارسنجی کنید تا فرآیندهای فیزیکی مختل نشوند.

---

## ⚠️ تذکر قانونی و اخلاقی

این وردلیست صرفاً برای تست امنیتی **مجاز**، عملیات Red Team، ارزیابی آسیب‌پذیری و پژوهش‌های آموزشی ارائه شده است. استفاده از آن بدون **مجوز کتبی صریح**، **غیرقانونی** است و ممکن است قوانین محلی، ملی و بین‌المللی را نقض کند.

با استفاده از این فایل، شما موافقت می‌کنید که:

۱. برای هر هدف، مجوز کتبی صریح در اختیار دارید.  
۲. مسئولیت کامل قانونی و اخلاقی استفاده را می‌پذیرید.  
۳. نگه‌دارنده (ابراهیم شفیعی) **هیچ‌گونه مسئولیتی** در قبال سوءاستفاده، خسارت، Crash دستگاه یا فعالیت غیرقانونی ندارد.

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
