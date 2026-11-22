# The Evolution of Netflix Content

**Netflix Project Assignment I – Challenge 3**

> **Business question:** How has Netflix's content library changed over time?

This repository holds our team's complete analytics workflow, from loading and cleaning the Netflix dataset to exploratory analysis, visualizations and findings. It also contains the project management documents: the project plan, sprint goal, Kanban board, risks and retrospective.

**Repository:** https://github.com/Simprabh/Netflix-Content-Evolution

**Kanban board (GitHub Projects):** https://github.com/Simprabh/Netflix-Content-Evolution/projects

---

## Team

| Member | Responsibilities |
| --- | --- |
| Sandesh Malla | Dataset management, data inspection, data cleaning and integration |
| Apoorva Kulkarni | Exploratory data analysis (EDA), statistical summaries and trend analysis |
| Aparna Devi Nangunoori | Visualizations, interpretation and business insights |
| Simprabh Dhillon | GitHub repository, project plan, Kanban board, sprint goal, risk management, retrospective, final report and README |

## Sprint goal

> By the end of Sprint 1, deliver a complete, reproducible analysis in Jupyter notebooks that shows how Netflix's content library changed over time, supported by at least three labelled visualizations and at least three business insights, together with a final report and a documented GitHub repository managed on a Kanban board.

Details: [`docs/SPRINT_GOAL.md`](docs/SPRINT_GOAL.md)

---

## Repository structure

```
Netflix-Content-Evolution/
├── data/
│   ├── raw/
│   │   └── netflix_titles.csv              # original dataset (8,807 titles, 12 columns)
│   └── cleaned/
│       └── netflix_titles_cleaned.csv      # cleaned dataset (8,807 titles, 13 columns)
├── docs/
│   ├── PROJECT_PLAN.md                     # team, tasks, owners, status
│   ├── SPRINT_GOAL.md                      # sprint goal and definition of done
│   ├── PROJECT_RISKS.md                    # two project risks and mitigation actions
│   ├── RETROSPECTIVE.md                    # sprint retrospective
│   ├── data_cleaning_report.md             # data cleaning summary
│   └── Kanban board.png                    # snapshot of the GitHub Projects board (live board: Projects tab)
├── notebooks/
│   ├── datainspection_cleaning.ipynb       # 1. inspection and cleaning (Sandesh Malla)
│   └── Netflix_EDA_Analysis.ipynb          # 2. EDA, statistics and trends (Apoorva Kulkarni)
├── visualizations/                         # charts saved automatically by the EDA notebook
└── README.md
```

---

## Dataset

**Netflix Movies and TV Shows** (public dataset, Kaggle): one row per title with `show_id`, `type`, `title`, `director`, `cast`, `country`, `date_added`, `release_year`, `rating`, `duration`, `listed_in` (genres) and `description`.

- 8,807 titles: 6,131 movies and 2,676 TV shows
- Titles were added between **1 January 2008 and 25 September 2021**, so **2021 is a partial year**

---

## How to run

**Requirements:** Python 3.10+ and the packages below.

```bash
git clone https://github.com/Simprabh/Netflix-Content-Evolution.git
cd Netflix-Content-Evolution
pip install pandas numpy matplotlib seaborn scipy jupyter
jupyter notebook
```

Run the notebooks in this order, each with **Kernel → Restart & Run All**:

1. **`notebooks/datainspection_cleaning.ipynb`** reads `data/raw/netflix_titles.csv`, cleans it and saves `data/cleaned/netflix_titles_cleaned.csv`.
2. **`notebooks/Netflix_EDA_Analysis.ipynb`** reads the cleaned file, runs the analysis and saves every chart as a PNG in `visualizations/`.

---

## Workflow

### 1. Data inspection and cleaning
*Owner: Sandesh Malla* · Full report: [`docs/data_cleaning_report.md`](docs/data_cleaning_report.md)

- Inspected missing values and duplicates: no duplicate rows or IDs. Missing values were concentrated in `director` (2,634), `country` (831) and `cast` (825).
- Fixed three records whose duration (`74 min`, `84 min`, `66 min`) was stored in `rating`.
- Replaced missing descriptive values with `Unknown`. Kept the 10 titles without `date_added` instead of inventing dates.
- Converted `date_added` to datetime, created `year_added` and standardized text and comma-separated values.
- Validated the result: 8,807 records, 13 columns, 0 duplicate rows, 0 duplicate IDs, 10 missing dates.

### 2. Exploratory data analysis
*Owner: Apoorva Kulkarni*

The EDA answers five questions, each with method, code, output and interpretation:

| # | Question | Column(s) |
| --- | --- | --- |
| 1 | How has the content library changed over time? | `date_added` |
| 2 | Are Movies or TV Shows more common? | `type` |
| 3 | Which countries contribute the most content? | `country` |
| 4 | Which genres dominate the library? | `listed_in` |
| 5 | How has the distribution of release years changed? | `release_year` |

### 3. Visualizations
Running the EDA notebook saves these charts to `visualizations/`:

| File | Chart |
| --- | --- |
| `01_titles_added_per_year.png` | Titles added per year and cumulative total |
| `02_titles_added_per_year_by_type.png` | Movies vs TV shows added per year |
| `03_titles_added_by_month.png` | Titles added by calendar month |
| `04_movies_vs_tv_shows.png` | Movies vs TV shows in the catalogue |
| `05_tv_show_share_by_year.png` | TV shows as a % of titles added each year |
| `06_top10_countries.png` | Top 10 production countries |
| `07_top5_countries_trend.png` | Trend of the top 5 countries |
| `08_top_genres.png` | Top genres overall, for movies and for TV shows |
| `09_top5_genres_trend.png` | Trend of the top 5 genres |
| `10_release_year_distribution.png` | Titles by original release year |
| `11_title_age_when_added.png` | Age of a title when added to Netflix |

---

## Key findings

| Topic | Finding |
| --- | --- |
| **Library growth** | Almost nothing was added before 2016; **2016–2019 account for 60% of all titles**, peaking in **2019 (2,016 titles)**. Over the same months, 2021 is **+10% vs 2020**, so additions plateaued rather than collapsed. October–December are the busiest months. |
| **Movies vs TV** | **Movies 69.6% (6,131) vs TV shows 30.4% (2,676)**, roughly 2.3 : 1. The TV share of new additions dipped to 25% in 2018 and recovered to about 34%. |
| **Countries** | The **United States** produces **46%** of titles with a known country, followed by **India (13%)** and the **UK (10%)**. Japan and South Korea are TV-heavy; India is movie-heavy. |
| **Genres** | **International Movies, Dramas, Comedies, International TV Shows and Documentaries** lead. Documentaries' share has been shrinking while comedies' has grown. |
| **Release years** | Median release year is **2017** and **85% of titles were released since 2010**. 55% of titles were added within a year of release, and this share of fresh content is slowly decreasing. |

**Answer to the business question:** Netflix's library grew rapidly from 2016 to 2019 and then levelled off at about 2,000 titles a year. It is still mostly movies, but TV shows have regained share since 2018. The catalogue became much more international, and the genre mix shifted toward mainstream entertainment such as comedies.

### Limitations
- `date_added` ends on 25 September 2021, so 2021 is partial in every year-based chart.
- The dataset is a 2021 snapshot: titles removed before then are missing, so early years are under-counted.
- Co-productions are counted once per country and genre, so those percentages overlap.
- The data has no viewing figures, so we describe what Netflix added, not what people watched.
- Statistical tests show association, not causation.

---

## Project management

We worked in one sprint and tracked every task on a **GitHub Projects Kanban board** linked to this repository. Each task is a card with an owner, moving from **Todo** to **In Progress** to **Done**.

**Live board:** open the repository's [**Projects** tab](https://github.com/Simprabh/Netflix-Content-Evolution/projects) and select our board.

Snapshot of the board:

![Kanban board](docs/Kanban%20board.png)

| Document | Contents |
| --- | --- |
| [`docs/PROJECT_PLAN.md`](docs/PROJECT_PLAN.md) | Team, task breakdown, owners and status |
| [`docs/SPRINT_GOAL.md`](docs/SPRINT_GOAL.md) | Sprint goal and definition of done |
| [`docs/PROJECT_RISKS.md`](docs/PROJECT_RISKS.md) | Two project risks and mitigation actions |
| [`docs/RETROSPECTIVE.md`](docs/RETROSPECTIVE.md) | What went well, what to improve, lessons and action items |

### Team Git workflow
1. `git pull` before starting work.
2. Each member edits only their own notebook, which avoids merge conflicts.
3. Commit with a clear message, e.g. `git commit -m "EDA: add genre trends"`, then `git push`.
4. Before submission, run every notebook top to bottom so all outputs and charts are saved.

---

## Submission checklist

- [x] Dataset loaded and inspected
- [x] Data cleaned and missing values handled
- [x] Exploratory data analysis
- [x] At least three labelled visualizations (11 charts)
- [x] Markdown cells explaining the work and findings
- [x] Key findings and conclusions
- [x] Version control on GitHub
- [x] Project plan, sprint goal, Kanban board, risks and retrospective
- [ ] All notebooks executed top to bottom without errors or warnings
- [ ] HTML/PDF export of the final notebook
- [ ] Screenshot of the final executed notebook
