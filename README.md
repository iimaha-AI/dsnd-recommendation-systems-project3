# IBM Article Recommendation Study

A notebook-based study of implicit user-article interactions for IBM Watson Studio, exploring popularity, user-user collaborative filtering, content similarity, and matrix factorization. This is an educational analysis, not a deployed service.

## Repository guide

- [notebooks/Recommendations_with_IBM.ipynb](notebooks/Recommendations_with_IBM.ipynb): analysis and recommendation functions.
- `data/user-item-interactions.csv` relative to the notebook working directory: interaction data.
- `project_tests.py` and `top_*.p`, where supplied: course helpers and expected answers, not disposable temporary models.

The notebooks in `notebooks/` and `starter/` have identical code. The notebook expects `data/` relative to its kernel working directory. Existing CI runs pytest against helpers without discoverable test names and executes the notebook from a directory without `data/`.

## Setup

```bash
git clone https://github.com/iimaha-AI/dsnd-recommendation-systems-project3.git
cd dsnd-recommendation-systems-project3
python -m venv .venv
```

Activate with `source .venv/bin/activate` on macOS/Linux or `.venv\Scripts\Activate.ps1` in PowerShell, then:

```bash
python -m pip install -r requirements-notebook.txt
python -m notebook
# Open notebooks/Recommendations_with_IBM.ipynb and set the kernel working directory to the repository root.
```

The dependency list is a starting environment, not a validated lockfile. Known execution limits are listed below.


## Approach

Inspect missing users and popularity, map user IDs, build a binary user-item matrix, compare similar users, and explore content/latent-factor similarities. Functions depend on notebook state and are not yet an importable application API.

## Validation and limitations

Run from a fresh kernel in cell order. Inspect assertions and printed messages: some course helpers print incorrect-answer messages without raising exceptions. Saved output does not prove a fresh run passes.

Reconstruction metrics on the matrix used for fitting are in-sample diagnostics, not held-out recommendation benchmarks. Add a held-out interaction split, popularity baseline, Recall@K/NDCG@K, coverage, and cold-start evaluation. Clustering and exact-neighbor assertions may vary with initialization and library versions.

## Next development steps

- Resolve the execution issues in [review notes](docs/REVIEW.md).
- Extract pure recommendation functions and test unknown users, empty histories, and duplicate recommendations.
- Lock dependencies after an end-to-end run and publish a small demo with reproducible results.

## Attribution

Based on Udacity Data Scientist Nanodegree material and IBM Watson Studio interaction data. Preserve the existing [LICENSE.txt](LICENSE.txt). Data licensing is separate from code licensing.

## Dependency scope

`requirements-notebook.txt` supplies an optional minimal notebook environment. The original `requirements.txt` also lists web/API/documentation packages not imported by this notebook and does not install Jupyter Notebook; it is retained pending dependency migration.
