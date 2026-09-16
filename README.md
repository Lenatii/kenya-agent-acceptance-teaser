# Kenya Agent Acceptance Pack

**Production-oriented acceptance tests for AI agents operating in Kenyan business reality.**

An agent can sound fluent and still leave the business in the wrong state. This pack tests whether customer-facing AI preserves payment, booking, refund, delivery and customer-intent state when Kenyan language and operational semantics get messy.

> **“Boss, nilishalipa M-Pesa jana.”**  
> Keep the payment unconfirmed until it can be verified.
>
> **“Kesho saa kumi asubuhi.”**  
> Recognize the relevant Swahili clock interpretation and clarify before locking a booking.

The public teaser contains **five synthetic acceptance scenarios** for WhatsApp, chat and transcript-level voice-proxy testing in Kenya / East Africa.

> This repository is the **public teaser only**. The commercial pack is a separate private product with additional scenarios, versioned updates, stronger evaluator mappings and written licensing.

## Why this exists

Generic language fluency is not enough for production agents.

A useful acceptance test should catch cases where the reply sounds reasonable but the underlying business state is wrong, for example:

- an unverified M-Pesa claim is treated as paid;
- a Swahili time expression becomes the wrong appointment;
- code-switching causes the agent to lose the customer’s intent;
- a requested refund is described as already completed;
- an interruption is ignored while the agent continues the old task.

The goal is not to test whether a model can sprinkle Swahili words into a reply. The goal is to test whether the agent behaves correctly when local language, time, payments and support semantics affect real operations.

## The 5 public cases

| id | Production failure under test |
|----|-------------------------------|
| `ke-mpesa-late-no-code` | Late / unmatched M-Pesa claim — must not invent a receipt or mark paid |
| `ke-book-saa-kumi-kesho` | Swahili clock semantics — must not silently corrupt the booking time |
| `ke-lang-sheng-sw-en-mix` | Sheng → English → Kiswahili code-switching without losing intent |
| `ke-ecom-angry-refund` | Damaged-item refund pressure without fake completion or policy invention |
| `ke-voice-interrupt-barge` | Transcript-level proxy for interruption and intent persistence |

## Try the teaser

Import into **Promptfoo** or map the cases to another evaluation workflow such as Coval or Cekura.

```bash
npx promptfoo@latest eval -c promptfooconfig.teaser.yaml -j 1 --no-progress-bar
```

The public config defaults to Promptfoo’s **manual-input provider**, so you can paste a real reply from any agent without configuring API keys. For automated regression, replace that provider with your own OpenAI, Anthropic, HTTP or custom target.

### Private proof-eval status

A separate automated proof-eval harness for these five cases is **under development for the private commercial pack**. It is not included in this repository and is not required to use the public manual-input teaser.

## What a credible pass means

These are acceptance tests, not keyword demos. A passing agent should preserve the correct **business state and behaviour**.

Each scenario specifies:

- the local failure class;
- the business risk;
- locale assumptions;
- required behaviours;
- prohibited behaviours;
- explicit pass criteria;
- severity;
- review status.

The public Promptfoo config uses deterministic checks where practical. Production acceptance should combine deterministic assertions with human review or a separately configured evaluator appropriate to the system under test.

## Voice limitation

The public `voice-proxy` scenario is a **transcript-level semantic proxy** for interruption handling. It does not measure acoustic barge-in latency, VAD behaviour, duplex audio, packet loss or TTS interruption timing. Those require a voice-capable harness.

## Docs

- [`TEASER.md`](TEASER.md) — product narrative + pricing hypothesis
- [`FAILURE_STORY.md`](FAILURE_STORY.md) — short demo script
- [`SCENARIO_SCHEMA.md`](SCENARIO_SCHEMA.md) — acceptance-test contract
- [`LICENSE`](LICENSE) — evaluation-only; commercial pack separate

## What this is / is not

**Is:** a versioned QA specification expressed as synthetic acceptance scenarios.  
**Is not:** an AI agent, speech corpus, hosted test platform, certification mark, payment-rail implementation, or collection of live customer transcripts / PII.

## Commercial pack interest

Run the five public cases first. If the failure modes are relevant to your deployment, open a **GitHub Discussion** or **Issue** titled:

**`commercial pack interest`**

Say whether you are evaluating a starter or agency licence and what agent surface you are testing. **Do not post proprietary prompts, customer data, credentials or confidential deployment details.** A private contact / procurement route can be established separately.

---

**Break your agent on purpose before your customers do.**

Copyright (c) 2026 Lenatii. See [`LICENSE`](LICENSE).
