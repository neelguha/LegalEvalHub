# Draft PR title

Proposal for review: eight exploratory 24-item Qwen3-4B-Q4_K_M component cohorts

# Draft PR body — eligibility review; ingestion and merge blocked

I am proposing eight partial-cohort results for **Qwen3-4B-Q4_K_M** under applicant name **Mohammed Mazen Al Nasser**. This is a standalone component study; the deployed MERENVAY product was not evaluated, and this identity does not describe its architecture.

**Draft eligibility proposal: please review before ingestion or merge. Hold these runs from full-task and aggregate rankings.** Each task has only 24 selected test examples. The contribution guide's `n_samples` field records that fact but does not establish acceptance or comparability, and no verified JSON flag in this proposal enforces the requested hold. The candidate JSON files are deliberately located under `proposals/merenvay-component-study-20261017/candidate_records/`, outside `eval_runs/`. This placement is a review boundary; it does not establish that every possible ingestion path excludes them.

| Task | Correct / n | Accuracy | Balanced accuracy | Macro F1 | Micro F1 | Valid ratio |
|---|---:|---:|---:|---:|---:|---:|
| `hearsay` | 16 / 24 | 66.67% | 0.664336 | 0.664336 | 0.666667 | 1.000000 |
| `ucc_v_common_law` | 21 / 24 | 87.50% | 0.812500 | 0.841758 | 0.875000 | 1.000000 |
| `cuad_anti-assignment` | 24 / 24 | 100.00% | 1.000000 | 1.000000 | 1.000000 | 1.000000 |
| `contract_nli_limited_use` | 23 / 24 | 95.83% | 0.944444 | 0.954459 | 0.958333 | 1.000000 |
| `abercrombie` | 11 / 24 | 45.83% | 0.476190 | 0.357143 | 0.458333 | 1.000000 |
| `personal_jurisdiction` | 13 / 24 | 54.17% | 0.541667 | 0.419780 | 0.541667 | 1.000000 |
| `legal_reasoning_causality` | 14 / 24 | 58.33% | 0.642857 | 0.555556 | 0.583333 | 1.000000 |
| `cuad_cap_on_liability` | 20 / 24 | 83.33% | 0.833333 | 0.832168 | 0.833333 | 1.000000 |

Group A: 84/96 (87.50%). Group B: 58/96 (60.42%). These use different task cohorts and support no improvement or suite-ranking claim. The attached transparent appendix discloses the separate later 8/16 (50.00%) screen, its four individual results, the CUAD eligibility deviation, and the operationally aborted predecessor. Those screen results are not candidate ranked entries.

The proposed metric dictionaries include every metric required by the eight pinned task definitions: accuracy, balanced_accuracy, f1_macro, f1_micro, valid_predictions_ratio, plus n_samples. Scores were rebuilt from frozen outputs/keys using whole-output ASCII punctuation removal, strip and lowercase; no label extraction, new inference or post-result cohort replacement was performed. All 192 candidate outputs are valid labels under this local rule.

Maintainer questions blocking ingestion and merge:

1. Can these partial cohorts be reviewed/displayed separately while excluded from full-task and aggregate rankings?
2. Which dataset split/version and sample denominator are required, given that official metadata totals differ from the archived test row counts?
3. Are the proposed prompt identifier, normalization and validity/metric conventions acceptable, and what ingestion/schema checks apply?
4. What non-proprietary prediction evidence is needed? There is currently no hosted public predictions file, so the optional predictions_url is omitted.

The unchanged JSON `submission_time` values record local proposal preparation at `2026-10-17T20:30:32Z`, not successful submission or acceptance. Any posted draft PR has its own GitHub creation timestamp. Please confirm timestamp semantics before any accepted record ingestion. No prompt bytes, proprietary code, model/server binary digests, runtime fingerprints, internal orchestration, credentials or client/employer data are included in the public proposal.

Status: DRAFT_ELIGIBILITY_PROPOSAL. Posting and review status are recorded by this GitHub PR; no acceptance or ranking is claimed. Please resolve the questions above before ingestion or merge.

References: [pinned contribution guide](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/CONTRIBUTING.md), the eight pinned task JSON sources listed below, and [task catalog](https://www.legalevalhub.ai/tasks).

Pinned task definitions: [`hearsay`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/hearsay.json), [`ucc_v_common_law`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/ucc_v_common_law.json), [`cuad_anti-assignment`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/cuad_anti-assignment.json), [`contract_nli_limited_use`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/contract_nli_limited_use.json), [`abercrombie`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/abercrombie.json), [`personal_jurisdiction`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/personal_jurisdiction.json), [`legal_reasoning_causality`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/legal_reasoning_causality.json), [`cuad_cap_on_liability`](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/tasks/cuad_cap_on_liability.json).
