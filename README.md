# Machine Learning for Content Refresh Prioritization

## Research Question

Can a machine-learning model identify content items that may deserve refresh or review based on observed historical performance signals?

The decision supported is prioritization: which content items should a human reviewer look at first?

## Project Overview

This project is part of the FlyRank ML Internship and focuses on content refresh prioritization.

The workflow uses historical content-performance signals to compare a machine-learning approach with a transparent Week-4 hand-written baseline.

The final model output is converted into a ranked action queue for human review.

> The output is directional decision-support. It is not a guarantee of future performance and does not automatically publish or change content.

## Method

- **Model:** Random Forest
- **Baseline:** Week-4 hand-written baseline
- **Task:** Content refresh prioritization
- **Features:** Historical content-performance signals
- **Validation:** Week-5 / Week-6 validation setup
- **Leakage review:** Week-6 validation audit
- **Intended use:** Directional decision-support for human review

## Data

The working dataset contains approximately 30,000 rows and 44 columns.

The analysis uses the prepared FlyRank ML Internship dataset.

Public-safe handling is used throughout the project. Private client names, domains, private queries, credentials, and raw private exports are not included.

## Results

The Random Forest was compared with the Week-4 hand-written baseline using the same evaluation setup.

| Method | Precision@50 |
|---|---:|
| Week-4 Hand-written Baseline | 0.24 |
| Random Forest | 0.74 |

**Observed difference: 0.50 Precision@50**

This is measured performance on the evaluated data. It does not guarantee future performance on new content.

## Ranked Recommendations

The model output is converted into a ranked action queue with reason codes.

Items near the top of the queue are prioritized for human review based on the observed model signals.

Before taking action, a reviewer should check:

- Current content
- Recent performance
- Relevance
- Reason codes
- Business and editorial context

The queue is a decision-support tool rather than an autonomous publishing system.

## Limitations

1. Historical data may not represent every future situation.
2. Model performance depends on the selected features and target definition.
3. Validation results do not guarantee future performance.
4. Content quality and business context may not be fully represented by the model features.
5. Recommendations require human review.
6. The output is decision-support, not automatic production action.

## Reproducibility

Important project artifacts:

- `work/notebooks/w05_model.ipynb`
- `work/notebooks/w06_validation_audit.ipynb`
- `work/notebooks/w07_action_playbook.ipynb`
- `work/notebooks/capstone.ipynb`
- `outputs/refresh_queue_sample.csv`
- `outputs/model_report.md`

The notebooks and exported artifacts provide the analysis trail from modeling through validation and ranked recommendations.

## AI Transparency

AI assistants were used to help with documentation, wording, and workflow guidance. Model results, project outputs, and final claims were checked against the actual notebook outputs and available project artifacts.

## Acknowledgments & Data Credit

This work was built as part of the FlyRank ML Internship and uses the FlyRank ML Internship dataset.

Data credit:

https://flyrank.ai/
