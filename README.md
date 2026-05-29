# IP Inscription — Demo

A zero-config, click-through demo of **IP Inscription**: upload any file and get a
verifiable, timestamped, tamper-proof proof of authorship.

This is a **standalone, root-level Next.js app** — deploy it to Vercel with no
configuration and no environment variables.

> This is the demo build. The full project (real Bitcoin Ordinals mode + an EVM
> reference contract) lives at
> https://github.com/anthonysidework/ipinscription-mvp

---

## What "demo mode" does

- **Real:** SHA-256 file hashing happens in your browser.
- **Simulated:** wallet connect (instant fake Signet address) and the Bitcoin
  inscription (realistic-looking but fake txid). No extension, no funds, no keys.
- **Persisted per visitor:** records are saved in the browser's localStorage, so
  Explore / My Inscriptions / Verify all work for each visitor.

A banner makes the simulated parts explicit.

---

## The loop

1. **Connect** — instant simulated wallet.
2. **Inscribe** — upload a file + title → real SHA-256 hash → simulated inscription
   → **Certificate of Inscription**.
3. **My Inscriptions** — your records.
4. **Explore** — the registry of your demo inscriptions.
5. **Verify** — upload a file; hit shows its record, miss shows "no record found".

---

## Run locally

```bash
npm install
npm run dev      # http://localhost:3000
```

No `.env` needed — it runs in demo mode by default.

---

## Deploy to Vercel

Because the app is at the **repository root**, this needs no special settings:

1. Push this repo to GitHub.
2. Vercel → **New Project → import the repo**.
3. Leave **Root Directory** empty (the default) and **add no environment
   variables**.
4. **Deploy.** The live URL runs the full demo.

---

## Tech

Next.js (App Router) · TypeScript · Tailwind CSS · SHA-256 via Web Crypto.

Demo · simulated inscriptions · not legal advice.
