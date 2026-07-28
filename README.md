# hAI.LeapMateDocker

[![GitHub Stars](https://img.shields.io/github/stars/jbkunama1/hAI.LeapMateDocker?style=flat-square&logo=github)](https://github.com/jbkunama1/hAI.LeapMateDocker/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/jbkunama1/hAI.LeapMateDocker?style=flat-square&logo=github)](https://github.com/jbkunama1/hAI.LeapMateDocker/network/members)
[![GitHub Issues](https://img.shields.io/github/issues/jbkunama1/hAI.LeapMateDocker?style=flat-square)](https://github.com/jbkunama1/hAI.LeapMateDocker/issues)
[![License: GPL-3.0](https://img.shields.io/badge/License-GPL--3.0-blue.svg?style=flat-square)](LICENSE)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ED?style=flat-square&logo=docker)](docker-compose.portainer.yml)
[![GitHub Pages](https://img.shields.io/badge/GH--Pages-live-brightgreen?style=flat-square&logo=github)](https://jbkunama1.github.io/hAI.LeapMateDocker)
[![Upstream](https://img.shields.io/badge/Upstream-ProtossBlaster%2Fleapmotor--mate-orange?style=flat-square&logo=github)](https://github.com/ProtossBlaster/leapmotor-mate)

> **Portainer Stack** für [LeapMotor-Mate](https://github.com/ProtossBlaster/leapmotor-mate) – Deploy direkt aus GitHub in Portainer, kein manuelles Clonen nötig.

---

## ℹ️ Beschreibung

[LeapMotor-Mate](https://github.com/ProtossBlaster/leapmotor-mate) ist ein selbst gehostetes Web-Dashboard für Leap-Motor-Fahrzeuge, das Fahrzeugdaten pollt, in einer SQLite-Datenbank speichert und über eine Web-Oberfläche zugänglich macht.

Dieses Repo liefert einen fertigen **Portainer Stack** (Git-Deployment), der direkt aus dem Upstream-Repo deployed werden kann.

---

## 🚀 Portainer Deploy (Git-Deployment)

### Voraussetzungen
- Portainer Business oder CE ≥ 2.x
- Zugriff auf das Internet vom Docker-Host aus

### Schritte

1. In Portainer → **Stacks** → **+ Add stack**
2. Name: `leapmotor-mate`
3. Build method: **Repository**
4. Repository URL: `https://github.com/jbkunama1/hAI.LeapMateDocker`
5. Repository reference: `refs/heads/main`
6. Compose path: `docker-compose.portainer.yml`
7. **Environment variables** setzen (siehe unten)
8. **Deploy the stack**

---

## 🔧 Environment Variables

| Variable | Beschreibung | Beispiel |
|---|---|---|
| `LEAPMOTOR_USER` | Leapmotor-App E-Mail | `dein@email.de` |
| `LEAPMOTOR_PASS` | Leapmotor-App Passwort | `geheim123` |
| `LEAPMOTOR_PIN` | PIN der App | `1234` |
| `DB_PATH` | Pfad zur SQLite-DB im Container | `/data/leapmotor_mate.db` |
| `TZ` | Zeitzone | `Europe/Berlin` |
| `PORT` | Web-Port im Container (default 4000) | `4000` |

Falls du eine `.env`-Datei nutzen möchtest: Kopiere `.env.example` und fülle die Werte aus.

---

## 📂 Dateistruktur

```
hAI.LeapMateDocker/
├── docker-compose.portainer.yml  ← Portainer Stack (baut Image aus Upstream-Repo)
├── .env.example                  ← Vorlage für Umgebungsvariablen
├── docs/
│   └── index.html                ← GitHub Pages Landingpage
└── README.md
```

---

## 📝 Upstream

Dieses Repo deployt direkt den Quellcode von [ProtossBlaster/leapmotor-mate](https://github.com/ProtossBlaster/leapmotor-mate).
Das Image wird beim ersten Deploy vom Docker-Host gebaut (kein vorgefertigtes Image nötig).

---

## 📄 Lizenz

GPL-3.0 – entsprechend dem Upstream-Projekt.
