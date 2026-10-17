# Exploratory partial-cohort proposal — hold for maintainer review

Applicant: **Mohammed Mazen Al Nasser**. Evaluated public identity: **Qwen3-4B-Q4_K_M**, a standalone public-data component study. The deployed MERENVAY product was not evaluated. This component identity is not a disclosure or description of MERENVAY's architecture.

Status: **DRAFT_ELIGIBILITY_PROPOSAL**. Posting and review status are recorded by the associated GitHub PR; no acceptance or ranking is claimed. The eight candidate records describe 24 examples per task, not full-task results. They are staged under `proposals/merenvay-component-study-20261017/candidate_records/`, outside the repository's `eval_runs/` tree, for eligibility review before any ingestion or merge. This placement is a review boundary; ingestion behavior has not been verified. Hold them out of all full-task and aggregate rankings unless maintainers explicitly approve a separate, clearly labelled partial-cohort treatment. Their `n_samples` fields disclose denominator size; those fields do not establish acceptance or comparability. The JSON shape has no verified ranking-exclusion control, so this written hold is not machine-enforced.

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

All eight completed 24-item task results are included. Group A was 84/96 (87.50%); Group B was 58/96 (60.42%). These are different task cohorts and are not an improvement comparison or a LegalBench suite score. Four later tiny-screen results, including the lower results and a CUAD protocol qualification, are disclosed in [TRANSPARENT_APPENDIX.md](TRANSPARENT_APPENDIX.md), without candidate ranked JSON files.

## Method and limits

- Data: public `nguha/legalbench`, frozen revision `daec8237410aa23e3faf4bc41ad8b3a7e1696826`; 24 selected test rows per candidate task. Source rows were selected by seeded, unstratified shuffling from the recorded eligible pools; class proportions vary. Exact known exposure exclusions were applied as recorded; broader training contamination remains unknown.
- Benchmark base few-shot templates were combined with a generic answer-format instruction. The proposed `prompt_id` `legalbench_base_label_only_component_v1` identifies this component-study configuration; it is not a claim of equivalence to another submitter's `base` configuration. Prompt bytes are not part of this proposal.
- Frozen outputs were rescored without inference: remove all ASCII `string.punctuation` characters from the whole output, strip leading/trailing whitespace, and lowercase; compare the entire normalized output to the normalized key. No answer substring extraction or answer repair. Request/context failures, empty outputs and truncated generations count incorrect in the planned cohort. No such generation failures occur in the eight candidates.
- Accuracy is correct/n; balanced accuracy is mean class recall; macro F1 is mean per-class F1; micro F1 pools class true/false positives/negatives. Every source class is represented in each candidate sample. All 192 candidate outputs are valid label strings under the local rule. Proposed `valid_predictions_ratio` means successful whole-output label predictions/n, including incorrect labels as valid. Maintainers must confirm this definition and the normalization policy.
- Scores were independently recomputed from the archived outputs and keys, then cross-checked with a separate installed metrics implementation. Local integrity and required-field checks are not service acceptance or external attestation.
- No public predictions host exists for this proposal. The optional `predictions_url` is omitted. Raw outputs, prompts and private execution material are not included in the release scope.

## Questions blocking ingestion and merge

1. Maintainer confirmation that partial test cohorts are acceptable and can be displayed separately without entering full-task/aggregate rankings. The contribution guide specifies `n_samples` but states no explicit minimum; that silence is not permission for comparable ranking.
2. Confirmation of the required dataset/split/version and how the repository's total sample counts relate to the frozen test populations shown in the appendix.
3. Confirmation of the proposed prompt identifier, whole-output normalization, validity rule and metric conventions. No running service schema/ingestion validator was used; an accepted schema cannot be asserted.
4. Agreement on reviewable prediction evidence if required without proprietary disclosure, and the timestamp semantics required before any accepted record ingestion. The unchanged `submission_time` values record proposal preparation at `2026-10-17T20:30:32Z`; they do not establish successful submission, acceptance, or ranking. Any posted draft PR has its own GitHub creation timestamp.

## Official references

Rules and task metadata were read at repository revision `31e226b3b466799216c42d47924dcad151285a7a` on 2026-10-17. [Contribution guide](https://github.com/neelguha/LegalEvalHub/blob/31e226b3b466799216c42d47924dcad151285a7a/CONTRIBUTING.md); [public task catalog](https://www.legalevalhub.ai/tasks). Per-task source links and sample counts appear in the appendix. A structural JSON proposal does not establish official eligibility.
