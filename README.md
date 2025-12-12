# Project Background

This is a data analytics project analysing outpatient waiting list trends in Ireland using official National Treatment Purchase Fund (NTPF) open data.
The NTPF is an Irish state agency that publishes regular statistics on hospital waiting lists across public hospitals. These datasets are used by healthcare planners, hospital managers, and policymakers to monitor access to care and identify pressure points in the health system.

From the perspective of a data analyst working in a healthcare analytics or operations team, this project focuses on understanding **outpatient waiting list pressures across medical specialties** between 2022 and 2025. Key business metrics include:

- Total number of patients waiting for outpatient treatment  
- Distribution of waiting times (0–6, 6–12, 12–18, 18+ months)  
- Long-wait exposure (patients waiting over 12 months)  
- Differences in demand across specialties and over time  

Insights and recommendations are provided across the following key areas:

- Waiting list trends over time  
- Specialties contributing most to outpatient demand  
- Long-wait risk across specialties  
- Changes in long-wait patterns over multiple years  



# Data Structure & Initial Checks

For this project, the specialty-level table was used to provide richer analytical insights.
Each row represents a **monthly snapshot of waiting list counts per specialty**.

Additional derived fields were created during data preparation:

- **Long_Waiters** = (12–18 months) + (18+ months)  
- **Long_Wait_Ratio** = Long_Waiters / Total  

**Row count:** ~1,000 records  
**Time period:** January 2022 – October 2025  
**Granularity:** Monthly summaries by specialty  


# Executive Summary

### Overview of Findings

Between 2022 and 2025, Ireland’s outpatient waiting list showed a **gradual overall decline**, though recent months indicate renewed pressure. While total waiting numbers decreased from approximately **6.8M in 2022 to 6.4M in 2024**, the waiting list reached **5.6M by October 2025**, which is higher than the same point in the previous two years.

Demand is **unevenly distributed across specialties**, with a small number consistently accounting for a large share of patients waiting. Long-wait risk also varies substantially by specialty, highlighting areas where access challenges may be worsening over time.

<img src=https://github.com/naomy19/ntpf-outpatient-waitlist-analysis/blob/main/images/Dashboard.png>


# Insights Deep Dive
### 1. Overall Waiting List Trends

- Total outpatient waiting numbers decreased gradually from 2022 to 2024.
- By October 2025, the waiting list stood at approximately **5.6M**, exceeding the same period in both 2023 and 2024.
- This suggests that while long-term progress has been made, recent demand pressures may be emerging.

<img src=https://github.com/naomy19/ntpf-outpatient-waitlist-analysis/blob/main/images/Total%20wait%20by%20year.png>


### 2. Specialties with the Highest Waiting Lists

- **Orthopaedics**, **Dermatology**, and **Otolaryngology** consistently recorded the highest outpatient waiting volumes.
- These specialties accounted for a disproportionate share of total outpatient demand across all years analysed.
- Trends indicate persistent structural pressure rather than short-term fluctuations.
  
<img src=https://github.com/naomy19/ntpf-outpatient-waitlist-analysis/blob/main/images/Total%20wait%20by%20specialty.png>


### 3. Long-Wait Risk by Specialty

- Long-wait ratios varied significantly between specialties.
- **Clinical Genetics** showed a steady increase in long-wait ratio over time, reaching the highest level among specialties in 2024.
- Other specialties exhibited more stable or fluctuating long-wait patterns, suggesting differing capacity constraints.

<img src=https://github.com/naomy19/ntpf-outpatient-waitlist-analysis/blob/main/images/Long%20wait%20ratio%20by%20specialty.png>


# Recommendations:

Based on the findings above, the following recommendations are proposed for healthcare planning and operational teams:

1. **Prioritise capacity planning in high-volume specialties**  
   Orthopaedics, Dermatology, and Otolaryngology consistently dominate outpatient waiting volumes and should remain priority areas for resourcing and process optimisation.

2. **Monitor specialties with rising long-wait ratios**  
   The steady increase in long-wait exposure in Clinical Genetics suggests growing access constraints that may require targeted intervention.

3. **Track recent upward trends in 2025 closely**  
   Although overall waiting numbers declined over previous years, the higher levels observed in 2025 compared to recent years may signal renewed system pressure.
  


# Assumptions and Caveats:

- The analysis is based on **summary-level monthly data**, not individual patient records.
- Waiting list counts reflect reported snapshots and may be affected by reporting or classification changes over time.
- No adjustment was made for population growth or demographic change.
- The analysis focuses on national-level trends and does not account for hospital-specific operational constraints.



## Data Source

National Treatment Purchase Fund (NTPF) – Outpatient Waiting List Open Data  
https://www.ntpf.ie/waiting-list-data/open-data/
