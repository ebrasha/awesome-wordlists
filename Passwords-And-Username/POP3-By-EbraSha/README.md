<!-- 
**********************************************************************
 Project Name : POP3 Penetration Testing Wordlists
 File Name    : README.md
 Maintainer   : Ebrahim Shafiei (EbraSha)
 Email        : Prof.Shafiei@Gmail.com
 Created On   : 2026-05-25 08:00:46
 Description  : English documentation for the POP3 penetration testing
                wordlists (usernames & passwords) crafted for
                authorized POP3 / POP3S security assessments against
                legacy mailbox accounts.
**********************************************************************
-->

<div align="right">

> 🌐 **Read in your language:** 🇬🇧 [English](README.md) | 🇮🇷 [فارسی](README.fa.md)

</div>

<p align="right">
  <img src="shot.png" alt="POP3 Wordlists Preview" align="right" />
</p>

# 📮 POP3 Penetration Testing Wordlists — High-Probability Usernames & Passwords for Legacy Mailbox Brute Force on Dovecot, Courier, qpopper, Exchange, Zimbra & ISP Mail

### 👤 Ebrahim Shafiei (EbraSha) 🇮🇷

A curated, real-world, high-signal wordlist pack tailored specifically for **authorized** penetration testing of **POP3 / POP3S** services on ports `110` and `995`. Built from breach corpora, vendor defaults, role-account conventions, ISP mailbox naming patterns, and a deliberate focus on the **never-rotated, decade-old passwords** that are still very common on legacy POP3 mailboxes.

---

## 📌 Why This Project Exists

POP3 is the **forgotten legacy protocol** of the email world — and that makes it especially attractive to attackers:

- Accounts that still actively use POP3 in 2026 frequently have **old, weak, never-rotated passwords**.
- POP3 is often **excluded** from corporate password-rotation policies.
- A successful POP3 credential grants **full read AND delete (DELE)** access — attackers can silently exfiltrate AND erase incoming MFA codes, password resets, and security alerts.
- POP3 supports **3 different username encodings** (`admin`, `admin@domain.tld`, `admin%domain.tld`) — generic lists miss the legacy `%` form.

This project ships **two small, surgical, high-probability files** with deliberate coverage of legacy/never-rotated passwords (`Password2018`, `Welcome2019`, `Summer2020`) that are still alive on POP3 mailboxes nobody monitors.

---

## ✨ Features & Capabilities

- 🎯 **POP3-focused**: Tuned for Dovecot, Courier-IMAP/POP, qpopper, Cyrus POP3, Microsoft Exchange / O365 POP3, Zimbra, MDaemon, IceWarp, MailEnable, hMailServer, Kerio Connect, cPanel mail, Plesk mail.
- 📜 **Legacy password coverage**: Includes `*2010`–`*2023` seasonal/admin/welcome patterns rarely covered by modern wordlists — but still very alive on never-rotated POP3 accounts.
- 📬 **Role accounts**: `postmaster`, `hostmaster`, `webmaster`, `noreply`, `bounce`, `abuse`, `info`, `support`.
- 🌐 **Three username encodings**: bare (`admin`), FQ (`admin@<DOMAIN>`), and legacy ISP-style (`admin%<DOMAIN>`).
- 👥 **Naming-scheme aware**: `first.last@`, `flast@`, `f.last@`, `firstname@`, `lastname@`.
- 🏢 **Enterprise & ISP patterns**: Seasonal, quarterly, monthly passwords + ISP customer-portal defaults.
- 🔣 **Leetspeak & substitution**: `M@il@2026`, `Exch@nge@2026`, `Z1mbra@2026`, `4dm1n@123`.
- ⌨️ **Keyboard-walk passwords**: `1qaz2wsx`, `qweasdzxc`, `zaq1!QAZ`.
- 🌍 **Localized credentials**: Iran / Tehran / Persia entries and common Persian first names.
- 📝 **Tool-friendly headers**: Comments prefixed with `#` so Hydra, Medusa, NetExec, Patator, Ncrack ignore them.

---

## 📁 Files in This Pack

| File | Purpose |
|---|---|
| `pop3_usernames_by_ebrasha.txt` | Mailbox role accounts, ISP/customer accounts, vendor defaults, FQ + `%` encoded patterns |
| `pop3_passwords_by_ebrasha.txt` | High-probability passwords with deliberate legacy/never-rotated coverage |

---

## 🚀 How To Use

> ⚠️ **STOP**: Use these wordlists ONLY against systems you **own** or have **explicit written authorization** to test. A successful POP3 credential grants full read+delete mailbox access — a **CRITICAL finding** that must be reported immediately.

### Replace `<DOMAIN>` placeholders first

```bash
sed -i 's/<DOMAIN>/example.com/g' pop3_usernames_by_ebrasha.txt
```

### 🐉 Hydra (port 995 POP3S — most common)

```bash
hydra -L pop3_usernames_by_ebrasha.txt -P pop3_passwords_by_ebrasha.txt -s 995 pop3s://<target> -t 1 -W 5
```

### 🐉 Hydra (port 110 STARTTLS / cleartext POP3)

```bash
hydra -L pop3_usernames_by_ebrasha.txt -P pop3_passwords_by_ebrasha.txt -s 110 pop3://<target> -t 1 -W 5
```

### 🛡️ Ncrack

```bash
ncrack -vv --user pop3_usernames_by_ebrasha.txt -P pop3_passwords_by_ebrasha.txt pop3://<target>:110 pop3s://<target>:995
```

### 🔧 Medusa

```bash
medusa -h <target> -U pop3_usernames_by_ebrasha.txt -P pop3_passwords_by_ebrasha.txt -M pop3 -n 995 -s
```

### 🧪 Patator

```bash
patator pop_login host=<target> port=995 ssl=1 user=FILE0 password=FILE1 0=pop3_usernames_by_ebrasha.txt 1=pop3_passwords_by_ebrasha.txt -x ignore:fgrep='-ERR'
```

### 🔍 Nmap NSE

```bash
nmap -p 110,995 --script pop3-brute --script-args userdb=pop3_usernames_by_ebrasha.txt,passdb=pop3_passwords_by_ebrasha.txt <target>
```

### 💧 Recommended Strategy

1. **Always check whether POP3 is actually enabled** on M365 / Google Workspace first — it's often disabled by default; if enabled, the accounts that use it are usually low-hygiene legacy mailboxes.
2. Use **password spraying** (one password against many users) — lockout is per-user-per-IP on Exchange / M365.
3. **Heavily test legacy passwords** (`*2018`, `*2019`, `*2020`, `*2021`) — they hit much more on POP3 than on any other protocol.
4. Add **30+ seconds delay** between attempts to evade smart-lockout heuristics.
5. **Always prefer POP3S (995)** over plaintext POP3 (110) — POP3 sends credentials in cleartext.
6. **Report any successful authentication IMMEDIATELY** — POP3 allows silent deletion of inbound MFA/reset/audit emails, making it a critical lateral-movement and persistence vector.

---

## ⚠️ Legal & Ethical Notice

This wordlist is provided strictly for **authorized** security testing, red team operations, vulnerability assessments, and educational research. Using it without **explicit written permission** is **ILLEGAL** and may violate local, national, and international laws.

By using this file you agree that:

1. You possess explicit written authorization for every target.
2. You assume full legal and ethical responsibility.
3. The maintainer (Ebrahim Shafiei) bears **NO liability** for misuse.

---

## 🐛 Reporting Issues

If you encounter any issues or have configuration problems, please reach out via email at Prof.Shafiei@Gmail.com. You can also report issues on GitHub.

## ❤️ Donation

If you find this project helpful and would like to support further development, please consider making a donation:

- [Donate Here](https://t.me/AbdalDonationBot)

## 🤵 Maintained by

Maintained with Passion by **Ebrahim Shafiei (EbraSha)**

- **E-Mail**: Prof.Shafiei@Gmail.com
- **Telegram**: [@ProfShafiei](https://t.me/ProfShafiei)
