# AI-Cockpit — Dokumentation

*[English version → README.md](README.md)*

<a href="https://apps.apple.com/app/id6802014255">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="img/mas-badge-de-dark.svg">
    <img src="img/mas-badge-de-light.svg" alt="AI-Cockpit im Mac App Store laden" height="44">
  </picture></a>

**Website: [aicockpit.info/de](https://aicockpit.info/de/)** · CHF 3.50, einmalig · [Weitere Apps](https://ipstyle.github.io)

Eine macOS-Menüleisten-App, die alle KI-Budgets an einem Ort zeigt: Auslastung
des Claude-Abos, ChatGPT/Codex-Kontingente, OpenAI-API-Kosten,
Anthropic-API-Kosten, Kimi-Guthaben — dazu die gerade laufenden
Claude-Code-Sitzungen auf deinem Mac, mit Subagenten, Token-Anteilen und
Kontextfenstern.

Standard Englisch, Deutsch wählbar unter Einstellungen → Anzeige.
Braucht macOS 14. Die Bildschirmfotos zeigen die englische Oberfläche.

Daneben gibt es **AI Cockpit Mobile** — eine gratis iPhone- und iPad-Fassung
mit Apple-Watch-Begleiter, derzeit in Prüfung bei Apple. Sie teilt sich den
Quellcode mit dieser App (geschlossen wie hier) und holt ihre Karten direkt
auf dem Gerät; sobald Apple freigibt, steht hier der Link.

## Bildschirmfotos

Das Menüleistensymbol — Gehirn, «AI-C» und beide Fenster, in unter 50 Punkten:

<img src="img/menubar.jpg" alt="Menüleistensymbol" width="360">

Vier Menüleisten-Stile — beide Fenster · kritischster Wert · Ring · Restzeit:

<img src="img/menubar-both.jpg" alt="Beide Fenster" height="30"> <img src="img/menubar-crit.jpg" alt="Kritischster Wert" height="30"> <img src="img/menubar-ring.jpg" alt="Ring" height="30"> <img src="img/menubar-rest.jpg" alt="Restzeit" height="30">

Das volle Cockpit — Anbieter nebeneinander, Sparklines, Hochrechnung,
Kostenaufteilung je Modell und Projekt:

<img src="img/dashboard.jpg" alt="Cockpit" width="760">

Jede Karte lässt sich auf eine Zeile einklappen — Warnungen bleiben farbig
sichtbar:

<img src="img/compact.jpg" alt="Eingeklappte Ansicht" width="760">

| Konten | Anzeige |
|---|---|
| <img src="img/settings-accounts.jpg" alt="Einstellungen — Konten" width="420"> | <img src="img/settings-display.jpg" alt="Einstellungen — Anzeige" width="420"> |

Über-Seite mit Transparenzangaben (Verbindungen, lokal Gelesenes,
Gespeichertes) und dem Prüfprotokoll:

<img src="img/about.jpg" alt="Über" width="560">

## Funktionen

- **Menüleiste auf einen Blick** — Gehirn-Symbol mit 5-Stunden- und
  7-Tage-Auslastung von Claude; alternative Stile (kritischster Wert, Ring,
  Restzeit) für volle Menüleisten. Die Symbolbreite wird gemessen, nicht
  geraten.
- **Claude-Abo** — 5-Stunden- und 7-Tage-Fenster, modellbezogene Wochenfenster,
  Zurücksetzungszeiten, Sparklines und Hochrechnung («bei diesem Tempo voll um
  16:44»).
- **ChatGPT/Codex** — Kontingente live; keine eigene Anmeldung, die bestehende
  wird genutzt.
- **OpenAI-API** — Kosten heute / Monat / gesamt, je Modell und je Projekt,
  Budget-Balken, Monatsbericht als HTML oder CSV, und das **verfügbare
  Guthaben**: OpenAI gibt den Stand nicht über die Schnittstelle heraus, darum
  erfasst man Aufladebetrag und Datum einmal, und die App zieht die
  abgerechneten Tageskosten ab.
- **Anthropic-API** — Kosten neben dem Abo, per Admin-Schlüssel.
- **Kimi** — verfügbares Guthaben und Coding-Abo-Kontingent.
- **Aktive Claude-Code-Sitzungen** — Zustand, Modell, Aufwand, verrechnete
  Token, Anteil am laufenden 5-Stunden-Fenster, Füllstand des Kontextfensters,
  Subagenten.
- **Hinweise** — beim Überschreiten von Schwellen, bei absehbarem Volllaufen,
  wenn eine Sitzung auf dich wartet, und bevor ein Kontextfenster voll ist.
- **Mach es zu deinem Cockpit** — Dunkel (Standard), warmes Hell oder System;
  Englisch oder Deutsch; nur die Karten zeigen, die du nutzt; Schwellen,
  Abrufintervalle und Verlaufsdauer sind einstellbar.

## Schnellstart

Installiert — und dann? Zwei Minuten Einrichtung.

1. **Bei Claude anmelden** — Fusszeile → «Bei Claude anmelden»: OAuth im
   Browser, nichts abzutippen.
2. **API-Schlüssel eintragen** — Einstellungen → Konten: OpenAI-Admin-Schlüssel
   (`sk-admin-…`) von platform.openai.com → Settings → Admin keys,
   Anthropic-Admin-Schlüssel (`sk-ant-admin-…`) aus console.anthropic.com
   und/oder ein Kimi-Schlüssel von platform.kimi.ai (bzw. .com für China).
   Nur eintragen, was du nutzt — jede Karte ist optional.
3. **ChatGPT — nichts zu tun:** läuft, sobald die ChatGPT-App mit Codex
   installiert und angemeldet ist.
4. **Sitzungen zeigen** — einmalig Lesezugriff auf `~/.claude` gewähren, wenn
   die Karte fragt.

## Berechtigungen

| Berechtigung | Wozu | Pflicht? |
|---|---|---|
| Schlüsselbund | API-Schlüssel und Claude-Anmeldung auf diesem Gerät speichern | ja, je Zugang |
| Mitteilungen | Schwellen- und Hochrechnungswarnungen | nein |
| Lesen von `~/.claude` und `~/.codex` | laufende Sitzungen und Kontingente anzeigen — nur lesend | nur für diese Funktionen |

## Privatsphäre & Sicherheit

- **Verbindungen ausschliesslich zu:** `api.anthropic.com`, `claude.com` /
  `platform.claude.com` (OAuth-Anmeldung), `api.openai.com`,
  `api.moonshot.ai` / `api.moonshot.cn` / `api.kimi.com`. Weiterleitungen
  werden nie befolgt; keine Telemetrie, keine Analytics, kein
  Update-Nachhausetelefonieren.
- **Sitzungsinhalte werden nie übertragen.** Transkripte werden lokal und nur
  für die Anzeige gelesen.
- **Zugangsdaten** liegen ausschliesslich im macOS-Schlüsselbund
  (`kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly`).
- **Der Verlauf** speichert nur Prozentwerte, Beträge und Zeitstempel und
  lässt sich in den Einstellungen abschalten und löschen.
- **Sicherheitsgeprüft:** vier dokumentierte Prüfdurchgänge gegen OWASP ASVS
  4.0, OWASP MASVS, Apple Secure Coding Guide, RFC 8252/7636 und die CWE
  Top 25 — das vollständige Protokoll steht auf der Über-Seite der App. Das ist
  eine dokumentierte modellgestützte Prüfung, kein externes Audit.

## Feedback

Fehlt ein Anbieter? Wünschst du dir eine Kennzahl, die das Cockpit noch nicht
zeigt? → [aicockpit.info/de/#feedback](https://aicockpit.info/de/#feedback)

---

© 2026 Albert Frick (ipstyle). Alle Rechte vorbehalten. Dieses Repository
enthält nur Dokumentation und Bildschirmfotos; die App selbst ist proprietär.
Claude ist eine Marke von Anthropic, ChatGPT und Codex von OpenAI, Kimi von
Moonshot AI. AI-Cockpit ist ein unabhängiges Werkzeug und steht mit keinem
dieser Anbieter in Verbindung.
