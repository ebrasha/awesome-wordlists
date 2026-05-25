<!-- 
**********************************************************************
 Project Name : SMTP Penetration Testing Wordlists
 File Name    : README.md
 Maintainer   : Ebrahim Shafiei (EbraSha)
 Email        : Prof.Shafiei@Gmail.com
 Created On   : 2026-05-25 08:00:46
 Description  : English documentation for the SMTP penetration testing
                wordlists (usernames & passwords) crafted for
                authorized SMTP AUTH / relay security assessments.
**********************************************************************
-->

<div align="right">

> 🌐 **Read in your language:** 🇬🇧 [English](README.md) | 🇮🇷 [فارسی](README.fa.md)

</div>

<p align="right">
  <img src="shot.png" alt="SMTP Wordlists Preview" align="right" />
</p>

# 📧 SMTP Penetration Testing Wordlists — High-Probability Usernames & Passwords for AUTH PLAIN / LOGIN Brute Force on Postfix, Exim, Sendmail, Exchange, Zimbra, M365 & SMTP Relays

### 👤 Ebrahim Shafiei (EbraSha) 🇮🇷

A curated, real-world, high-signal wordlist pack tailored specifically for **authorized** penetration testing of **SMTP authentication** on ports `25`, `465`, `587`, `2525`. Built from breach corpora, vendor defaults, role-account conventions, transactional-email API key formats, and real engagement data targeting on-prem MTAs and cloud-bridged relays.

---

## 📌 Why This Project Exists

SMTP is **uniquely valuable** to attackers — a single valid AUTH credential typically enables **BEC, phishing, malware delivery, and brand abuse**. Yet most generic wordlists miss SMTP's specifics:

- SMTP accepts **both bare (`admin`) and FQ (`admin@domain.tld`) usernames** depending on server config.
- **Mailbox role accounts** (`postmaster`, `noreply`, `bounce`, `abuse`) are everywhere and often have weak/static passwords.
- **Cloud relays** (SendGrid, Mailgun, SES, Postmark) expose dedicated SMTP credentials with predictable API-key formats.
- **Exchange & M365** apply "smart lockout" — generic brute force triggers it instantly.

This project ships **two small, surgical, high-probability files** — maximizing first-shot success while minimizing lockout risk.

---

## ✨ Features & Capabilities

- 🎯 **SMTP-focused**: Tuned for Postfix, Exim, Sendmail, qmail, Dovecot SASL, Microsoft Exchange / O365, Zimbra, MDaemon, IceWarp, MailEnable, hMailServer, Kerio Connect.
- 📬 **Role accounts everywhere**: `postmaster`, `hostmaster`, `webmaster`, `mailer-daemon`, `noreply`, `bounce`, `abuse`, `noc`, `info`, `support` (the targets that almost always exist).
- 🌐 **Both bare and FQ formats**: `admin` AND `admin@<DOMAIN>` — replace `<DOMAIN>` with the target before use.
- ☁️ **Cloud relay coverage**: SendGrid (`SG.*`), Mailgun (`key-*`), Amazon SES (`AKIA*`), Postmark, Mailjet, SparkPost, ElasticEmail, Mailtrap, SMTP2GO, TurboSMTP.
- 🛡️ **Mail-security appliances**: IronPort, Proofpoint, Mimecast, Barracuda, FortiMail, Sophos Email, Trustwave, SpamTitan.
- 🏢 **Enterprise patterns**: Seasonal (`Summer2025!`), quarterly (`Q1@2026`), monthly (`June2026`) passwords from rotation policies.
- 🔣 **Leetspeak & substitution**: `M@il@2026`, `Exch@nge@2026`, `Z1mbra@2026`, `4dm1n@123`.
- ⌨️ **Keyboard-walk passwords**: `1qaz2wsx`, `qweasdzxc`, `zaq1!QAZ`.
- 🌍 **Localized credentials**: Iran / Tehran / Persia entries and common Persian first names.
- 🤖 **Marketing/CRM/ERP integrations**: Salesforce, Zendesk, Freshdesk, ServiceNow, Jira, SAP, Mailman, phpList, Sympa.
- 📝 **Tool-friendly headers**: Comments prefixed with `#` so Hydra, Medusa, NetExec, Patator, Ncrack ignore them.

---

## 📁 Files in This Pack

| File | Purpose |
|---|---|
| `smtp_usernames_by_ebrasha.txt` | Mailbox role accounts, admin / service accounts, vendor defaults, FQ email patterns |
| `smtp_passwords_by_ebrasha.txt` | High-probability passwords + cloud relay API-key formats + policy-compliant patterns |

---

## 🚀 How To Use

> ⚠️ **STOP**: Use these wordlists ONLY against systems you **own** or have **explicit written authorization** to test. A successful SMTP AUTH credential enables BEC / phishing and **must be reported immediately**.

### Replace `<DOMAIN>` placeholders first

```bash
sed -i 's/<DOMAIN>/example.com/g' smtp_usernames_by_ebrasha.txt
```

### 🐉 Hydra (port 587 STARTTLS — most common)

```bash
hydra -L smtp_usernames_by_ebrasha.txt -P smtp_passwords_by_ebrasha.txt -s 587 smtp://<target> -t 1 -W 5
```

### 🐉 Hydra (port 465 SSL/TLS)

```bash
hydra -L smtp_usernames_by_ebrasha.txt -P smtp_passwords_by_ebrasha.txt -s 465 smtps://<target> -t 1 -W 5
```

### 🛡️ Ncrack

```bash
ncrack -vv --user smtp_usernames_by_ebrasha.txt -P smtp_passwords_by_ebrasha.txt smtp://<target>:587
```

### 🧪 Patator (most flexible — supports SSL & STARTTLS)

```bash
patator smtp_login host=<target> port=587 starttls=1 user=FILE0 password=FILE1 0=smtp_usernames_by_ebrasha.txt 1=smtp_passwords_by_ebrasha.txt -x ignore:fgrep='535'
```

### 🔍 Nmap NSE (enum + brute)

```bash
nmap -p 25,465,587 --script smtp-enum-users,smtp-brute --script-args userdb=smtp_usernames_by_ebrasha.txt,passdb=smtp_passwords_by_ebrasha.txt <target>
```

### 💧 Recommended Strategy

1. **Always enumerate first** with `smtp-user-enum`, `VRFY`, `EXPN`, `RCPT TO` probes to confirm valid mailboxes BEFORE brute forcing — saves attempts and reduces detection.
2. Use **password spraying** (one password against many users) — Exchange / M365 lockout is per-user-per-IP.
3. Add **30+ seconds delay** between attempts to evade smart-lockout heuristics.
4. Start with **role accounts** (`postmaster`, `noreply`, `info`) — these are universal and often weakly protected.
5. For cloud relays (SendGrid/Mailgun/SES), test the **API-key format** patterns first.
6. **Report any successful authentication IMMEDIATELY** — SMTP AUTH compromise is a critical BEC/phishing risk.

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
