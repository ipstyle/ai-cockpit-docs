# AI-Cockpit — Documentation

*[Deutsche Version → README.de.md](README.de.md)*

<a href="https://apps.apple.com/app/id6802014255">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="img/mas-badge-en-dark.svg">
    <img src="img/mas-badge-en-light.svg" alt="Download AI-Cockpit on the Mac App Store" height="44">
  </picture></a>

**Website: [aicockpit.info](https://aicockpit.info)** · CHF 3.50, one-time

A macOS menu bar app that keeps every AI budget you have in one place: Claude
subscription usage, ChatGPT/Codex quotas, OpenAI API costs, Anthropic API
costs, Kimi credit — plus the Claude Code sessions currently running on your
Mac, with their subagents, token shares and context windows.

English by default, German selectable in Settings → Display. Requires macOS 14.

## Screenshots

The menu bar icon — brain, «AI-C» and both usage windows, in under 50 pt:

<img src="img/menubar.jpg" alt="Menu bar icon" width="360">

Four menu-bar styles — both windows · most critical value · ring · time
remaining:

<img src="img/menubar-both.jpg" alt="Both windows" height="30"> <img src="img/menubar-crit.jpg" alt="Most critical value" height="30"> <img src="img/menubar-ring.jpg" alt="Ring" height="30"> <img src="img/menubar-rest.jpg" alt="Time remaining" height="30">

The full dashboard — providers side by side, sparklines, forecasts, cost
breakdown per model and project:

<img src="img/dashboard.jpg" alt="Dashboard" width="760">

Every card collapses to a one-line summary — warnings stay visible in colour:

<img src="img/compact.jpg" alt="Collapsed view" width="760">

| Accounts | Display |
|---|---|
| <img src="img/settings-accounts.jpg" alt="Settings — accounts" width="420"> | <img src="img/settings-display.jpg" alt="Settings — display" width="420"> |

About tab with transparency notes (connections, local reads, storage) and the
security review record:

<img src="img/about.jpg" alt="About" width="560">

## Features

- **Menu bar at a glance** — brain icon with your 5-hour and 7-day Claude
  usage; alternative styles (most critical value, ring, time remaining) for
  narrow menu bars. The icon width is measured, not guessed.
- **Claude subscription** — 5-hour and 7-day windows, per-model weekly windows,
  reset times, trend sparklines and a forecast («at this pace, full at 16:44»).
- **ChatGPT/Codex** — live quotas; no extra sign-in, it reuses the one you
  already have.
- **OpenAI API** — costs today / month / total, per model and per project,
  budget bar, monthly report as HTML or CSV, and a **credit balance**: OpenAI
  does not expose the balance via API, so you record top-up amount and date
  once and the app subtracts the billed daily costs.
- **Anthropic API** — costs next to the subscription, via admin key.
- **Kimi** — available balance and coding-plan quota.
- **Active Claude Code sessions** — state, model, effort, billed tokens, share
  of the current 5-hour window, context window fill level, subagents.
- **Notifications** — on threshold crossings, on forecasted exhaustion, when a
  session is waiting for you, and before a context window fills up.
- **Make it yours** — dark (default), warm light or system theme; English or
  German; show only the cards you use; thresholds, refresh rates and history
  are all configurable.

## Quick start

Installed — and then? Two minutes of setup.

1. **Sign in to Claude** — footer → «Sign in to Claude»: OAuth in your
   browser, nothing to copy over.
2. **Add your API keys** — Settings → Accounts: OpenAI admin key
   (`sk-admin-…`) from platform.openai.com → Settings → Admin keys, Anthropic
   admin key (`sk-ant-admin-…`) from console.anthropic.com, and/or a Kimi key
   from platform.kimi.ai (or .com for China). Add only what you use — every
   card is optional.
3. **ChatGPT — nothing to do:** works as soon as the ChatGPT app with Codex is
   installed and signed in.
4. **See your sessions** — grant read-only access to `~/.claude` once when the
   card asks.

## Permissions the app asks for

| Permission | Why | Mandatory? |
|---|---|---|
| Keychain | store your API keys and the Claude sign-in on this device | yes, per credential |
| Notifications | threshold and forecast alerts | no |
| Read `~/.claude` and `~/.codex` | show running sessions and quotas — read-only | only for those features |

## Privacy & security

- **Connections go exclusively to:** `api.anthropic.com`, `claude.com` /
  `platform.claude.com` (OAuth sign-in), `api.openai.com`, `api.moonshot.ai` /
  `api.moonshot.cn` / `api.kimi.com`. Redirects are never followed; there is
  no telemetry, no analytics, no update phone-home.
- **Session contents are never transmitted.** Transcripts are read locally and
  only for display.
- **Credentials** live exclusively in the macOS Keychain
  (`kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly`).
- **History** records only percentages, amounts and timestamps, and can be
  disabled and deleted in Settings.
- **Security-reviewed:** four documented review passes against OWASP ASVS 4.0,
  OWASP MASVS, the Apple Secure Coding Guide, RFC 8252/7636 and the CWE
  Top 25 — the full record ships in the app's About tab. This is a documented
  model-assisted review, not an external audit.

## Feedback

Missing a provider? Want a metric the cockpit doesn't show yet?
→ [aicockpit.info/#feedback](https://aicockpit.info/#feedback)

---

© 2026 Albert Frick (ipstyle). All rights reserved. This repository contains
documentation and screenshots only; the application itself is proprietary.
Claude is a trademark of Anthropic; ChatGPT and Codex of OpenAI; Kimi of
Moonshot AI. AI-Cockpit is an independent tool and is not affiliated with any
of these providers.
