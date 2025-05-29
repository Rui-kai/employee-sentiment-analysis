# Employee Sentiment Analysis

This project implements end-to-end sentiment analysis on employee messages, covering:
1. **Sentiment Labeling**  
   - Uses TextBlob to compute each message’s polarity and classify it as Positive, Negative, or Neutral.

2. **EDA & Visualization**  
   - Bar chart of overall sentiment distribution  
   - Monthly sentiment proportion trend line chart

3. **Monthly Sentiment Scoring**  
   - Maps Positive → +1, Negative → –1, Neutral → 0  
   - Aggregates by employee and month to produce `monthly_scores`

4. **Top/Bottom N Employees**  
   - Retrieves the top 3 and bottom 3 scoring employees for any given month

5. **Flight-Risk Identification**  
   - Flags employees who posted 4 or more negative messages within any rolling 30-day window

6. **Trend Forecasting**  
   - Builds a simple linear regression model to predict next month’s average sentiment score per employee

## Repository Structure
