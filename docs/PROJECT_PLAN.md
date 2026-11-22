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
| T14 | Sprint retrospective | Team review after project completion: what went well, what to improve, actions | Simprabh Dhillon |  Done |

**Order:** T1–T4 (setup) first, then T5–T7 (cleaning). T8–T9 need the cleaned data, T10–T11 need T9, T13 needs T8–T11, and T14 happens after T13.

## Related documents

- Sprint goal: [`SPRINT_GOAL.md`](SPRINT_GOAL.md)
- Kanban board: [`KANBAN_BOARD.md`](KANBAN_BOARD.md)
- Project risks and mitigation: [`PROJECT_RISKS.md`](PROJECT_RISKS.md)
- Retrospective: [`RETROSPECTIVE.md`](RETROSPECTIVE.md)
