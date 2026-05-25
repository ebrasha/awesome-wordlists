<!-- 
**********************************************************************
 Project Name : SSH Penetration Testing Wordlists
 File Name    : README.md
 Maintainer   : Ebrahim Shafiei (EbraSha)
 Email        : Prof.Shafiei@Gmail.com
 Created On   : 2026-05-25 08:00:46
 Description  : English documentation for the SSH penetration testing
                wordlists (usernames & passwords) crafted for
                authorized Linux/Unix/BSD/IoT SSH assessments.
**********************************************************************
-->

<div align="right">

> 🌐 **Read in your language:** 🇬🇧 [English](README.md) | 🇮🇷 [فارسی](README.fa.md)

</div>

<p align="right">
  <img src="shot.png" alt="SSH Wordlists Preview" align="right" />
</p>

# 🐧 SSH Penetration Testing Wordlists — High-Probability Usernames & Passwords for Linux, Unix, BSD, IoT and Cloud SSH Brute Force / Password Spraying

### 👤 Ebrahim Shafiei (EbraSha) 🇮🇷

A curated, real-world, high-signal wordlist pack tailored specifically for **authorized** penetration testing of **OpenSSH and SSH-compatible** services on port `22` (and custom ports). Built from breach corpora, vendor defaults, cloud image defaults, IoT/embedded device habits, and the most common Linux/Unix administrator patterns observed in production environments.

---

## 📌 Why This Project Exists

Most public wordlists (`rockyou.txt`, `SecLists`, etc.) are **too large, too generic, and too noisy** for SSH engagements. SSH has unique characteristics that make general-purpose lists inefficient and risky:

- **Fail2ban / sshguard / CrowdSec** ban source IPs after a small number of failed attempts.
- **Cloud images** ship with predictable usernames (`ec2-user`, `ubuntu`, `centos`, `opc`, `core`) — not `root`.
- **IoT and embedded devices** still use vendor defaults (`pi/raspberry`, `root/toor`, `admin/admin`).
- **Real-world admins** reuse a small, predictable set of patterns (seasonal, vendor, policy-compliant).

This project solves these problems by shipping **two small, surgical, high-probability files** instead of millions of noisy candidates — maximizing the chance of a successful login per request and minimizing IP bans and detection.

---

## ✨ Features & Capabilities

- 🎯 **SSH-focused**: Tuned for OpenSSH, Dropbear, libssh, Cisco IOS SSH, JunOS SSH, and embedded SSH stacks.
- 🧠 **High-signal, low-volume**: Quality over quantity — engineered for **password spraying**, not blind brute force.
- 🐧 **Linux/Unix/BSD defaults**: Ubuntu, Debian, CentOS, RHEL, SUSE, Arch, Alpine, FreeBSD, OpenBSD, Solaris, AIX.
- ☁️ **Cloud image defaults**: `ec2-user`, `ubuntu`, `centos`, `debian`, `opc`, `core`, `azureuser`, `gcpuser`, `linode`.
- 📦 **Container & orchestration accounts**: Docker, Kubernetes, Rancher, OpenShift, Nomad, Consul, Vault.
- 🌐 **Network appliance defaults**: Cisco, Juniper, MikroTik, Ubiquiti, Fortinet, Palo Alto, Check Point, SonicWall, Huawei.
- 🖥️ **Out-of-band management**: iLO, iDRAC, IPMI, BMC, Nutanix (including the infamous `idrac/calvin`, `nutanix/nutanix/4u`).
- 📷 **IoT & embedded**: Raspberry Pi, IP cameras (Hikvision, Dahua, Axis), NAS (Synology, QNAP, TrueNAS).
- 🏢 **Enterprise patterns**: Seasonal (`Summer2025!`), quarterly (`Q1@2026`), and monthly (`June2026`) passwords from 90-day rotation policies.
- 🔣 **Leetspeak & substitution patterns**: `r00t@123`, `4dm1n@123`, `L1nux@2026`, `S3rv3r@2026`.
- ⌨️ **Keyboard-walk passwords**: `1qaz2wsx`, `qweasdzxc`, `zaq1!QAZ`.
- 🌍 **Localized credentials**: Iran/Tehran/Persia-themed entries and common Persian first-name patterns.
- 📝 **Tool-friendly headers**: Comments are prefixed with `#` so Hydra, Medusa, NetExec, Patator, and Ncrack ignore them automatically.

---

## 📁 Files in This Pack

| File | Purpose |
|---|---|
| `ssh_usernames_by_ebrasha.txt` | Linux/Unix, cloud, container, vendor, IoT and role-based accounts |
| `ssh_passwords_by_ebrasha.txt` | High-probability, real-world passwords used on SSH-exposed hosts |

---

## 🚀 How To Use

> ⚠️ **STOP**: Use these wordlists ONLY against systems you **own** or have **explicit written authorization** to test. Unauthorized use is a criminal offense.

### 🐉 Hydra (slow, fail2ban-safe)

```bash
hydra -L ssh_usernames_by_ebrasha.txt -P ssh_passwords_by_ebrasha.txt ssh://<target> -t 4 -W 5
```

### 🔧 NetExec / CrackMapExec

```bash
netexec ssh <target> -u ssh_usernames_by_ebrasha.txt -p ssh_passwords_by_ebrasha.txt --continue-on-success
```

### 🛡️ Ncrack

```bash
ncrack -vv --user ssh_usernames_by_ebrasha.txt -P ssh_passwords_by_ebrasha.txt ssh://<target>:22
```

### 🧪 Patator (most flexible)

```bash
patator ssh_login host=<target> user=FILE0 password=FILE1 0=ssh_usernames_by_ebrasha.txt 1=ssh_passwords_by_ebrasha.txt -x ignore:mesg='Authentication failed'
```

### 💧 Recommended Password Spraying Strategy

1. Test **one password against all usernames** before moving to the next password.
2. Add a **delay of 60+ seconds** between attempts to avoid fail2ban / sshguard triggers.
3. Always identify the **OS / cloud provider** first (`nmap -sV`) to pick the right username (`ec2-user` vs `root` vs `pi`).
4. Start with **vendor defaults** (`pi/raspberry`, `idrac/calvin`, `nutanix/nutanix/4u`) — they have the highest hit rate on unmanaged devices.
5. For policy-compliant servers, start with **current-year seasonal** passwords (`Summer2026!`, `Winter@2026`).

---

## ⚠️ Legal & Ethical Notice

This wordlist is provided strictly for **authorized** security testing, red team operations, vulnerability assessments, and educational research. Using it against any system, network, or account without **explicit written permission** from the legitimate owner is **ILLEGAL** and may violate local, national, and international laws (Computer Fraud and Abuse Act, GDPR, and similar legislation).

By using this file you agree that:

1. You possess explicit written authorization for every target.
2. You assume full legal and ethical responsibility for your use.
3. The maintainer (Ebrahim Shafiei) bears **NO liability** for any misuse, damage, or unlawful activity performed with this list.

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
