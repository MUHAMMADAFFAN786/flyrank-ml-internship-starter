# FL-09 — Documentation

# Machine Learning for Content Refresh Prioritization

## Abstract

This project investigates whether machine-learning signals can help prioritize content items for human review. A Random Forest model was compared with a Week-4 hand-written baseline using the prepared FlyRank internship dataset and the defined validation setup.

The evaluation measures observed performance under the selected split rather than guaranteeing future outcomes. The resulting model output was converted into a ranked action queue with reason codes for practical review.

The final recommendations are intended as directional decision-support and require human judgment before any content changes are made.

## 1. Research Question

**Research question:**

Can a machine-learning model identify content items that may deserve refresh or review based on observed historical performance signals?

**Decision supported:**

Which content items should a human reviewer look at first?

The goal is not to predict guaranteed future performance. The model is used as directional decision-support to compare a learned approach with the Week-4 baseline and identify items that may deserve further review.

## 2. Data

This analysis uses the prepared FlyRank ML Internship dataset available in the repository.

The dataset contains anonymized content-performance information used to construct model features and evaluate the refresh-prioritization task.

The dataset contains approximately 30,000 rows and 44 columns.

The analysis uses historical content-performance signals such as impressions, clicks, sessions, CTR, average position, content age, freshness, and trend information.

Private client identifiers, private queries, and information that is not necessary for the public research artifact were excluded from the analysis.

The available historical data and validation setup are used for evaluation. The exact data files and processing steps are preserved in the repository so the work can be inspected and rerun.

## 3. Methodology

The task is treated as a supervised machine-learning problem.

A Random Forest model was used to learn from historical feature signals and estimate which content items may deserve refresh or review.

The Random Forest model was compared with the Week-4 hand-written baseline using the same evaluation metric and evaluation setup.

**Model:** Random Forest

**Baseline:** Week-4 hand-written baseline

**Task:** Content refresh prioritization

**Features:** Historical content-performance signals

**Validation:** Week-5/Week-6 validation setup

A leakage review was also included as part of the validation audit.

The model output is treated as directional decision-support rather than a guaranteed prediction.

## 4. Results vs Baseline

The Random Forest model was compared with the Week-4 hand-written baseline using Precision@50.

| Method | Precision@50 |
|---|---:|
| Week-4 Hand-written Baseline | 0.24 |
| Random Forest | 0.74 |

The observed difference was **0.50 Precision@50**.

The Random Forest showed higher observed Precision@50 than the Week-4 baseline on the evaluated data.

This result represents observed performance on the evaluated data and does not guarantee future performance on new content.

## 5. Limitations

This analysis cannot establish that recommended content changes will definitely improve future performance.

The model is limited by:

- Available historical data
- Selected features
- Target definition
- Validation design
- Changes in the underlying content environment
- Information not represented in the model features

A measured improvement over the baseline does not automatically mean that the model will generalize to every new situation.

The model does not replace human review. Content quality, relevance, business context, and unusual situations may require information that is not represented in the model.

The results should therefore be treated as observed and directional evidence for prioritization and decision-support.

## 6. Ranked Recommendations

The validated model output was converted into a ranked action queue for human review.

The queue prioritizes content items using the observed model signals and reason codes.

The highest-ranked items can contain signals such as:

- Declining performance
- Low CTR
- Model decline risk
- Visibility or ranking concerns
- Content freshness signals

The ranked queue should not be treated as an automatic publishing instruction.

Before making a content change, a reviewer should check:

1. Current content quality
2. Recent performance
3. Search relevance
4. Business context
5. Model reason codes

The queue is therefore intended as a practical decision-support tool rather than an autonomous publishing system.

## 7. Supporting Artifacts

The repository preserves the notebooks and outputs used to support this analysis.

Important artifacts include:

- `work/notebooks/w05_model.ipynb`
- `work/notebooks/w06_validation_audit.ipynb`
- `work/notebooks/w07_action_playbook.ipynb`
- `work/notebooks/capstone.ipynb`
- `outputs/refresh_queue_sample.csv`
- `outputs/model_report.md`

These artifacts make the analysis traceable from the research question through modeling, validation, and recommendations.

## 8. Demo Summary

### Question

Can machine-learning signals help prioritize content items that may deserve refresh or human review?

### Method

A Random Forest model was compared with the Week-4 hand-written baseline using the prepared FlyRank ML Internship dataset and the defined validation setup.

### Evidence

The Random Forest achieved an observed Precision@50 of 0.74 compared with 0.24 for the Week-4 baseline.

### Honest Result

The result represents measured performance on the selected evaluation data. It is directional evidence and does not guarantee future content performance.

### Recommendation

Use the ranked action queue to prioritize content for human review. Reviewers should check current content, relevance, recent performance, and reason codes before taking action.

## 9. Self-Check

- Research question stated
- Data source and public-safe handling documented
- Methodology documented
- Model and baseline compared
- Validation and leakage review documented
- Results reported honestly
- Limitations documented
- Ranked recommendations documented
- Supporting artifacts referenced
- Human review required
- No private client information included

## Acknowledgments & Data Credit

This work was built as part of the FlyRank ML Internship and uses the FlyRank ML Internship dataset.

**Data credit: FlyRank**

---

**Claim language used:** observed, measured, directional, decision-support.

**The results do not claim guaranteed future performance.**
