# BaseShield 🛡

> **Free AI-powered smart contract security auditor for Base & EVM chains.**
> Powered by **Xiaomi MiMo V2.5** — no API key required to try, BYO key for production-grade reasoning.

[![Live Demo](https://img.shields.io/badge/demo-live-0052ff?style=flat-square)](https://fikrizz.github.io/baseshield/)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](#license)
[![Built with MiMo](https://img.shields.io/badge/AI-Xiaomi%20MiMo%20V2.5-ff6b35?style=flat-square)](https://platform.xiaomimimo.com/)

---

## ✨ What it does

Paste a deployed contract address (or raw Solidity source) → get an instant AI-powered audit with:

- 🧠 **40+ built-in static rules** for Solidity vulnerabilities (reentrancy, access control, oracle manipulation, signature replay, integer over/underflow, MEV, proxy issues, gas anti-patterns…)
- 🤖 **AI-generated fix suggestions** for each finding, in code-block form, ready to paste
- 💬 **BaseAI Chat** — context-aware security assistant that knows your audit context
- 📊 **Severity score** (0–100) + breakdown by Critical / High / Medium / Low / Info
- 🌐 **Multi-chain on-chain fetch:** Base, Ethereum, BSC, Polygon, Arbitrum, Optimism, Avalanche, Linea
- 📝 **Export reports:** plain text, Markdown, JSON, or PDF certificate (PNG)
- 💾 **History** — all your audits saved locally, browser-only, zero backend

## 🎯 Why MiMo?

The **reasoning** model in MiMo V2.5 is exceptionally well-suited to security audit logic:

- Traces multi-step exploit paths (flash-loan → oracle manipulation → liquidation cascade)
- Distinguishes false-positive from true-positive on overloaded patterns (e.g. CEI vs CFI)
- Returns structured Solidity patches that compile

We use the OpenAI-compatible endpoint `https://api.xiaomimimo.com/v1/chat/completions` — drop in your key under **Settings ⚙** and BaseShield uses MiMo for every AI call. Without a key, a free public endpoint provides a rate-limited demo.

## 🚀 Quick start

### Try it live

→ **https://fikrizz.github.io/baseshield/**

### Run locally

It's a single self-contained `index.html`. No build step, no framework, no backend.

```bash
git clone https://github.com/Fikrizz/baseshield.git
cd baseshield
python3 -m http.server 8000
# open http://localhost:8000
```

### Add your MiMo API key

1. Get a free key at [platform.xiaomimimo.com](https://platform.xiaomimimo.com/)
2. Open BaseShield → click **⚙ Settings** in the header
3. Paste your key → **Test** → **Save**

Your key never leaves your browser; it's stored in `localStorage` and sent only to `api.xiaomimimo.com`.

## 🧱 Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      BaseShield (single .html)              │
├─────────────────────────────────────────────────────────────┤
│  UI: Vanilla JS · CSS Glass Morphism · Inter + JetBrains   │
│       └─ Tabs: Audit / Approvals / Examples / History       │
├─────────────────────────────────────────────────────────────┤
│  Engine                                                     │
│    1. Source fetch ──► Etherscan/Basescan/BscScan/...       │
│    2. Static rules  ──► 40+ regex + AST heuristics          │
│    3. AI reasoning  ──► Xiaomi MiMo V2.5 (BYOK)             │
│       │                  └─ fallback: Pollinations free     │
│       │                  └─ fallback: rule-based KB         │
│    4. Report build  ──► score, severity, fixes, gas hints   │
├─────────────────────────────────────────────────────────────┤
│  Storage: localStorage (history, settings, API key)         │
│  Export:  TXT · MD · JSON · PNG certificate                 │
└─────────────────────────────────────────────────────────────┘
```

## 🛠 Built with

- Pure HTML + CSS + vanilla JS — single file, ~130 KB
- [Xiaomi MiMo V2.5](https://platform.xiaomimimo.com/) reasoning model — primary AI engine
- [Pollinations](https://pollinations.ai/) free public endpoint — keyless demo fallback
- Block explorer APIs: Etherscan, Basescan, BscScan, Polygonscan, Arbiscan, Optimistic Etherscan
- Built with **Cursor + Claude Code** (AI-driven development)

## 🗺 Roadmap

- [ ] On-chain bytecode disassembly + decompiled-source fallback
- [ ] Foundry test harness generator (auto-write PoC for each finding)
- [ ] Slither / Echidna integration via WASM
- [ ] Multi-file Solidity project upload
- [ ] Audit certificate verification on-chain (Base mainnet)
- [ ] CLI version + GitHub Action

## 📄 License

MIT — see [LICENSE](LICENSE).

## 🙋 Author

[**@Fikrizz**](https://github.com/Fikrizz) — submitting to **Xiaomi MiMo Orbit 100T Creator Program**.

If this project helps you, give it a ⭐ — it really helps for the program submission.
