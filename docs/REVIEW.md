# Source review — 2026-09-13

## Strength

Notebook code separated into notebooks/data/tests with repeated source in starter.

## Findings

Both notebooks have identical code but data path assumes repository root; existing pytest helpers have no test_ functions; CI notebook working directory is wrong.

## Changes in this pass

README documentation now describes the checked-in source and known limitations. Local environment/cache ignore patterns were added without hiding required datasets or serialized test fixtures. Only confirmed OS metadata and Python bytecode were removed where present. Existing application/model logic is unchanged.

## Remaining work

Choose one notebook and implement real CI tests; fix working-directory handling after approval, then add held-out ranking evaluation.

## Portfolio decision

Keep as development history or Private after canonical IBM selection.

## Validation scope

Tracked-file inventory, Python syntax inspection, notebook JSON/code inspection, and path/schema checks were performed. This is not a claim of a full application, camera, cloud, training, or database integration run. Runtime-specific results are recorded in the account review report. Existing licenses and differing notebook checkpoints are retained. Bulk deletions, privacy changes, data/schema changes and model retraining require a separate decision.

## Observed runtime check

Executed 1 code cells in order in `notebooks/Recommendations_with_IBM.ipynb`. Result: `failed`. First stop: cell 5, FileNotFoundError: notebooks/data/user-item-interactions.csv is absent. Analysis was run through IPython with the Agg plotting backend; display-only matplotlib magic and HTML export were excluded. Notebook source and assertions were unchanged. Python 3.12; audit environment used pandas 2.3.3, NumPy 2.5.3, scikit-learn 1.9.1, and pytest 9.1.1. This is an audit environment, not a claim that the original dependency manifest was installed successfully.
