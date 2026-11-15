# Feedback to Policy — practical GitHub annex

**Business Analyst assignment**

## Why this repository exists

The written note starts from a **fictional, not-yet-clarified request**: policy officers want to find, compare and reuse information about EU-funded research projects for policy discussions.

This annex demonstrates **one early feasibility question** from the proposed approach:

> Can a small selection of project metadata produce a transparent, source-linked shortlist that users could assess?

The aim is to demonstrate **basic, coherent use of GitHub and Jupyter**, not to develop a new search application. Before building anything, the analyst would check existing **F2P/CORDIS** services and clarify what the policy officers actually need.

## What the notebook does

1. States a **provisional policy question** and editable search terms.
2. Loads a deliberately small and **mixed-topic** dataset (energy, education, health).
3. Checks essential fields, duplicate identifiers and link format.
4. Applies a simple, explainable **keyword screening baseline**.
5. Exports both **selected and excluded projects** for user review.

The default example question concerns **digital education solely to illustrate the method**. It can be replaced in the first code cell; the written note does **not** assume any specific policy topic has been agreed with users. No AI is used in the notebook.

## Files

| Path | Purpose |
| --- | --- |
| [`notebooks/01_project_discovery.ipynb`](notebooks/01_project_discovery.ipynb) | Short explained notebook with a completed example run. |
| [`data/sample_projects.csv`](data/sample_projects.csv) | Twelve curated, **mixed-topic CORDIS-linked** example records. |
| [`outputs/candidate_shortlist.csv`](outputs/candidate_shortlist.csv) | **Provisional** matches for the illustrative question. |
| [`outputs/all_projects_for_review.csv`](outputs/all_projects_for_review.csv) | Selected **and excluded** records, with blank user-review fields. |
| [`outputs/data_quality_checks.csv`](outputs/data_quality_checks.csv) | Simple completeness and traceability checks. |

## Run locally (optional)

Use Python 3.10+ and install the small set of dependencies:

```bash
python -m pip install -r requirements.txt
jupyter notebook notebooks/01_project_discovery.ipynb
```

Run all cells from top to bottom. The input is a CSV file in `data/`, and output files are written to `outputs/`. It should also run in VS Code with the Python and Jupyter extensions. **No login, API key, model, or private data is required.**

## How this connects to the written note

| Written-note point | Demonstration here |
| --- | --- |
| **Section 1: Clarify needs** | The notebook distinguishes provisional assumptions from confirmed requirements. |
| **Section 2: Conceptual framework** | One user question maps to data fields → quality checks → search → reviewable outputs. |
| **Section 3: AI/data choice** | An explainable, non-AI keyword baseline comes before any proposal to use embeddings or LLMs. |
| **Section 4: Practical tools** | GitHub repository structure, README, Jupyter notebook and reproducible example outputs. |
| **Section 5: Implementation** | User review is required before accepting the approach or starting an operational pilot. |

## Essential limitations

- The 12 projects are **hand-picked**, not a representative sample and not a CORDIS data export.
- Grant identifiers, acronyms, titles and links point to public CORDIS project records; `short_description` and `example_domain` are **analyst-prepared**, not official metadata.
- URL format is checked by the notebook, **not live page availability or project-data currency**.
- The simple matching rule can miss relevant projects or return irrelevant ones. The exported `user_relevance` fields are intentionally **blank**: no policy officers have reviewed these examples.
- Project aims are **not verified research findings**. There are no AI-generated claims, scientific synthesis or policy recommendations.

A real F2P use case would require agreed policy objectives, an authorised representative data source, data-quality checks, user-labelled examples, assessment of existing tools and governance approval before wider implementation.
