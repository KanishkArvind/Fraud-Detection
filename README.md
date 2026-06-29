# Fraud Detection System using Unsupervised ML and GenAI
This project builds an anomaly-based fraud detection workflow for banking transactions using unsupervised machine learning and a GenAI-powered explanation layer. It profiles normal customer behavior, flags suspicious deviations, and presents the results through an interactive dashboard for human review.

## Project Overview
The notebook focuses on moving beyond rules-based fraud checks and instead detecting unusual transaction patterns from historical behavior. It uses transaction history, velocity signals, login friction, and account balance relationships to surface risky activity. The final decision is intentionally left to a human reviewer, with the model acting as a decision-support layer rather than an automatic fraud verdict.

## Workflow
The pipeline starts by loading and cleaning transaction data, including parsing transaction timestamps and checking for missing values. It then engineers behavioral features such as signed transaction amount, historical average spend, amount-to-history ratio, days since last transaction, cumulative login failures, and signed balance ratio. After that, the notebook performs exploratory analysis, correlation checks, and feature transformation to prepare the data for anomaly detection.

## Modeling Approach
Two unsupervised algorithms are used: Isolation Forest and Local Outlier Factor. Isolation Forest identifies transactions that are easy to isolate in feature space, while LOF flags records whose local density is unusually low compared with nearby points. The notebook combines both model outputs into an ensemble fraud flag, which is used to create a broader risk perimeter.

## GenAI Dashboard
The project also includes a Gradio-based dashboard that displays flagged transaction details and an AI-generated explanation for why a transaction may look suspicious. The explanation prompt is structured to give a balanced risk assessment, including trigger metrics, a threat hypothesis, a benign alternative, and a recommended next check for analysts. This makes the project more practical for fraud operations teams that need interpretable outputs.

## Tech Stack
- Python:
  - Pandas, NumPy
  - Matplotlib, Seaborn
  - scikit-learn, including Isolation Forest, Local Outlier Factor
  - Gradio (for interactive dashboard)

- LLM:
  - Google Generative AI (gemini-3.1-lite)



