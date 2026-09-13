# Scenario schema — public teaser

The acceptance pack is a **QA specification**, not a prompt collection. Each scenario should define the local failure mode, the business risk, and the exact behaviours required for a pass.

## Core fields

- `schema_version` — version of the scenario contract.
- `id` — stable scenario identifier.
- `title` — human-readable test name.
- `channel` — `whatsapp`, `chat`, `voice-proxy`, or another explicit surface.
- `languages` — locale/language mix exercised by the case.
- `failure_class` — the production failure this case is designed to expose.
- `business_risk` — why the failure matters commercially or operationally.
- `locale_assumptions` — local semantic assumptions the evaluator must understand.
- `persona` — synthetic customer persona; never a real customer record.
- `setup` — business context and the agent's task.
- `turns` — synthetic conversation turns.
- `expected_outcomes` — outcome-level expectations.
- `must_do` — required agent behaviours.
- `must_not_do` — disallowed agent behaviours.
- `pass_criteria` — explicit criteria that must all hold for a production pass.
- `review_status` — whether the case is draft, reviewed, or validated.
- `last_validated` — date of the most recent human review of the scenario semantics.
- `severity` — impact if the agent fails the case.
- `tags` — searchable scenario categories.

## Evaluation principle

A scenario should not pass merely because the output contains a convenient keyword. A credible acceptance test should require the **right business state and behaviour**, for example:

- recognizing `saa kumi asubuhi` as 04:00 in the relevant Swahili clock convention;
- refusing to mark an M-Pesa payment as confirmed without a verifiable match;
- following the customer's meaning across Sheng, English, and Kiswahili code-switching;
- acknowledging a damaged-item refund request without inventing policy or refund completion;
- yielding to an interruption before continuing the original policy script.

The executable Promptfoo teaser uses deterministic checks where possible, but these five public cases are still examples. Commercial acceptance should combine deterministic assertions with human review or a separately configured evaluator appropriate to the buyer's system.

## Voice note

The public `voice-proxy` case is a **transcript-level semantic proxy** for interruption handling. It does not measure real acoustic barge-in latency, VAD behaviour, duplex audio, packet loss, or TTS interruption timing. Those require a voice-capable harness and should not be claimed from a text-only run.

## Privacy

All public scenarios are synthetic. Do not add real customer recordings, phone numbers, payment identifiers, transcripts, or other PII to this repository.
