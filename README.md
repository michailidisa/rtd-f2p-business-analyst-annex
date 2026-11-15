# Feedback to Policy — practical GitHub annex

**Business Analyst assignment**

## Why this repository exists

The written note starts from a **fictional, not-yet-clarified request**: policy officers want to find, compare and reuse information about EU-funded research projects for policy discussions.

This annex demonstrates **one early feasibility question** from the proposed approach:

> Can a small selection of project metadata produce a transparent, source-linked shortlist that users could assess?

The aim is to demonstrate **basic, coherent use of GitHub and Jupyter**, not to develop a new search application. Before building anything, the analyst would check existing **F2P/CORDIS** services and clarify what the policy officers actually need.

## What the notebook does

Using a a small dataset of 12 CORDIS-linked **hand-picked projects**, not a representative sample and not a CORDIS data export,  covering different research areas. For illustration, the notebook searches for projects related to digital education. The topic and search terms can be changed in the first code cell.

1. Inspect the data: Load project records and check essential fields, duplicate identifiers and source-link formats.
2. Test a simple approach: Apply transparent keyword matching to identify potentially relevant projects.
3. Prepare user review: Export both selected and excluded projects, including the matching terms and source links.

The exercise uses Python/pandas in Jupyter, without an AI model or external API.

## Files

| Path | Purpose |
| --- | --- |
| [`notebooks/01_project_discovery.ipynb`](notebooks/01_project_discovery.ipynb) | Data exploration, basic checks and keyword search |
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

Run the notebook cells in order. It can also be opened in VS Code with the Python and Jupyter extensions.
No credentials or private data are required.

## Essential limitations

- The 12 projects are **hand-picked**, not a representative sample and not a CORDIS data export.
- Identifiers, acronyms, titles and links point to public CORDIS project records; `short_description` and `example_domain` are **analyst-prepared**, not official metadata.
- URL format is checked by the notebook, **not live page availability or project-data currency**.
- The simple matching rule can miss relevant projects or return irrelevant ones. The exported `user_relevance` fields are intentionally **blank**: no policy officers have reviewed these examples.
- Project aims are **not verified research findings**. There are no AI-generated claims, scientific synthesis or policy recommendations.

A real F2P use case would require agreed policy objectives, an authorised representative data source, data-quality checks, user-labelled examples, assessment of existing tools and governance approval before wider implementation.
