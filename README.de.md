# Ultimative Wordlist-Sammlung für Penetrationstests, Brute-Force und Web-Fuzzing

> 🌐 **In Ihrer Sprache lesen:** 🇬🇧 [English](README.md) | 🇨🇳 [中文](README.zh.md) | 🇷🇺 [Русский](README.ru.md) | 🇪🇸 [Español](README.es.md) | 🇯🇵 [日本語](README.ja.md) | 🇮🇷 [فارسی](README.fa.md) | 🇸🇦 [العربية](README.ar.md) | 🇹🇷 [Türkçe](README.tr.md) | 🇩🇪 [Deutsch](README.de.md) | 🇮🇳 [हिन्दी](README.hi.md)


[![Security](https://img.shields.io/badge/Security-Pentesting-red.svg)](#)


Das umfassendste Repository auf GitHub, das als zentralisierte und hochgradig optimierte Hauptsammlung von Wordlists, Wörterbuchangriffsdaten und fortgeschrittenen Fuzzing-Payloads dient — speziell zugeschnitten auf Sicherheitsexperten, Penetrationstester und ethische Hacker.

---

## 🎯 Warum dieses Repository existiert

Während Sicherheitsbewertungen und Penetrationstests ist der unmittelbare Zugriff auf gut strukturierte, qualitativ hochwertige Daten entscheidend. Standard-Wordlists sind häufig verstreut, veraltet oder mit redundanten Daten gefüllt, die Brute-Force-Angriffe und Web-Fuzzing verlangsamen.

Dieses Repository wurde geschaffen, um diese Lücke zu schließen. Es stellt eine essenzielle Infrastrukturkomponente für die Arbeitsumgebung eines Sicherheitsprüfers dar. Durch die Konsolidierung vielseitig nutzbarer Listen in einem einzigen, strukturierten Repository können Sie es schnell in jede Testumgebung klonen und unmittelbar gezielte Wörterbuchangriffe, Verzeichnis­erkennung oder Payload-Injektionen einsetzen.

---

## 📂 Inhalt und Struktur des Repositories

Die Datensätze in diesem Repository sind strategisch kategorisiert und optimiert, um Geschwindigkeit zu maximieren, Rauschen zu minimieren und hohe Erfolgsraten bei aktiven Penetrationstests und ethischen Hacking-Einsätzen sicherzustellen. Nachfolgend finden Sie eine umfassende Aufschlüsselung des strukturellen Aufbaus dieses Repositories:

### 🤖 1. Künstliche Intelligenz (KI) und LLM-Sicherheit (`/Ai`)
Eine hochmoderne Sammlung, entwickelt für adversariale Tests, die Verifikation der Sicherheitsausrichtung und das Red-Teaming moderner LLMs und KI-Modelle:
* **Bias- und Fairness-Tests:** Standardisierte Wörterbücher (`gender_bias.txt`, `race_ethnicity_bias.txt`) zur Auditierung der Modellausrichtung.
* **Datenleck und Datenschutz:** Gezielte Payloads zur Simulation versehentlicher PII-Abrufe und Metadaten­offenlegung (`personal_data.txt`).
* **Adversariale und Jailbreak-Prompts:** Historische und weiterentwickelte Prompt-Injection-Sätze, die entwickelt wurden, um Modellgrenzen zu umgehen und strenge Ausrichtungseinschränkungen zu prüfen.

### 🔍 2. Web-Fuzzing, Asset-Discovery und Aufklärung (`/Discovery`)
Umfassende Listen, strukturiert für die aggressive Kartierung der unternehmensweiten Angriffsfläche über Netzwerk-, Anwendungs- und Infrastruktur­ebenen hinweg:
* **Verzeichnis- und Dateienumeration:** Enthält hochwertige Wordlists wie die kuratierten `raft`- und `DirBuster`-Serien zur Identifizierung versteckter Web-Pfade, System-Backdoors und Shell-Locations.
* **Infrastruktur und Netzwerk:** Subdomain-Enumerationslisten (einschließlich kombinierter Top 1M-Varianten), gängige Web-Erweiterungen, Dienstnamen und benutzerdefinierte SNMP Community Strings (`snmp.txt`).
* **CMS- und Umgebungskontexte:** Hoch spezifische Endpoints für Unternehmenssysteme und Content-Management-Systeme, einschließlich umfassender Pfade für WordPress-Plugins/Themes, Drupal, Joomla, Apache, Nginx, Tomcat und WebSphere.

### 🔑 3. Authentifizierung und Anmeldedaten (Passwörter und Leak-Datensätze)
Hauptlisten mit Fokus auf hochperformantes Credential Stuffing, die Auditierung von Standardzugängen und ausgefeilte Brute-Force-Wörterbuchangriffe:
* **Geleakte Anmeldedaten und Dumps:** Optimierte Varianten legendärer Leak-Datensätze (wie sortierte `rockyou`-Shards, `myspace` und historisch geleakte Community-Muster) — mit oder ohne Vorkommensanzahl.
* **Standardzugangsdaten:** Umfangreiche Zuordnungen herstellerseitiger Standardkonten, gängige Router-Passwörter, CICS-Transaktions-IDs und herstellerübergreifende CCTV/DVR-Anmeldeprofile.
* **Spezialisierte Umgebungen:** Maßgeschneiderte Anmeldedateien, strukturiert für spezifische Netzwerkprotokolle (SSH, Telnet, Datenbank-Roots und IPMI-Profile).

### ⚡ 4. Injection-, Fuzzing- und Mutation-Payloads
Fortgeschrittene Payloads, zusammengestellt zur Validierung von Schwachstellen auf Anwendungsebene und zum Aussortieren nicht ausnutzbarer Randfälle:
* **Serverseitige Schwachstellen:** Dynamische Listen, gezielt für Local File Inclusion (LFI), optimiert für Unix-/Windows-Pfade, Remote File Inclusion sowie das Überschreiben von Systemvariablen.
* **Native Web-Komponenten:** Umfassende Zuordnungen für Parameter-Mining (`burp-parameter-names.txt`), API-Discovery (`api-endpoints.txt`) und individuell angepasste PHP-Fuzz-Listen zur Umgehung von Eingabevalidierungsfiltern.


---

## ⚖️ Rechtlicher Hinweis

**Wichtiger Hinweis:** Dieses Repository und die darin bereitgestellten Datensätze wurden ausschließlich zu Bildungszwecken, für autorisierte Penetrationstests und für Sicherheitsaudits erstellt.

*   **Verantwortung des Nutzers:** Die letztendliche Verantwortung für die Nutzung dieser Wordlists liegt vollständig beim Endnutzer. Der Maintainer übernimmt keinerlei Haftung für jegliche missbräuchliche Verwendung, unbefugte Angriffe, Datenschutzverletzungen oder rechtliche Konsequenzen, die durch die Nutzung dieser Dateien entstehen.
*   **Compliance:** Stellen Sie sicher, dass Sie die ausdrückliche schriftliche Genehmigung der Zielorganisation oder des Asset-Eigentümers besitzen, bevor Sie irgendeine Form der Sicherheitsbewertung, eines Wörterbuchangriffs oder Fuzzings einleiten.

Durch das Klonen oder die Nutzung dieses Repositories stimmen Sie diesen Bedingungen zu und bestätigen, dass Ihre Aktivitäten den lokalen und internationalen Gesetzen im Bereich der Cybersicherheit strikt entsprechen müssen.



## 🐛 Probleme melden

Sollten Sie auf Probleme stoßen oder Konfigurationsfragen haben, kontaktieren Sie uns bitte per E-Mail unter Prof.Shafiei@Gmail.com. Sie können Probleme auch auf GitHub melden.


## ❤️ Spende

Wenn Sie dieses Projekt hilfreich finden und die weitere Entwicklung unterstützen möchten, ziehen Sie bitte eine Spende in Betracht:

- [Hier spenden](https://t.me/AbdalDonationBot)


## 🤵 Betreut von

Mit Leidenschaft gepflegt von **Ebrahim Shafiei (EbraSha)**

- **E-Mail**: Prof.Shafiei@Gmail.com

- **Telegram**: [@ProfShafiei](https://t.me/ProfShafiei)
