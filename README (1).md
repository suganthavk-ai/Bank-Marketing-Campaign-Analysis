# Bank Marketing Campaign Analysis Using Python

**Author:** B Sugantha  
**Domain:** Banking | Marketing Analytics | Exploratory Data Analysis

## Project Overview

This Python exploratory data analysis (EDA) project examines a Portuguese bank’s telemarketing campaigns to understand which customer attributes and campaign characteristics are associated with subscriptions to term deposits. It uses customer segmentation, conversion-rate calculations, statistical summaries and visualizations to support data-informed marketing decisions.

## Project Objectives

- Measure overall campaign subscription performance.
- Compare subscription rates by month and contact method.
- Examine contact frequency and call duration.
- Identify responsive age groups and job categories.
- Explore prior contact history, previous campaign outcomes and customer account balances.

## Dataset

Source: UCI Machine Learning Repository — Bank Marketing dataset (https://archive.ics.uci.edu/dataset/222/bank+marketing). The uploaded project analyzes 45,211 records across 17 original fields (7 numerical and 10 categorical). The target field y indicates whether a customer subscribed to a term deposit; the analysis renames it subscription.

## Dataset Features

age, job, marital, education, default, balance, housing, loan, contact, day, month, duration, campaign, pdays, previous, poutcome, y (renamed to subscription). Derived variables in the analysis include age_group, previous_contact and a numerical subscribed indicator.

## Tools and Technologies

- Python
- Pandas and NumPy — data manipulation and statistics
- Matplotlib and Seaborn — charts and visualizations
- Google Colab / Jupyter Notebook — execution and documentation
- Microsoft Excel — source data imported with pandas.read_excel()

## Project Workflow

- Load the Excel data and inspect head, tail, data types, shape and summary statistics.
- Check nulls, category values such as unknown, and fully duplicated records.
- Examine skewness and kurtosis and flag possible numerical outliers with the IQR rule.
- Rename y to subscription and create derived customer segments and conversion measures.
- Perform exploratory analysis with charts across demographic, financial and campaign factors.
- Interpret observed trends and suggest opportunities for better campaign targeting.

## Visualizations Included

- Donut chart — overall subscription outcome
- Monthly subscription analysis — month-by-month comparison
- Bar chart — contact method subscription rate
- Area/line chart — campaign contact frequency
- Bar chart — subscription rate by age group
- Box plot — call duration by subscription outcome
- Previous-campaign contact and outcome comparisons
- Heatmap — age group × contact method
- Scatter plot — age versus balance by subscription
- Count plot and conversion-rate summary — job category

## Key Findings

- Overall, 5,289 of 45,211 records show a subscription (11.70%); 39,922 do not (88.30%).
- The source notebook reports zero standard null values and zero fully duplicated rows. It also identifies unknown categories in job (288), education (1,857), contact (13,020) and poutcome (36,959), retained for analysis.
- Cellular calls show a higher observed subscription rate than telephone and unknown contact methods.
- The 65+ age group has the highest subscription rate among the notebook’s specified age bands; segment sizes should also be considered.
- Students have the highest reported job-category subscription rate (28.68%), followed by retired customers (22.79%).
- The numeric data include heavily skewed features and potential outliers, particularly previous, balance, duration and campaign. These need careful interpretation.
- These relationships are descriptive associations; they do not establish causal effects.

## Recommendations

- Prioritize testing targeted communication for segments with higher observed response rates while accounting for audience size.
- Review the balance between campaign contact frequency and conversions rather than assuming more calls always help.
- Use previous campaign history and contact-method information to inform customer segmentation.
- Check data quality, measurement definitions and potential selection bias before operational deployment.

## How to Run

- Clone or download the repository from https://github.com/suganthavk-ai/Bank-Marketing-Campaign-Analysis
- Open the project notebook in Google Colab or Jupyter.
- Install dependencies if needed: pip install pandas numpy matplotlib seaborn openpyxl
- Ensure the Excel input file is accessible at the URL or path used in the notebook; modify pd.read_excel(...) if required.
- Run the notebook cells in order. Ensure that subscribed is consistently coded as 0/1 and multiply by 100 only once when computing percentages.

## Conclusion

The project demonstrates a complete descriptive analytics workflow, from dataset inspection and preprocessing checks through segmentation, conversion-rate analysis and visualization. The findings indicate differences in term-deposit subscription behavior across customer groups and contact strategies, offering useful hypotheses for follow-up campaigns. Future improvements could include corrected percentage-scale validation, confidence intervals, statistical tests and predictive modeling.

## Author and Attribution

Project prepared by B Sugantha. Dataset: UCI Bank Marketing (Paulo Cortez and Sérgio Moro). Repository: https://github.com/suganthavk-ai/Bank-Marketing-Campaign-Analysis

> **Note:** This repository documents exploratory associations, not causal effects. Recheck any plots that apply a second `* 100` to a percentage-coded `subscribed` column.
