# Project Risks and Mitigation – The Evolution of Netflix Content (Challenge 3)

**Risk owner:** Simprabh Dhillon (project manager)

| Risk | Impact | Mitigation action | Owner |
| --- | --- | --- | --- |
| **1. Poor data quality may distort the conclusions.** 2,634 titles have no director, 831 no country and 825 no cast; 10 have no `date_added`; 3 had a duration in `rating`; the data stops on 25 Sep 2021, so 2021 is a partial year. | High: wrong trends, e.g. reading 2021 as a decline | Clean and validate first (T5–T7, done): `Unknown` instead of dropped rows, validation checks in notebook 01. Exclude the 10 undated titles from time-based analysis, and label 2021 as partial (or compare the same months) in every chart. | Sandesh Malla (cleaning); Apoorva Kulkarni and Aparna Devi Nangunoori (partial-year handling) |
| **2. Parallel work on notebooks causes Git conflicts or a broken final notebook.** `.ipynb` files are JSON and conflict easily. | Medium: lost work, missed deadline | One notebook per owner (01/02/03); pull before every push; small, clearly named commits; final "Restart & Run All" of every notebook before submission (T13). | Simprabh Dhillon |
