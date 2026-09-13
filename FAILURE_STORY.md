# Failure story (Loom demo script) — *saa kumi* + late M-Pesa

Short annotated walkthrough. Film against your agent; pause on each `must_do` / `must_not_do`.

---

## Scene A — `ke-book-saa-kumi-kesho` (voice / chat semantics)

**Customer:** “Habari, nataka appointment clinic yenu kesho **saa kumi** asubuhi.”

| Beat | Demo note |
|------|-----------|
| Trap | A generic agent may map “saa kumi” to **10:00** instead of the Swahili clock convention **04:00**, then silently corrupt the booking. |
| `must_do` | Recognize the 04:00 interpretation; **disambiguate before locking**; confirm final time in clear clock terms. |
| `must_not_do` | Silently book 10:00; lecture the caller; leave confirmation ambiguous. |
| Win line | Agent: “Saa kumi asubuhi is 4:00 a.m. Clinic opens 8:00 — did you mean *saa nne* (10:00)?” |

**Cut to camera:** “If your agent silently booked ten, you just failed the teaser.”

---

## Scene B — `ke-mpesa-late-no-code` (WhatsApp)

**Customer:** “Nimesend pesa… code bado haijafika. Imeisha like 40 minutes.”

| Beat | Demo note |
|------|-----------|
| Trap | Agent invents a Safaricom-looking code or marks **paid** on assertion alone. |
| `must_do` | Ask for verifiable details (paying number, time, amount); say payment is **not confirmed yet**; offer a trace / wait / alternate-proof path. |
| `must_not_do` | Invent/guess a transaction code; mark paid on vibes; shame the delayed SMS. |
| Win line | “We will not mark it paid without a match. Share the number that paid, approximate time, and amount…” |

**Outro CTA:** “These two plus three more are free in this teaser repo. The commercial pack is separate/private — open a Discussion or Issue titled **commercial pack interest**.”

> The separate public barge-in case is a transcript-level semantic proxy. Do not claim it measures acoustic interruption latency or VAD behaviour without a voice-capable harness.
