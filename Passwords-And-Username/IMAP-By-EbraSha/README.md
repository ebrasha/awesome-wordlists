<!-- 
**********************************************************************
 Project Name : IMAP Penetration Testing Wordlists
 File Name    : README.md
 Maintainer   : Ebrahim Shafiei (EbraSha)
 Email        : Prof.Shafiei@Gmail.com
 Created On   : 2026-05-25 08:00:46
 Description  : English documentation for the IMAP penetration testing
                wordlists (usernames & passwords) crafted for
                authorized IMAP / IMAPS security assessments.
**********************************************************************
-->

<div align="right">

> 🌐 **Read in your language:** 🇬🇧 [English](README.md) | 🇮🇷 [فارسی](README.fa.md)

</div>

<p align="right">
  <img src="shot.png" alt="IMAP Wordlists Preview" align="right" />
</p>

# 📥 IMAP Penetration Testing Wordlists — High-Probability Usernames & Passwords for IMAP / IMAPS Brute Force on Dovecot, Cyrus, Exchange, Zimbra, M365 & cPanel Mail

### 👤 Ebrahim Shafiei (EbraSha) 🇮🇷

A curated, real-world, high-signal wordlist pack tailored specifically for **authorized** penetration testing of **IMAP / IMAPS** services on ports `143` and `993`. Built from breach corpora, vendor defaults, role-account conventions, common mailbox naming schemes (`first.last@`, `flast@`, `firstname@`) and real engagement data targeting on-prem mail servers and cloud-hosted mailboxes.

---

## 📌 Why This Project Exists

A compromised IMAP credential is **one of the most damaging mailbox findings** — it grants full read access to every historical message, attachment, recovery code, contact, and internal communication. Generic wordlists are poor for IMAP because:

- IMAP accepts **both bare (`admin`) and FQ (`admin@domain.tld`) usernames** depending on server config.
- **Mailbox role accounts** (`postmaster`, `info`, `noreply`, `support`) almost always exist and are often poorly protected.
- **Common naming schemes** (`first.last`, `flast`, `firstname`) drastically narrow the username space — generic lists waste effort.
- **Exchange / M365 / Google Workspace** trigger smart-lockout instantly on noisy brute force.

This project ships **two small, surgical, high-probability files** — maximizing first-shot success while minimizing lockout risk and detection.

---

## ✨ Features & Capabilities

- 🎯 **IMAP-focused**: Tuned for Dovecot, Cyrus IMAP, Microsoft Exchange / O365 IMAP, Zimbra, MDaemon, IceWarp, MailEnable, hMailServer, Kerio Connect, cPanel mail, Plesk mail.
- 📬 **Role accounts everywhere**: `postmaster`, `hostmaster`, `webmaster`, `noreply`, `bounce`, `abuse`, `noc`, `info`, `support` (targets that almost always exist).
- 🌐 **Both bare and FQ formats**: `admin` AND `admin@<DOMAIN>` — replace `<DOMAIN>` with the target before use.
- 👥 **Naming-scheme aware**: `first.last@`, `flast@`, `f.last@`, `firstname@`, `lastname@` — covers ~95% of corporate conventions.
- 🏢 **Enterprise patterns**: Seasonal (`Summer2025!`), quarterly (`Q1@2026`), monthly (`June2026`) passwords from rotation policies.
- 🔣 **Leetspeak & substitution**: `M@il@2026`, `Exch@nge@2026`, `Z1mbra@2026`, `4dm1n@123`.
- ⌨️ **Keyboard-walk passwords**: `1qaz2wsx`, `qweasdzxc`, `zaq1!QAZ`.
- 🌍 **Localized credentials**: Iran / Tehran / Persia entries and common Persian first names.
- 🤖 **Integrations**: CRM/ERP/Ticketing service accounts (Salesforce, Zendesk, Freshdesk, ServiceNow, Jira, SAP).
- 📝 **Tool-friendly headers**: Comments prefixed with `#` so Hydra, Medusa, NetExec, Patator, Ncrack ignore them.

---

## 📁 Files in This Pack

| File | Purpose |
|---|---|
| `imap_usernames_by_ebrasha.txt` | Mailbox role accounts, VIP names, vendor defaults, FQ email patterns, naming schemes |
| `imap_passwords_by_ebrasha.txt` | High-probability passwords + vendor defaults + policy-compliant rotation patterns |

---

## 🚀 How To Use

> ⚠️ **STOP**: Use these wordlists ONLY against systems you **own** or have **explicit written authorization** to test. A successful IMAP credential grants full mailbox read access — a **HIGH-severity finding** that must be reported immediately.

### Replace `<DOMAIN>` placeholders first

```bash
sed -i 's/<DOMAIN>/example.com/g' imap_usernames_by_ebrasha.txt
```

### 🐉 Hydra (port 993 IMAPS — most common)

```bash
hydra -L imap_usernames_by_ebrasha.txt -P imap_passwords_by_ebrasha.txt -s 993 imaps://<target> -t 1 -W 5
```

### 🐉 Hydra (port 143 STARTTLS)

```bash
hydra -L imap_usernames_by_ebrasha.txt -P imap_passwords_by_ebrasha.txt -s 143 imap://<target> -t 1 -W 5
```

### 🛡️ Ncrack

```bash
ncrack -vv --user imap_usernames_by_ebrasha.txt -P imap_passwords_by_ebrasha.txt imap://<target>:143 imaps://<target>:993
```

### 🔧 Medusa

```bash
medusa -h <target> -U imap_usernames_by_ebrasha.txt -P imap_passwords_by_ebrasha.txt -M imap -n 993 -s
```

### 🧪 Patator

```bash
patator imap_login host=<target> port=993 ssl=1 user=FILE0 password=FILE1 0=imap_usernames_by_ebrasha.txt 1=imap_passwords_by_ebrasha.txt -x ignore:fgrep='NO'
```

### 🔍 Nmap NSE

```bash
nmap -p 143,993 --script imap-brute --script-args userdb=imap_usernames_by_ebrasha.txt,passdb=imap_passwords_by_ebrasha.txt <target>
```

### 💧 Recommended Strategy

1. **Always use password spraying** (one password against many users) — IMAP lockout is per-user-per-IP on Exchange / M365.
2. Add **30+ seconds delay** between attempts to evade smart-lockout heuristics.
3. Start with **role accounts** (`postmaster`, `noreply`, `info`, `support`) — universal and weakly protected.
4. Use **OSINT-derived names** (Hunter.io, LinkedIn, Have-I-Been-Pwned) to build a targeted list of real employees first.
5. **Always prefer IMAPS (993)** over plaintext IMAP (143) — both for stealth and to avoid leaking credentials to passive sniffers on shared infrastructure.
6. **Report any successful authentication IMMEDIATELY** — full mailbox read access is a critical finding.

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
