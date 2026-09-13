# Teaser — Kenya Agent Acceptance Pack

Your American-English demo agent says: *“Sure! I can help with that appointment tomorrow at ten.”*

Your Nairobi caller says: **“Boss, nilishalipa M-Pesa jana”** — and books **saa kumi**.

Same product. Different failure mode.

The point of this pack is not to test whether a model can sprinkle Swahili words into a reply. It is to test whether the agent preserves the **correct business state** when Kenyan language, time, payment and support semantics get messy.

## Touch it without buying the vault

Five free hard cases live in [`scenarios/`](scenarios/):

- unmatched / delayed M-Pesa payment;
- *saa kumi* booking ambiguity;
- Sheng ↔ English ↔ Kiswahili code-switching;
- damaged-item refund pressure;
- interruption / barge-in semantic proxy.

Import them. Break your agent on purpose. That is the point.

The **commercial pack** is a **separate private product**: additional hard cases, versioned updates, stronger evaluator mappings, and written commercial/agency licensing.

## What buyers get (hypothesis)

| | |
|--|--|
| **Starter** | Additional Kenya hard cases, versioned scenario schema, Promptfoo/Coval-shaped mappings, severity + business-risk tags, update cadence | **€149–€249 hypothesis** |
| **Agency licence** | Multi-client commercial use and redistribution terms in writing | on request |

Pricing is a **hypothesis**, not a live checkout. No fake testimonials or fake customer logos.

## Why this is not “just prompts”

Each case carries:

- an explicit failure class;
- business risk;
- locale assumptions;
- required and prohibited behaviours;
- pass criteria;
- severity;
- human review status.

A test should fail an agent that sounds fluent but leaves the business in the wrong state.

## What this is NOT

- Not an AI agent, chatbot, or runtime
- Not a speech / audio corpus
- Not a Promptfoo replacement
- Not Conekta (or any payment-rail) code
- Not live customer transcripts or PII
- Not a certification mark
- **Not the full commercial pack**

## Commercial pack interest

1. Run the five samples (`npx promptfoo@latest eval -c promptfooconfig.teaser.yaml -j 1 --no-progress-bar`). Paste real agent replies, or swap in your own automated provider.
2. Open a **GitHub Discussion** or **Issue** titled **`commercial pack interest`**.
3. Say starter vs agency licence and the agent surface you are evaluating.
4. Do **not** post proprietary prompts, customer data, credentials, or confidential deployment details.

A private contact/procurement route can be established separately after initial interest.
