# Kenya Agent Acceptance Pack — Public Teaser

**Five free synthetic acceptance scenarios** for WhatsApp / voice agents serving Kenya & East Africa.

Import into **Promptfoo** (or map to Coval / Cekura). Gate releases before production.

> This repo is the **teaser only**. The full commercial pack (additional scenarios, updates, written licence) is a **separate private product** and is **not** included here.

## The 5 cases

| id | Why it hurts |
|----|----------------|
| `ke-mpesa-late-no-code` | Late M-Pesa with no txn code — must not invent a receipt or mark paid |
| `ke-book-saa-kumi-kesho` | *Saa kumi kesho* — Swahili clock semantics can silently corrupt bookings |
| `ke-lang-sheng-sw-en-mix` | Sheng → English → Kiswahili mid-thread without losing intent |
| `ke-ecom-angry-refund` | Damaged-item refund to M-Pesa without fake completion or policy invention |
| `ke-voice-interrupt-barge` | Transcript-level proxy for a caller interrupting a policy monologue |

## Quick eval

```bash
npx promptfoo@latest eval -c promptfooconfig.teaser.yaml -j 1 --no-progress-bar
```

The teaser defaults to Promptfoo's **manual-input provider** so you can paste a real reply from any agent without configuring API keys. For automated regression, replace that provider with your own Promptfoo target (OpenAI/Anthropic/HTTP/custom provider/etc.).

**Important:** the public voice interruption case is a transcript-level semantic proxy. It does not measure acoustic barge-in latency, VAD, duplex audio, packet loss, or TTS interruption timing; those require a voice-capable harness.

## What a credible pass means

These are acceptance tests, not keyword demos. A passing agent should preserve the correct **business state and behaviour** — e.g. disambiguate Swahili time before booking, refuse to confirm an unmatched M-Pesa payment, and follow code-switched intent without forcing one language.

The public Promptfoo config uses deterministic checks where practical. For production use, combine deterministic assertions with human review or a separately configured evaluator appropriate to your system.

## Docs

- [`TEASER.md`](TEASER.md) — product narrative + pricing hypothesis
- [`FAILURE_STORY.md`](FAILURE_STORY.md) — short demo script
- [`SCENARIO_SCHEMA.md`](SCENARIO_SCHEMA.md) — acceptance-test contract
- [`LICENSE`](LICENSE) — evaluation-only; commercial pack separate
- **Spoken teaser demo** (~46s voice note covering *saa kumi*, M-Pesa without code, and this repo CTA) exists privately — ask via Discussion/Issue if you want to hear it. Audio is not mirrored here.

## What this is / is not

**Is:** versioned YAML acceptance scenarios (synthetic dialogues only).  
**Is not:** an AI agent, speech corpus, test runner, Conekta/payment-rail code, or live PII transcripts.

## Commercial pack interest

Open a **GitHub Discussion** or **Issue** titled:

**`commercial pack interest`**

Say whether you are evaluating a starter or agency licence. **Do not post proprietary prompts, customer data, credentials, or confidential deployment details.** A private procurement/contact route can then be established separately.

---

Copyright (c) 2026 Lenatii. See [`LICENSE`](LICENSE).
