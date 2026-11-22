# Sprint Retrospective – The Evolution of Netflix Content (Challenge 3)

**Sprint:** Sprint 1 · **Date:** 22 November 2026 · **Facilitator:** Simprabh Dhillon
**Participants:** Sandesh Malla, Apoorva Kulkarni, Aparna Devi Nangunoori, Simprabh Dhillon
**Repository:** https://github.com/Simprabh/Netflix-Content-Evolution

## 1. Sprint goal review

> By the end of Sprint 1, deliver a complete, reproducible analysis in Jupyter notebooks that shows how Netflix's content library changed over time, supported by at least three labelled visualizations and at least three business insights, together with a final report and a documented GitHub repository managed on a Kanban board.

**Delivered in this sprint:**

| Deliverable | Owner | Result |
| --- | --- | --- |
| Clean, validated dataset | Sandesh Malla | `notebooks/datainspection_cleaning.ipynb`: 8,807 records, 0 duplicates, 3 misplaced durations fixed, missing values set to `Unknown`, 10 undated titles kept; output in `data/cleaned/` |
| EDA, statistical summaries and trends | Apoorva Kulkarni | `notebooks/Netflix_EDA_Analysis.ipynb`: five questions answered, statistical tests with effect sizes, summary of findings |
| Labelled visualizations | Aparna Devi Nangunoori / Apoorva Kulkarni | 11 labelled charts, saved automatically to `visualizations/` |
| Repository, plan, Kanban board, risks | Simprabh Dhillon | GitHub repo with `data/`, `notebooks/`, `visualizations/`, `docs/`; GitHub Projects board; project plan, sprint goal and risk register in `docs/` |

## 2. What went well

- **Clear ownership.** Each member owned one stage and one notebook, so work ran in parallel without anyone editing the same file.
- **Data quality came first.** Cleaning and validation (assert checks) were finished before EDA started. No rows were deleted; missing values became `Unknown` and misplaced values were moved to the right column.
- **The partial-year trap was avoided.** The EDA marks 2021 as partial in every year-based chart and compares the same months. This shows 2021 at +10% vs 2020 instead of a false decline.
- **Sound statistics.** The EDA reports effect sizes (e.g. Cramér's V) next to significance tests and lists its caveats.
- **Consistent charts.** One colour palette and one styling helper give all charts the same look.
- **Visible progress.** Every task had an owner and a card on the Kanban board, and the planning documents live in the repo.

## 3. What could be improved

- **File paths.** Notebooks were written with the CSV in the same folder as the notebook, so they broke when moved into the repo's `data/` and `notebooks/` folders. The EDA notebook now uses project-relative paths; the cleaning notebook needs the same fix.
- **Saving figures.** Charts were at first only shown inline. Saving them to `visualizations/` was added at the end.
- **Naming.** Notebook names follow no single convention (`datainspection_cleaning.ipynb`, `Netflix_EDA_Analysis.ipynb`), and the cleaned file moved from `data/` to `data/cleaned/`.
- **Planning churn.** The task order and the planning documents were restructured several times. Agreeing the structure on day one would have saved time.
- **Hidden warnings.** The EDA notebook switches warnings off globally (`warnings.filterwarnings("ignore")`). This can hide real problems, and the assignment asks for no unexplained warnings.
- **Notebook hygiene.** The cleaning notebook's section numbers are out of order (9, 10, 11, 13, 14, 12) and it ends with an empty cell.

## 4. What we learned

- Agree the repository structure, file names and relative paths before anyone writes code.
- "Restart & Run All" inside the repository is the real test of reproducibility, not running on your own machine.
- Check a dataset's time coverage before reading trends; a partial final year looks like a decline.
- A clear hand-off file between stages (the cleaned CSV) lets each person work independently.

## 5. Risk review

| Risk | Did it occur? | Did the mitigation work? |
| --- | --- | --- |
| **1. Poor data quality distorts conclusions** | Yes: 3 durations in `rating`; missing director (2,634), country (831) and cast (825); 10 undated titles; 2021 ends on 25 Sep. | Yes. Cleaning and validation came first; undated titles are excluded from year-based analysis; 2021 is marked partial and compared like-for-like. |
| **2. Parallel work causes Git conflicts or a broken notebook** | Partly. Separate notebooks meant nobody edited the same file, but integration problems appeared instead: broken file paths and figures not saved. | Mostly. Both were fixed during integration; a "Run All" check from the repo after each hand-off would have caught them sooner. |

## 6. Action items

**Before submission**

| Action | Owner |
| --- | --- |
| Change the cleaning notebook's input path to `../data/netflix_titles.csv` (or project-relative) and fix the section numbering | Sandesh Malla |
| Remove the global warning filter in the EDA notebook; fix or explain any warning that appears | Apoorva Kulkarni |
| Run every notebook top to bottom from the repo; commit outputs and the `visualizations/` PNGs | All members |
| Move all cards to Done and take a screenshot of the Kanban board | Simprabh Dhillon |

**For the next project**

| Action | Owner |
| --- | --- |
| Start from a repo template with folders, a naming convention (`01_`, `02_`, …) and a path snippet on day one | Simprabh Dhillon |
| Use project-relative paths in every notebook from the first commit | All members |
| Save every chart to `visualizations/` from its first version | Aparna Devi Nangunoori, Apoorva Kulkarni |
| Run "Restart & Run All" in the repo before moving a card to Done | All members |
| Fix the planning document structure at the sprint kick-off and change it only if needed | Simprabh Dhillon |
