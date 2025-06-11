# Employee Sentiment Analysis

Overview
This repository implements a complete pipeline to process, analyze, and model employee message data for sentiment insights and engagement metrics. Deliverables include:

1. **Sentiment Labeling**  
   - Automatically classify messages as Positive, Neutral, or Negative using transformer-based or lexicon-based models, with threshold boundaries validated against a labeled sample.

2. **EDA & Visualization**  
   - Bar chart of overall sentiment distribution  
   - Monthly sentiment proportion trend line chart
   - Analyze sentiment distribution and monthly trends. Visualizations include a bar chart of overall sentiment and a time-series plot, each interpreted with business context to explain the implications.

3. **Monthly Sentiment Scoring**
   - Convert sentiment to numerical scores (+1, 0, -1) and compute aggregated scores by employee and month.
   - Maps Positive → +1, Negative → –1, Neutral → 0  
   - Aggregates by employee and month to produce `monthly_scores`
4. **Employee Ranking**
   - Determine top 3 and bottom 3 employees by sentiment score in a given month. For example, in May 2010, the top performers were:
   - don.baughman@enron.com (Score: 8)
   - patti.thompson@enron.com (Score: 7)
   - sally.beck@enron.com (Score: 6)
   - And the bottom performers were:
   - johnny.palmer@enron.com (Score: 0)
   - bobette.riner@ipgdirect.com (Score: 1)
   - john.arnold@enron.com (Score: 1)

5. **Flight Risk Identification**
   - Employees with ≥4 negative messages in any 30-day window are flagged. Identified flight risks:
   - bobette.riner@ipgdirect.com
   - johnny.palmer@enron.com
   - lydia.delgado@enron.com
   - patti.thompson@enron.com
   - rhonda.denton@enron.com
   - sally.beck@enron.com

6. **Trend Forecasting**  
   - Builds a simple linear regression model to predict next month’s average sentiment score per employee
   - A linear regression model predicts the next month’s average sentiment score based on message volume and current sentiment. Achieved MSE: 0.0617.

## Repository Structure
employee-sentiment-analysis/
├── test(in).csv                # Input data
├── analysis.ipynb              # Jupyter notebook covering Tasks 1–6
├── requirements.txt            # Python dependencies
└── README.md                   # Project overview and documentation

## Methodology & Justification
Sentiment Thresholds: Chosen cautiously to reflect business tone; ±0.1 ensures neutral region absorbs minor polarity fluctuations.

Tool Limitations: TextBlob was used but acknowledged for domain mismatch; validating on corporate language is encouraged.

Interpretation Matters: Every visualization is supported by a narrative. For instance, a neutral-heavy trend suggests risk of disengagement despite low negativity.

Metric Design: Simple score mapping with interpretable logic (+1, 0, -1); avoids over-engineering while remaining explainable.

Flight Risk Policy: Rolling 30-day window aligns with HR monitoring cycles; threshold of 4 negative messages is empirically tested.

Model Performance: MSE was preferred over R² alone for its robustness to outliers, aligning with Q&A best practices.

## Key Insights
Most of the information is positive and neutral, indicating that most people can maintain a positive and stable emotional state at work, and the few that are negative indicate that the overall work environment in the company is positive and active.

The consistently high moods of high performing employees reflect the fact that there is a positive relationship between high performance and mood .
Flagged employees may need the attention of their managers to facilitate the management of task assignments, these employees can go for assigning simple and unimportant tasks to ease their emotions and can reduce the company's loss of errors.

Predictive trending can be a good way to help managers see potential risks in their employees, and can be used early to minimize future losses through interviews or increased training.
