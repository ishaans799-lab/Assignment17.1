# Comparing Classifiers for Bank Marketing Campaigns

This project completes Required Assignment 17.1 by comparing four supervised classification models on the UCI Bank Marketing dataset:

- k-nearest neighbors
- logistic regression
- decision tree
- support vector machine

## Notebook

Open the completed notebook here: [prompt_III.ipynb](prompt_III.ipynb)

## Business Problem

The bank wants to improve the efficiency of telephone marketing campaigns for term deposits. The modeling goal is to identify customers who are more likely to subscribe so campaign teams can prioritize better leads, reduce wasted calls, and monitor the tradeoff between precision and recall.

## Summary of Findings

- The target is imbalanced: about 11.3% of contacted clients subscribed to a term deposit.
- Accuracy alone is misleading because a majority-class baseline is already about 88.7% accurate while finding no subscribers.
- `duration` is excluded from predictive modeling because it is only known after a call and would create leakage for pre-call targeting.
- Logistic regression produced the strongest held-out average precision in this run, with support vector machine performance very close behind.
- Prior campaign outcome, contact channel, month, and economic context variables were among the most important practical signals.

## Best Model Result

The best model by held-out average precision was logistic regression:

| Metric | Score |
| --- | ---: |
| Average precision | 0.453 |
| ROC-AUC | 0.798 |
| Accuracy | 0.830 |
| Precision | 0.358 |
| Recall | 0.649 |
| F1 | 0.462 |

## Recommendations

- Use model scores to create campaign priority tiers instead of contacting customers uniformly.
- Prioritize high-scoring customers for agent outreach and use lower-cost channels for medium-score groups.
- Monitor precision, recall, and average precision over future campaign waves.
- Validate on later time periods and add campaign cost/customer value data before production use.

## Files

- `prompt_III.ipynb`: completed and executed Jupyter Notebook.
- `data/bank-additional-full.csv`: full UCI Bank Marketing dataset used for analysis.
- `data/bank-additional.csv`: smaller sample included with the starter files.
- `data/bank-additional-names.txt`: data dictionary and citation information.
