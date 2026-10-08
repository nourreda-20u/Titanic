# Titanic Passenger Survival Analysis

An exploratory data analysis of 891 Titanic passenger records using direct Pandas operations, Matplotlib and Seaborn. The notebook covers all 30 questions in the Titanic workshop, with objectives, visible calculations, group counts, interpretations and a final conclusion.

## Start here

- [Open the completed notebook](Titanic_DA_Workshop.ipynb)
- [Open in Google Colab](https://colab.research.google.com/github/nourreda-20u/Titanic/blob/main/Titanic_DA_Workshop.ipynb)
- [Download the source dataset](titanic_dataset.csv)

The notebook includes executed results and charts, so it can be read directly on GitHub.

## Repository files

| File | Purpose |
|---|---|
| `Titanic_DA_Workshop.ipynb` | Main analysis, all 30 questions and conclusions |
| `titanic_dataset.csv` | Original passenger data supplied for the workshop |
| `requirements.txt` | Python packages for local execution |
| `.gitignore` | Excludes notebook checkpoints, environments and generated exports |

## Run locally

Use Python 3.11 or newer (the notebook was verified with Python 3.12). Clone or download this repository, then open a terminal in its folder:

```bash
python -m venv .venv
```

Activate the environment on Windows:

```powershell
.venv\Scripts\Activate.ps1
```

Or on macOS/Linux:

```bash
source .venv/bin/activate
```

Install the packages and start Jupyter:

```bash
python -m pip install -r requirements.txt
python -m jupyterlab
```

Open `Titanic_DA_Workshop.ipynb` and select **Restart Kernel and Run All Cells**. Keep the CSV next to the notebook and launch Jupyter from this repository folder.

## Run in Google Colab

Use the Colab link above. Run the cells from top to bottom; the loading cell prompts you to upload the supplied Titanic CSV. Its original upload filename is accepted. Colab already includes the main analysis libraries.

## Notebook structure

1. Project brief and loading
2. Dataset understanding and column dictionary
3. Missingness, duplicates, validity and outlier checks
4. Justified preparation and feature engineering
5. Passenger distributions
6. All 30 survival-analysis questions
7. Consolidated key findings
8. Conclusion and prepared-data export

## Analytical choices

- `df_raw` preserves the source, and `df_clean` holds the prepared table.
- Missing ages are retained; age analyses use the 714 observed ages.
- The two missing ports are labeled `Unknown` rather than guessed.
- Extreme but plausible values are retained.
- Family size is `SibSp + Parch + 1`; alone means no recorded relatives.
- Children are defined as under 16. Age bins and fare quartiles are explained where created.
- Shared-ticket counts are based on this sample, not the entire ship.
- Summaries include both passenger counts and survival percentages.
- Class comparisons help examine overlapping fare, cabin and port associations.

Running the final export cell creates `titanic_prepared.csv` beside the notebook. This generated file is ignored by Git; the source CSV is retained in the repository.

## Main findings and limits

Overall survival is 38.38%. Female survival is 74.20% versus 18.89% for males. First-class survival is 62.96% versus 24.24% in third class. These patterns remain relevant when sex and class are considered together.

The data describe associations, not proven causes. Age is missing for 19.87% of passengers and Cabin for 77.10%. Sparse groups, shared family/ticket circumstances, sample coverage and unmeasured rescue conditions limit interpretation.

## Learning approach

The analysis uses the supplied learning notebook as a style reference: clear objectives, short direct Pandas calculations, readable tables, basic charts and written interpretations. It uses explicit `groupby`, `agg`, `loc`, `map`, `merge`, pivot tables and cross-tabulations rather than hiding calculations in custom helper functions. No dashboard is needed to complete the workshop.
