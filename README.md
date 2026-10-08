# Heart Failure Survival Analysis | Power BI Dashboard

An interactive Power BI dashboard that looks at who survives heart failure and who doesn't, broken down by age, gender, key blood markers and common risk factors.



## Why I built this

I wanted a project where the numbers connect to a real decision. A hospital can't give every patient the same level of attention, so it needs to know which groups are most at risk. I picked a public heart failure dataset and set myself one question: **which patients are most likely to not survive, and what do their numbers look like?**



## About the data

|||
|-|-|
|**Source**|UCI Heart Failure Clinical Records|
|**Size**|299 patients, 13 clinical columns|
|**Fields used**|Age, sex, serum creatinine, ejection fraction, smoking, high blood pressure, anaemia, diabetes, death event|
|**File**|`data/Heart\\\_Disease\\\_Dataset.xlsx`|

Note: this dataset is about patients with **heart failure**, so that is the term I use throughout.

\---

## What I did

1. **Cleaned the data in Power Query.** Checked data types, renamed columns, and turned the 0/1 flags into readable labels (Male/Female, Survived/Died).
2. **Grouped patients into age bands** (40-50, 51-60, 61-70, 71+) so I could compare groups instead of individual ages.
3. **Wrote DAX measures** for total survivors, total deaths, survival rate and average age of survivors.
4. **Built the dashboard** with KPI cards, a Male/Female toggle and charts for survival, serum creatinine, ejection fraction and risk factors.



## What I found

**Overall:** 203 of 299 patients survived (**67.9%**) and 96 died.

|Age group|Patients|Survived|Survival rate|
|-|-|-|-|
|40-50|74|55|\~74%|
|51-60|88|63|\~72%|
|61-70|85|64|\~75%|
|71+|52|21|\~40%|

* **Age is the clearest divider.** Survival holds at roughly 72-75% up to age 70, then falls to about 40% for patients 71 and over.
* **Men and women had almost the same survival rate** (68.0% vs 67.6%). Men make up about 65% of the patients (194 vs 105), so the cohort is uneven even though the outcomes are not.
* **The 71+ group had the highest average serum creatinine** among the age groups in the female view, which fits what is known about kidney function and heart failure outcomes.



## What I would suggest

If I were advising a hospital team, I would flag patients over 70 for closer follow-up. I would also look at serum creatinine and ejection fraction together when deciding who needs more monitoring, not each on its own.

## Dashboard contents

* KPI cards: total survivors, total deaths, survival rate, average age of survivors
* Survival count with average serum creatinine by age group
* Survival count with average ejection fraction by age group
* Survival rate by age group
* Smoking, high blood pressure, anaemia and diabetes by age group
* Male / Female toggle that filters every visual

\---

## Limitations

* Only 299 records from one source, so I would not generalise this to other hospitals.
* There is no time dimension, so I can't show how patients changed over time.
* These are patterns in the data, not proof of cause.

\---

## What I learned

My first version of the "survival rate by age group" chart was actually plotting patient counts, not rates. I rewrote the measure as survivors divided by total patients in each group, and the real drop after age 70 became much clearer. It taught me to check what a chart is calculating before trusting how it looks.

\---

## Tools

Power BI Desktop, Power Query, DAX, Microsoft Excel

## Credits

* **Dataset:** Chicco, D. \& Jurman, G. (2020). *Machine learning can predict survival of patients with heart failure from serum creatinine and ejection fraction alone.* BMC Medical Informatics and Decision Making, 20(1), 1-16. Source: https://archive.ics.uci.edu/dataset/519/heart+failure+clinical+records. Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
* **Heart image:** [Freepik](https://www.freepik.com/free-psd/3d-rendering-realistic-heart_344840361.htm)
* **Icons:** Sudowoodo on [Flaticon](https://www.flaticon.com/free-icon/person_13482183) and [Flaticon](https://www.flaticon.com/free-icon/avatar_13482193)
* **Inspiration:** the layout idea comes from an existing public Power BI heart disease project by Paramesh Mandapaka. I rebuilt the analysis from the raw data and wrote my own measures and findings.

\---

## About me

**Samson Savio** | Data Analyst | Bengaluru, India
BCA in Data Analytics, St. Joseph's University
[LinkedIn](https://linkedin.com/in/samson-savio-263202165)

If this project was useful to you, a star on the repo is appreciated.

