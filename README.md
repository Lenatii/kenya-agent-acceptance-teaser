# Kenya Agent Acceptance Pack — Public Teaser

**Five free synthetic acceptance scenarios** for WhatsApp / voice agents serving Kenya & East Africa.

Import into **Promptfoo** (or map to Coval / Cekura). Gate releases before production.

> This repo is the **teaser only**. The full commercial pack (additional scenarios, updates, written licence) is a **separate private product** and is **not** included here.

## The 5 cases

| id | Why it hurts |
|----|----------------|
| `ke-mpesa-late-no-code` | Late M-Pesa with no txn code — must not invent a receipt |
| `ke-book-saa-kumi-kesho` | *Saa kumi kesho* — Swahili time vs clinic slots |
| `ke-lang-sheng-sw-en-mix` | Sheng → English → Kiswahili mid-thread |
| `ke-ecom-angry-refund` | Angry damaged-item refund to M-Pesa |
| `ke-voice-interrupt-barge` | Caller barge-in over a policy monologue |

## Quick eval

```bash
npx promptfoo@latest eval -c promptfooconfig.teaser.yaml
```

Replace the echo provider with your agent under test.

## Docs

- [`TEASER.md`](TEASER.md) — punchy narrative + pricing hypothesis
- [`FAILURE_STORY.md`](FAILURE_STORY.md) — Loom-style demo script
- [`LICENSE`](LICENSE) — evaluation-only; commercial pack separate

## What this is / is not

**Is:** versioned YAML acceptance scenarios (synthetic dialogues only).  
**Is not:** an AI agent, speech corpus, test runner, Conekta/payment-rail code, or live PII transcripts.

## CTA — request the commercial pack

Open a **GitHub Discussion** or **Issue** on this repository titled:

**`commercial pack interest`**

Say starter vs agency licence. Prefer Discussions/Issues over email so nothing depends on a live inbox.

Optional placeholder mailto (change anytime): [hello@example.com](mailto:hello@example.com?subject=commercial%20pack%20interest).

---

Copyright (c) 2026 Lenatii. See [`LICENSE`](LICENSE).
