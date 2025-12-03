Project overview
This project simulates an advocacy operations cockpit for a navigation lead. It focuses on where work is piling up, how quickly patients receive first responses and resolutions, and which advocates are over capacity. The goal is to turn messy, interaction-level activity into clear operational signals that guide staffing, prioritization, and escalation decisions.

Business questions and metrics
The project is built around a few practical questions an advocacy or navigation lead would care about each week:

How long are patients waiting for a first response, and does that vary by issue type or priority?

How long do cases take to resolve once they are opened?

How many interactions and reassignments does it typically take to close a case?

Which advocates are carrying the largest open backlog, and who still has capacity?

To answer these, the analysis tracks metrics such as time to first response, resolution time, interaction counts, reassignments, and open case backlog by advocate.

Data and pipeline
The data flow is intentionally simple and transparent:

The project starts with a small set of hand-written cases and interactions in initial_advocacy_cases.json, capturing 4–5 realistic cases with multiple interactions each.

The notebook notebooks/advocacy_operations_tracker.ipynb uses Python to expand this seed into around 50 synthetic cases with varied patterns, while keeping the structure and logic grounded in real operational scenarios.

From there, the notebook produces:

data/raw/case_metrics_raw.csv and data/raw/backlog_by_advocate_raw.csv as intermediate, exploratory outputs.

data/processed/cases_analysis_ready.csv and data/processed/interactions_analysis_ready.csv as clean, analysis-ready tables at the case and interaction level.

These processed tables are used as the basis for the Power BI reports.

Reports in this repo
All three views live inside a single Power BI report and share the same slicers, so a navigation lead can filter once and then look at the data from different angles:

Average Time to First Response by Issue Type and Priority
Shows how quickly patients receive their first response after opening a case, broken down by reason and priority level, so slower segments stand out immediately.

Case Detail: Resolution Time, Interactions, Reassignments
Drops down to individual cases, highlighting how long they took to resolve, how many interactions were involved, and where reassignments occurred, which helps explain why certain cases dragged on.

Open Case Backlog by Advocate
Focuses on current workload by advocate and priority, making it easier to see who is overloaded and where new work should be routed.

The corresponding files are in reports/:

Average Time to First Response by Issue Type & Priority.pbix

Case Detail Resolution Time, Interactions, Reassignments.pbix

Open Case Backlog by Advocate.pbix

How to explore this project
Open notebooks/advocacy_operations_tracker.ipynb to see how the initial JSON is expanded into a larger synthetic dataset and split into case-level and interaction-level tables.

Inspect data/processed/cases_analysis_ready.csv and interactions_analysis_ready.csv to review the final tables that feed the reports.

Open the .pbix files in reports/ with Power BI Desktop. Use the shared slicers (e.g., date, issue type, priority) to filter the data, then switch between the three report pages to see backlog, first response times, and case details for the same slice.

Tools used
Python, JSON, Kaggle Notebooks, Power BI.
