# Transparent appendix

Draft eligibility proposal. Posting and review status are recorded by the associated GitHub PR; no acceptance or ranking is claimed. Candidate JSON bytes and their preparation timestamps are unchanged. Records are staged under `candidate_records/` for review, outside `eval_runs/`; no ingestion-exclusion behavior has been verified.

## Candidate cohort sizes

| Task | Evaluated n | Frozen test rows | Recorded eligible pool | Official metadata samples | Official metadata |
|---|---:|---:|---:|---:|---|
| `hearsay` | 24 | 94 | 94 | 99 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/hearsay.json) |
| `ucc_v_common_law` | 24 | 94 | 94 | 100 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/ucc_v_common_law.json) |
| `cuad_anti-assignment` | 24 | 1172 | 1172 | 1178 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/cuad_anti-assignment.json) |
| `contract_nli_limited_use` | 24 | 208 | 175 | 216 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/contract_nli_limited_use.json) |
| `abercrombie` | 24 | 95 | 71 | 100 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/abercrombie.json) |
| `personal_jurisdiction` | 24 | 50 | 26 | 54 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/personal_jurisdiction.json) |
| `legal_reasoning_causality` | 24 | 55 | 31 | 59 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/legal_reasoning_causality.json) |
| `cuad_cap_on_liability` | 24 | 1246 | 1222 | 1252 | [task JSON](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/cuad_cap_on_liability.json) |

The official metadata totals and frozen test populations differ. This proposal does not assume that they refer to interchangeable denominators or establish which split/version the service expects. Each candidate metric uses its actual 24-item denominator.

Group A has documented prior local experimentation on `contract_nli_limited_use`; recorded exposed item IDs were excluded. Some historical raw experiment originals are absent, so portions of the prior-exposure audit rely on retained exports. Group B excluded the recorded prior 192 selected texts, train/template exact overlaps and duplicate text under its frozen eligibility rule. These are exact-match controls, not evidence that pretraining or semantic contamination is absent.

## Operationally aborted predecessor

Before completed Group B, a separate 96-item attempt was operationally aborted after repeated request timeouts. It retained 54 recorded rows, including five recorded timeouts and 49 response rows; 41 items were definitely unattempted and one item had uncertain interrupted/not-started status. No completed-run score is claimed for that attempt; its outputs were not merged into Group B. The revised completed run used a separate frozen cohort excluding all 96 selected predecessor texts. This is a disclosed protocol restart, not an omitted completed result.

## Later four-item-per-task screen — no candidate ranked entries

The subsequent frozen screen was **8/16 (50.00%)**, using the same whole-output normalization. All four task results are shown:

| Later screen task | Correct / n | Strict accuracy | Proposed valid-output ratio |
|---|---:|---:|---:|
| `corporate_lobbying` | 3 / 4 | 75.00% | 1.00 |
| `proa` | 1 / 4 | 25.00% | 0.25 |
| `international_citizenship_questions` | 1 / 4 | 25.00% | 1.00 |
| `cuad_termination_for_convenience` | 3 / 4 | 75.00% | 1.00 |

`proa` includes outputs such as `A: No`; ASCII punctuation removal gives `a no`, which is not a complete valid `no` label under the frozen rule. They remain incorrect; no substring extraction is used.

The independent protocol review status is **PASS_WITH_PROTOCOL_DEVIATION**. For `cuad_termination_for_convenience`, unused `document_name` metadata entered content hashing. That caused three known prior prompt texts to remain in the eligible pool (430 rather than the intended 427); the actual selected four rows had no detected exact prompt-text overlap. Applying the intended exclusion would change the shuffled sample. The observed cohort and its 3/4 result remain preserved and qualified; no resampling, replacement inference or counterfactual score is presented.

Four rows per task are too small for a performance or improvement claim. None of these four screen tasks has a proposed ranked JSON entry. All results are exploratory component evidence, not a product certification or an official ranking.
