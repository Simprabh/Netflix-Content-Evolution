# Project Plan – The Evolution of Netflix Content (Challenge 3)

**Business question:** How has Netflix's content library changed over time?
**Project manager:** Simprabh Dhillon · **Method:** one sprint on a GitHub Projects Kanban board

## Team

| Member | Responsibilities |
| --- | --- |
| Sandesh Malla | Dataset management, data inspection, data cleaning and integration |
| Apoorva Kulkarni | Exploratory data analysis (EDA), statistical summaries and trend analysis |
| Aparna Devi Nangunoori | Visualizations (at least 3), interpretation and business insights |
| Simprabh Dhillon | GitHub repository setup, project plan, Kanban board, sprint goal, risk management, retrospective, final report and README |

## Task breakdown

| ID | Task | Description | Owner | Status |
| --- | --- | --- | --- | --- |
| T1 | Project plan and sprint goal | Task breakdown with owners, sprint goal and definition of done | Simprabh Dhillon | Done |
| T2 | GitHub repository setup | Repository, folder structure, `requirements.txt`, `.gitignore`, team Git workflow | Simprabh Dhillon | Done |
| T3 | Kanban board | GitHub Projects board with one card per task, owner and status | Simprabh Dhillon | Done |
| T4 | Risk management | Two project risks with mitigation actions; track them during the sprint | Simprabh Dhillon | Done |
| T5 | Data inspection | Load the dataset; check shape, data types, missing values, duplicates and categorical values | Sandesh Malla | Done |
| T6 | Data cleaning | Fix 3 durations stored in `rating`; fill missing descriptive values with `Unknown`; convert `date_added`; create `year_added`; standardize text | Sandesh Malla | Done |
| T7 | Clean data export and report | Validate the result and export `data/netflix_titles_cleaned.csv`; write the data cleaning report | Sandesh Malla | Done |
| T8 | Statistical summaries | Descriptive statistics and counts by type, rating, country and genre | Apoorva Kulkarni | Done |
| T9 | Trend analysis | How additions, Movie/TV mix, genres, countries and ratings change by year added | Apoorva Kulkarni | Done |
| T10 | Visualizations | At least three labelled charts that answer the business question | Aparna Devi Nangunoori | Done |
| T11 | Business insights | Interpret the charts; write at least three business insights | Aparna Devi Nangunoori | Done |
| T12 | README | Project overview, structure, how to run, cleaning summary; key findings after T8–T11 | Simprabh Dhillon | Done |
| T13 | Final report and submission | Conclusions from T8–T11; HTML/PDF export; completion screenshot; final checklist | Simprabh Dhillon | Done |
| T14 | Sprint retrospective | Team review after project completion: what went well, what to improve, actions | Simprabh Dhillon | Done |

**Order:** T1–T4 (setup) first, then T5–T7 (cleaning). T8–T9 need the cleaned data, T10–T11 need T9, T13 needs T8–T11, and T14 happens after T13.

## Project risks and mitigation

| Risk | Impact | Mitigation action | Owner |
| --- | --- | --- | --- |
| **1. Poor data quality may distort the conclusions.** 2,634 titles have no director, 831 no country and 825 no cast; 10 have no `date_added`; 3 had a duration in `rating`; the data stops on 25 Sep 2021, so 2021 is a partial year. | High: wrong trends, e.g. reading 2021 as a decline | Clean and validate first (T5–T7, done): `Unknown` instead of dropped rows, validation checks in notebook 01. Exclude the 10 undated titles from time-based analysis, and label 2021 as partial (or compare the same months) in every chart. | Sandesh Malla (cleaning); Apoorva Kulkarni and Aparna Devi Nangunoori (partial-year handling) |
| **2. Parallel work on notebooks causes Git conflicts or a broken final notebook.** `.ipynb` files are JSON and conflict easily. | Medium: lost work, missed deadline | One notebook per owner (01/02/03); pull before every push; small, clearly named commits; final "Restart & Run All" of every notebook before submission (T13). | Simprabh Dhillon |

## Retrospective

*To be completed with the whole team after project completion (T14).* Format: 30 minutes, everyone answers each question, then agree on actions.

**What went well?**
- Data cleaning was finished first, as planned for Risk 1, and checked with validation asserts (8,807 records, 0 duplicates, 10 missing dates kept).
- *(team input)*

**What could be improved?**
- *(team input)*

**What did we learn?**
- *(team input)*

**Action items for the next project**

| Action | Owner |
| --- | --- |
| *(team input)* | |

**Risk review:** did Risk 1 or Risk 2 occur, and did the mitigation work? *(team input)*
