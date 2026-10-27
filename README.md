# 📈Bank Marketing Campaign Analysis
## 🎯Description
This capstone project explores a Portuguese bank's direct marketing campaign data to understand patterns associated with customer subscriptions to term deposits. Python-based data cleaning, descriptive statistics, exploratory data analysis (EDA), and visualizations are used to compare customer groups and campaign outcomes. The goal is to support data-informed targeting and campaign planning rather than to establish causal effects.

- **Project domain:** Banking and Marketing Analytics
- **Dataset:** UCI Machine Learning Repository — Bank Marketing
- **Dataset link:** https://archive.ics.uci.edu/dataset/222/bank+marketing

## 🎯Project Objectives
1. Evaluate overall term-deposit subscription performance.
2. Compare subscriptions across contact months and contact methods.
3. Examine the relationship between campaign contact frequency and subscription.
4. Identify age and job groups with higher subscription rates.
5. Explore associations with call duration and earlier campaign contacts.
6. Investigate customer age, balance, and campaign segmentation patterns.

## 🎯Dataset Overview
- The notebook uses 45,211 records and 17 original columns.
- The original subscription target y is renamed to subscription for readability.
- It contains 5,289 yes and 39,922 no outcomes, corresponding to an overall subscription rate of approximately 11.70%.

**Original columns:** age, job, marital, education, default, balance, housing, loan, contact, day, month, duration, campaign, pdays, previous, poutcome, y.

## 🎯Tools and Technologies
- Python
- Pandas and NumPy — data manipulation and numerical analysis
- Matplotlib and Seaborn — visualizations
- Google Colab / Jupyter Notebook — notebook execution
- Excel (.xlsx) — input data format in the displayed notebook

## 🎯Data Cleaning and Preprocessing
- Inspected the dataset using head(), tail(), info(), shape, dtypes, and describe().
- Checked all columns for null values; no standard null values were reported.
- Examined text-based unknown categories separately:
    1. job (288),
    2. education (1,857),
    3. contact (13,020), and
    4. poutcome (36,959).
     - These were retained for analysis.
- Checked fully duplicated rows; the notebook reports zero duplicates.
- Renamed y to subscription.
- Identified numerical and categorical columns, calculated skewness and kurtosis, and detected potential outliers with the IQR method.
- Created age groups and indicators for subscription and previous campaign contact where needed for charts.

## 🎯Main Analysis and Visualizations
1. **Overall marketing campaign success:** Donut chart of subscribing and non-subscribing customers.
2. **Monthly subscription pattern:** Month-wise subscription analysis.
3. **Contact method performance:** Bar chart comparing cellular, telephone, and unknown contacts.
4. **Contact frequency:** Area/line chart of subscription outcomes across current campaign contact counts.
5. **Age-group performance:** Bar chart of subscription rates by age group.
6. **Call duration:** Box plot comparing contact duration by subscription status.
7. **Previous campaign contact:** Bar chart comparing previously contacted and non-contacted customers.
8. **Age group × contact method:** Heatmap exploring segment-level subscription rates.
9. **Age vs. account balance:** Scatter plot colored by subscription status.
10. **Job category:** Subscription counts and calculated subscription rates by job.
**Note:** - The chart labeled as the previous campaign outcome analysis actually plots an age-group-by-contact-method heatmap.
- Also, the subscribed indicator is assigned on a 0–100 scale in some cells, so multiplying its average by 100 again can overstate percentages.
- Normalize it to 0/1 before calculating mean() * 100 or average the 0/100 version without another multiplication.

## 🎯Key Findings
- **Overall subscription rate:** Approximately 11.70% (5,289 of 45,211 records); most customers did not subscribe.
- **Contact channel:** The displayed contact-method chart shows cellular calls with a higher subscription rate than telephone or unknown contact methods.
- **Age group:** The displayed age-group chart shows the 65+ group with the highest subscription rate by percentage; group sizes should also be considered.
- **Job category:** The printed job-rate output ranks students (28.68%) and retired customers (22.79%) among the highest-rate groups; these rates should be interpreted alongside customer counts.
- **Data distribution:** Balance, duration, and prior-contact features are strongly right-skewed, indicating some extreme values worth examining.
- **Interpretation:** These are descriptive associations. They do not prove that a contact method, age group, or more/longer calls cause subscription.

## 🎯Project Conclusion:
- The analysis identifies variation in term-deposit subscription outcomes across customer demographics, contact channels, and campaign history. 
- The baseline subscription rate is relatively low, which suggests value in further customer segmentation and more selective outreach. 
- A practical next step is to validate rates, examine group sample sizes, and compare campaign strategies with appropriate controls before drawing operational or causal conclusions.

## 🎯Dependencies
- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- openpyxl (for reading Excel files with Pandas)
- Jupyter Notebook or Google Colab

## 🎯Installing
1. Download or clone the GitHub repository containing the notebook and input Excel dataset.
2. Install dependencies using the following command:
```
pip install pandas numpy matplotlib seaborn openpyxl notebook
```
4. Confirm that the notebook's Excel data URL or file path points to an accessible dataset.

## 🎯Executing program
1. Open the project notebook in Google Colab or Jupyter Notebook.
2. Run the library import and dataset loading cells first.
3. Run the cleaning and preprocessing cells in order.
4. Before calculating monthly or other grouped percentage rates, create a consistent binary indicator:
df["subscribed"] = df["subscription"].eq("yes").astype(int)
month_rate = df.groupby("month")["subscribed"].mean() * 100
5. Run the EDA and visualization cells to display the charts.
6. Review and interpret chart outputs before using the findings in a presentation.

## 🎯Help
- KeyError: 'subscribed': Create df["subscribed"] before using it in a groupby calculation.
- Incorrect rates above 100%: Use a consistent 0/1 subscription indicator when multiplying group means by 100.
- Excel read error: Check the file or URL, permissions, and whether openpyxl is installed.
- Unexpected chart output: Run notebook cells in sequence and verify column names after renaming y.

## 🎯Version History
- 1.0 — October 2026: Initial README for Bank Marketing Campaign Analysis, documenting the notebook workflow, visualizations, findings, and execution instructions.

## 🎯Acknowledgments
- UCI Machine Learning Repository for the Bank Marketing dataset: https://archive.ics.uci.edu/dataset/222/bank+marketing
- Paulo Cortez and Sérgio Moro, identified in the notebook as dataset contributors.
- Open-source Python libraries Pandas, NumPy, Matplotlib, and Seaborn.

## 👩‍💻 Author
Sugantha B
-	Aspiring Data Analyst | Python | SQL | Power BI | Excel
