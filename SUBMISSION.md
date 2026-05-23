# 🚀 BaseShield — Submission Pack untuk Xiaomi MiMo 100T Program

> Ini panduan + template lengkap buat submit ke https://100t.xiaomimimo.com/
> Deadline: **28 Mei 2026 00:00 (Beijing) / 27 Mei 2026 16:00 UTC**

---

## ✅ Pre-submit checklist

Pastiin SEMUA ini ready sebelum klik "立即申请":

- [ ] **Repo public di GitHub:** https://github.com/Fikrizz/baseshield
- [ ] **Live demo URL:** https://fikrizz.github.io/baseshield/ (GitHub Pages)
- [ ] **README lengkap** (sudah ada — `README.md`)
- [ ] **MIT License** (sudah ada — `LICENSE`)
- [ ] **2-3 screenshot/GIF** demo (rekomendasi: pakai Loom atau bikin GIF dari ScreenToGif)
- [ ] **Akun Xiaomi MiMo Open Platform** dibuat dengan email yang sama dengan email di form
- [ ] **API key MiMo** udah di-test working (kalau bisa, integrate sebelum submit)

---

## 🎬 Step-by-step deploy ke GitHub Pages

```bash
# 1. Login ke GitHub & buat repo "baseshield" (public, kosong, no README)

# 2. Push project
cd /home/ubuntu/baseshield
git init
git add .
git commit -m "Initial commit: BaseShield v2.0"
git branch -M main
git remote add origin https://github.com/Fikrizz/baseshield.git
git push -u origin main

# 3. Enable GitHub Pages
#    Repo → Settings → Pages
#    Source: Deploy from branch → main → /(root) → Save
#    Tunggu ~1 menit, refresh, copy URL: https://fikrizz.github.io/baseshield/
```

---

## 📝 Form Submission Templates

Form di 100t.xiaomimimo.com biasanya minta info berikut. Gw siapin 2 versi: **Mandarin** (default form) dan **English** (fallback).

### Field 1: 项目名称 / Project Name

```
BaseShield — AI Smart Contract Security Auditor
```

### Field 2: 项目链接 / Project URL

```
Live Demo: https://fikrizz.github.io/baseshield/
GitHub: https://github.com/Fikrizz/baseshield
```

### Field 3: 项目描述 / Project Description

**🇨🇳 中文版:**

```
BaseShield 是一款面向 Base 和所有 EVM 链的免费 AI 智能合约安全审计工具，
深度集成 Xiaomi MiMo V2.5 推理模型。

核心功能：
1. 一键审计 — 输入合约地址或粘贴 Solidity 源码，AI 自动检测 40+ 种漏洞
   (重入攻击、权限控制、预言机操纵、签名重放、整数溢出、MEV、代理升级等)
2. AI 修复建议 — MiMo V2.5 为每一个漏洞生成可直接编译的 Solidity 修复代码
3. BaseAI 安全助手 — 上下文感知的对话式安全咨询，懂得你刚审计的合约细节
4. 多链支持 — Base / Ethereum / BSC / Polygon / Arbitrum / Optimism / Avalanche / Linea
5. 报告导出 — TXT / Markdown / JSON / PNG 审计证书

为什么选 MiMo？智能合约审计需要多步推理（追踪攻击路径、区分 false-positive、
生成可编译的补丁代码），MiMo V2.5 的推理能力在这些场景下表现优于通用模型。

技术栈：纯 HTML + CSS + 原生 JavaScript，单文件 ~130KB，无后端，
直接调用 https://api.xiaomimimo.com/v1/chat/completions（OpenAI 兼容接口）。

开发工具：Cursor + Claude Code（AI-driven development）
```

**🇬🇧 English version:**

```
BaseShield is a free AI-powered smart contract security auditor for Base and 
all EVM chains, deeply integrated with Xiaomi MiMo V2.5 reasoning model.

Core features:
1. One-click audit — paste a contract address or Solidity source, AI detects 
   40+ vulnerability types (reentrancy, access control, oracle manipulation, 
   signature replay, integer overflow, MEV, proxy upgrade issues, etc.)
2. AI-generated fixes — MiMo V2.5 produces compilable Solidity patches for 
   each finding
3. BaseAI security assistant — context-aware conversational AI that knows 
   your latest audit findings
4. Multi-chain — Base / Ethereum / BSC / Polygon / Arbitrum / Optimism / 
   Avalanche / Linea
5. Report export — TXT / Markdown / JSON / PNG certificate

Why MiMo? Smart contract auditing requires multi-step reasoning (tracing 
exploit paths, distinguishing false-positives, generating compilable patches). 
MiMo V2.5's reasoning capability outperforms generic models in these cases.

Tech: Pure HTML + CSS + vanilla JS, single ~130KB file, no backend, calls 
https://api.xiaomimimo.com/v1/chat/completions (OpenAI-compatible).

Built with: Cursor + Claude Code (AI-driven development workflow)
```

### Field 4: 使用的 AI 工具和模型 / AI Tools & Models Used

```
Primary AI Engine: Xiaomi MiMo V2.5 (mimo-v2.5-reasoning)
  - Endpoint: https://api.xiaomimimo.com/v1/chat/completions
  - Use cases: vulnerability reasoning, fix generation, audit chat assistant

Development Tools:
  - Cursor IDE
  - Claude Code (Anthropic)
  - GitHub Copilot
```

### Field 5: 项目证明材料 / Proof Materials

Upload/link berikut:

```
1. Live demo: https://fikrizz.github.io/baseshield/
2. Source code: https://github.com/Fikrizz/baseshield
3. README: https://github.com/Fikrizz/baseshield/blob/main/README.md
4. Screenshots:
   - screenshot-audit.png    (full audit report view)
   - screenshot-chat.png     (BaseAI chat with context)
   - screenshot-settings.png (MiMo API integration)
5. Demo video (optional, recommended): upload to YouTube/Bilibili
```

### Field 6: 你计划如何使用 Token 权益？/ How will you use the Token credits?

```
🇨🇳:
将完全用于 BaseShield 的 MiMo API 调用：
- 为公开演示版本提供免费的 MiMo V2.5 推理能力（不需要用户自带 key）
- 处理大型合约审计（多文件项目、proxy 模式、复杂 DeFi 协议）
- 生成 Foundry 测试用例（roadmap 第二阶段）
- 训练用户提交的真实漏洞数据集（脱敏后用于改进检测规则）

预计每月调用：~50-200 万 tokens（取决于用户量）

🇬🇧:
100% allocated to MiMo API calls for BaseShield:
- Provide free MiMo V2.5 inference for the public demo (no user key needed)
- Handle large contract audits (multi-file projects, proxy patterns, complex DeFi)
- Generate Foundry test cases (phase 2 of roadmap)
- Build vulnerability dataset from anonymized user submissions

Estimated usage: ~500K–2M tokens/month depending on traffic.
```

### Field 7: Email / 邮箱

```
[Email yang sama dengan akun di platform.xiaomimimo.com]
```

⚠️ **PENTING:** Email di form HARUS sama dengan email yang terdaftar di akun MiMo Open Platform. Kalau akun lo register pakai nomor HP, bind email dulu di id.mi.com.

---

## 🎁 Tips buat naikin tier reward

1. **Detail > singkat** — mereka eksplisit bilang "填写越详细、项目越具体，评估通过率和权益档位越高"
2. **Bukti konkret** — live URL > screenshot > deskripsi
3. **Sebut MiMo dengan spesifik** — sebut model name (`mimo-v2.5-reasoning`), endpoint URL, dan kenapa MiMo cocok untuk use case lo
4. **Sebut AI dev tools** — Cursor, Claude Code, dll. Mereka suka karena nunjukin lo aktif di AI dev ecosystem
5. **Show traction** kalau ada — star count, user count, contoh audit yang udah dijalankan
6. **Roadmap jelas** — nunjukin lo ga abandonware setelah submit

---

## ⏰ Timeline

```
Hari ini (24 Mei) — Submit form ✅
~3 hari kerja        — Email evaluasi
+24 jam setelah ACK  — Token Plan masuk ke akun
28 Mei 00:00 (BJT)   — DEADLINE PROGRAM
```

---

## 🆘 Kalau ada masalah

- **Email gak masuk** → cek spam, tunggu sampai 3 hari kerja, baru submit ulang
- **Email akun ≠ email form** → bind ulang di https://id.mi.com
- **Form gak submit** → bisa jadi VPN issue, coba ganti region
- **API error setelah dapat key** → cek di https://platform.xiaomimimo.com/ dashboard

Good luck 🛡
