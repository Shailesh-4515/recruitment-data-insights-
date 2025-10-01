# Project Background

Our client, a recruitment and selection firm, recently faced a surge in job inquiries within the data domain from multiple external sources. While the data contained valuable details about job openings, it was highly unstructured and fragmented, making it extremely difficult to extract insights. Some providers delivered normalised datasets, while others shared centralised tables, resulting in inconsistent formats and disconnected information.

## The main challenges with the database included:

- Data inconsistencies and missing information — critical details were embedded in unstructured text, while many fields had missing or unreliable values.

- Fragmented and poorly connected tables — datasets were distorted, isolated, and lacked clear relationships.

- Large data volume — with over 700,000+ rows, ensuring scalability and maintaining reporting performance in Power BI was a major challenge.

- Report optimisation — given the scale and complexity, the Power BI dashboards had to be designed for both accuracy and speed.

## To address these challenges, the client requested:

- Creation of a unified database schema from disparate sources.

- Consolidation of data into a single analysis-ready dataset in Power BI, following a structured schema including job details (ID, title, field, location, type, level, skills, employment type, etc.).

- Development of dashboards to provide insights into:

  - Hiring trends over time

  - Distribution of job types (onsite, hybrid, remote)

  - Country- and job-field level analysis

  - Skills in demand

The objective of this project was not only to prepare the data for analysis but also to deliver strategic insights for workforce planning, enabling the client to optimise recruitment campaigns, adapt to evolving work models, and invest in the right talent pipelines.


# Data Structure & Initial Checks

The company’s main database structure consists of 8 tables sourced from different providers, with a total row count of 700,000+ records. These were normalized and consolidated into the following schema:

- Jobs — job_id, job_title, job_field, job_posting_date, job_level

- Companies — company_id, company_name, job_id link

- Job Types — job_id, job_type (onsite, hybrid, remote), job_employment_type

- Locations — job_id, job_location (city, country)

- Skills — job_id, job_skills (aggregated from multiple rows via Python merge)

- Summaries — job_id, summary text

- Job Field Mapping — job_id, standardized job_field values

- Miscellaneous (raw sources) — staging data, later merged

## Initial checks included:

 - Removing duplicates on job_id

 - Standardizing date formats → YYYY-MM-DD

 - Handling missing job_location values by imputing based on company HQ

 - Merging multiple skill rows per job into one aggregated skill list

 
  # Executive Summary
  
## Overview of Findings

 - Hiring is cyclical, with monthly average openings fluctuating between 1.7K and 2.9K in 2023. Peaks were seen in January (2.9K) and August (2.4K).

 - Remote and hybrid roles are increasingly offered, accounting for ~84% remote in 2023 compared to only 6% in 2022.

 - Data Science, AI/ML, and Cloud roles dominate job openings in recent years. SQL and Python remain the most demanded skills.

## If a stakeholder could only take away three insights:

 1) Plan recruitment campaigns around Q1 (January) and Q3 (August) as hiring peaks.

 2) Align hiring strategy with remote/hybrid growth (remote jobs rose from 6% in 2022 → 83% in 2023 → 100% in 2024).

 3) Invest in SQL, Python, and Cloud skills pipelines, as they consistently rank top across years.

<img width="932" height="732" alt="image" src="https://github.com/user-attachments/assets/ef0c80bf-3eb0-42c0-8441-09a6c65dba25" />


# Insights Deep Dive
## Category 1: Hiring Trends Over Time

 * 2022 → 1,341 postings

 * 2023 → 145,262 postings (massive growth)

 * 2024 (partial data) → 3,953 postings

 * Seasonal spikes: January (2.9K in 2023, 1.3K in Dec 2022) and August (2.4K in 2023) are peak periods.

   <img width="1173" height="183" alt="image" src="https://github.com/user-attachments/assets/2505ff20-6812-4329-9e47-2d86bc2ff14e" />


## Category 2: Job Types & Distribution

 * 2022: 94% Onsite, 6% Remote, negligible Hybrid.

 * 2023: 83% Remote, 17% Onsite, 2% Hybrid.

 * 2024: 100% Remote (based on data so far).

 * Companies are rapidly shifting away from onsite toward remote-first models.

## Category 3: Country-Level & Job Field Analysis

 * Roles vary across countries:

   * Abu Dhabi (UAE): Senior Data Engineer

   * Saudi Arabia cities: Data Analyst, Data Engineer, Cloud Engineer, Business Analyst

     <img width="630" height="455" alt="image" src="https://github.com/user-attachments/assets/efaf1210-fcd2-4dc1-822a-46219e117bf8" />


 * Top 3 domains by year:

 * 2022: Data Engineer, Data Analyst, Data Scientist

 * 2023: Data Scientist, Data Analyst, Data Engineer

 * 2024: Business Analyst, Data Analyst, Data Engineer

## Category 4: Skills in Demand

 * From job field trends, the consistently in-demand skills are:

    * SQL, Python, Data Analysis, Cloud (AWS/Azure), Business Analytics

 * Soft skills are less mentioned but communication stands out when listed.


# Recommendations

  * Marketing / Workforce Strategy → Run campaigns in January and August when hiring peaks.

  * HR & Client Advisory → Encourage clients to offer remote/hybrid roles to remain competitive.

  * Training & Upskilling → Focus on SQL, Python, and Cloud platforms as they dominate demand.

  * Business Development → Prioritize industries needing Data Science and Cloud talent.

  * Operations → Standardize job posting schema to avoid fragmented skill data in future.
