### Content. # LinkedIn Analytics Notebook

Welcome to the LinkedIn Analytics Notebook! This project walks you through a comprehensive analysis of LinkedIn content (posts + metrics), visitors, and followers across multiple time periods. Below is a high-level overview of the work, organized by major deliverable.

<hr style="border: 2px  grey;" />
**All data in this repository is anonymised!**
<hr style="border: 2px  grey;" />

## 1. Data Preparation & Anonymization
> **Note:** The raw Excel files are not included in this repository for confidentiality reasons.  
> Please place them in the `data/` directory before running the notebook.
> 
**Role:** Data Analyst / ML Engineer  
**Expected input files (example names):**
- `data/content_1year_anonym.xlsx`
- `data/content_1month_anonym.xlsx`
- `data/visitors_1year.xlsx`
- `data/followers_1year.xlsx`
- **Process:**  
  1. Load raw Excel files into pandas  
  2. Generate unique `post_id` and `employee_id`  
  3. Drop sensitive columns (`Post title`, `Post link`, `Author`)  
  4. Verify data integrity and save anonymized tables  

---

## 2. Defining Cohorts & Time Periods

There were compared three cohorts for both **Content** and **Visitors/Followers**:

| Cohort                | Content Period                        | Visitors/Followers Period              |
|-----------------------|---------------------------------------|----------------------------------------|
| **2024_baseline**     | Feb 12, 2024 – Feb 10, 2025            | Apr 14, 2024 – Apr 13, 2025             |
| **2024_same_period**  | Mar 20, 2024 – Apr 20, 2024            | Mar 20, 2024 – Apr 20, 2024             |
| **2025_campaign**     | Mar 20, 2025 – Apr 20, 2025            | Mar 20, 2025 – Apr 20, 2025             |

For each cohort, we filter and slice the data accordingly.

---

## 3. Descriptive Analysis: Content Metrics

- **Time series** of impressions, clicks, engagement rate, CTR
- **Comparisons** of means/medians across cohorts  
- **Outlier detection** (IQR, Z-score)  
- **Visualizations** of trends and distributions  

---

## 4. Statistical Testing: Content Performance

- **Normality checks** (Q–Q plot for Engagement Rate — confirms heavy skew and zero-mass)  
- **Group tests**  
  - **Kruskal–Wallis H-test** for cohort comparisons (nonparametric alternative to ANOVA)  
  - **Paired Mann–Whitney U-tests** between each cohort pair, with **Bonferroni correction** for multiple comparisons  
- **Effect size** (η² for the one-way ANOVA on weekday CTR)  
- **Bootstrap CIs** for per-weekday median CTR (95% intervals via 10 000 resamples)

- **Key takeaway:** with limited posts, differences are suggestive but not formally significant  

---

## 5. Visitors & Followers Analysis

- **Annual trends** in new visitors & followers  
- **Cohort comparisons** of growth rates  
- **Breakdowns** by country, industry, company size, job function, seniority  
- **“Top N” charts** showing relative shares  

---

## 6. Correlation: Content ↔ Engagement

- **Merge** post dates with overall traffic/follower peaks  
- **Cross-correlation** & lag analysis  
- **Moving averages** to smooth noise  
- **Interpretation:** indirect signals of content impact  

---

## 7. Visualization & Reporting

- **Dashboard-ready charts** and summary tables  
- **Slide deck** (PowerPoint) with commentary  
- **Narrative highlights** aligned to corporate style guidelines  

---

## 8. Conclusions & Recommendations

1. **Data volume is too small** for robust predictive models (< 15 posts vs. 50–100 needed)  
2. **Expand feature set**: format, time of day, text length, audience segment  
3. **Continue A/B testing** on format/headline within consistent posting days  
4. **Maintain 3 posts/week** to reach target volume in 4–6 months  
5. **Monthly descriptive reviews** to track medians/intervals  
6. **Plan predictive modeling** once sufficient data is collected  

---

## Required Skills & Tools

- **Data wrangling:** Python (pandas, numpy, seaborn, matplotlib, plotly, re, scipy, translator);
- **Statistics:** scipy, statsmodels, bootstrap methods  
- **Time series:** cross-correlation, moving averages  
- **Visualization:** Matplotlib, Seaborn, PowerPoint  
- **Anonymization:** best practices for data privacy  
- **Consulting:** crafting clear insights & strategic roadmaps  

---

Feel free to explore each section of the notebook via the Table of Contents. Happy analyzing! 
