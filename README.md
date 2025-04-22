# Optimizing Marketing Spend Efficiency for College X

all code contained in SpendEfficiency.ipynb

### Domain: Higher Education

### Tools Utilized
* Python
  * analysis: pandas
  * visualization: matplotlib, plotly
 
### Objective
The client is a community college (College X). This project aims to answer the following questions for 3 months of marketing spend from June 15 to Sept 15 targeting fall 2024 enrollment:
* How does attribution vary between the marketing channel tracked in via UTM code and the marketing channel that applicants self-report interacting with?
* How does performance, based on CPL, CPE, uplift, ROAS vary between the current marketing channels?
* How do these metrics vary based on attribution methodology?

## Data Sources
### marketing_spend.csv
This dataset contains spend in USD per channel, per day, from 15 June 2024 to 15 Sept 2024.

| Field | Domain | Description | non-null count | 
| :---: | :----- | :---------: | -------------: |
| date | [2024-06-15, 2024-09-15] | | 558 |  
| channel | ['facebook', 'google', 'linkedin', 'snapchat', 'tiktok', 'other'] | marketing channel | 558 |
| spend_usd | [0, $105,407.10] | single-day spend in USD | 558 | 

### applicants_abbrev.csv
This is a subset of the applicants dataset from college-conversion-analysis. It contains one record per applicant with dates related to their journey from application to enrollment, if applicable.

| Category | Field | Domain | Description | non-null count | 
| -------- | :---: | :----- | ----------- | -------------: |
| General Demo | person_id | $\mathbb{Z}$ | primary key; [1, 12983] in this sample | 12,920 |
| Admissions Process | lead_created_date | [10/22/2021, 09/15/2024] | | 12,916 |
| Admissions Process | reported_channel | ['email', 'employer', 'facebook', 'google', 'linkedin', 'natural search', 'other', 'referred', 'snapchat', 'tiktok', 'unknown', 'wordOfMouth'] | response to 'How did you hear about College X? | 12,920 |
| Admissions Process | utm_marketing_channel | ['employer', 'facebook', 'google', 'linkedin', 'natural search', 'referral', 'snapchat', 'tiktok', 'unknown'] | marketing channel according to UTM tracking code from first applicant interaction | 12,920 |
| Admissions Process | app_submit_date | [06/15/2024, 10/17/2024] | | 12,906 |
| Admissions Process | admit_date | [06/18/2024, 02/25/2025] | date admitted | 1,882 |
| Admissions Process | enroll_date | [02/16/2024, 02/11/2025] | date student commits to College X | 911 |
| Term 1 | reg_status_t1 | ['Registered', 'Did Not Start', 'Provisional Drop', 'Withdrawn', nan] | student's registration status at end of Term 1; Registered if they completed term, Did Not Start if they never attended a class, Provisional Drop if they withdrew in first 6 weeks of term, Withdrawn if they withdrew after first 6 weeks, nan if they never registered | 911 |
| Term 1 | last_attend_date | [10/07/2024, 12/12/2024] | last date student attended class | 755 |
| Term 1 | term_start | 10/07/2024 | date Term 1 begins | 12,920 |
| Term 1 | term_end | 12/12/2024 | date Term 1 ends | 12,920 |




