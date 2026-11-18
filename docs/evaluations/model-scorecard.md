# Model scorecard — rule R1 (pensionableSalary)

> One run is a sample, not a benchmark. Synthetic data only — never paste secrets or real member data.

| | Model A | Model B |
|---|---|---|
| Model (name as shown in the picker) | Claude Haiku 5.5 | GPT-6.1 Terra |
| Harness · Mode · Permissions | Not recorded | Not recorded |
| Reasoning effort | Not recorded | Not recorded |
| Date | 2026-11-18 | 2026-11-18 |

Model B received the same prompt in the same chat, but no answer was recorded. This was not an independent-chat comparison.

## Scores

| Criterion | How to score | Model A | Model B |
|---|---|---|---|
| Correctness verified | Expected values that match the `node -e` output (x / 5) | Not run / 5 | No answer / 5 |
| Edge cases found | Which did it cover? franchise boundary · salary cap · part-time · below franchise → 0 · invalid factor (0 or > 1) · negative salary | Zero salary, franchise boundary, salary cap, above cap with part-time factor, zero factor; no negative salary | No answer recorded |
| Hallucinations | Invented functions, parameters, files or rules? List them (none = 👍) | None identified in the answer | Not assessable |
| Latency feel | fast / ok / slow | Not recorded | Not recorded |
| Cost / credits | Relative cost of the model (supported-models doc) — heavier model = more AI credits | Not recorded | Not recorded |

## Verification output

52000 1 34455
46000 0.6 17073
150000 1 120255
16000 0.9 0

17545 1 0
137801 1 120255
50000 0 RangeError: partTimeFactor must be greater than 0 and at most 1

## Verdict

- For **this kind of task** I would use: No model selected yet.
- Because: Model B has no recorded answer and neither model has runtime verification.
- Would I trust it **without** the `node -e` check? No — execute the function to verify the exact values and errors.
- To make this a real benchmark I would need: Independent chats, multiple tasks and runs, the same scoring rule, measured latency and credit usage.
