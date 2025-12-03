🏥 Patient Advocacy Operations Tracker
A healthcare operations analytics project that simulates how a patient advocacy navigation lead would track backlog, responsiveness, and workload across their team. Built from scratch using a hand-crafted JSON schema, expanded with Python, and visualized in Power BI to answer the operational questions that guide staffing, prioritization, and escalation decisions.

📌 Project Objective
This project was built to mirror the day-to-day analytics needs of a healthcare advocacy or navigation team. It focuses on turning raw case and interaction data into clear operational signals that help leaders answer:
- Where is work piling up?
- How fast are we responding to patients?
- Who is overloaded, and who has capacity?

🔁 Project Workflow
1. Design the Data Model
Started with a nested JSON schema representing advocacy cases and their interaction histories — capturing issue type, priority, timestamps, advocate assignments, and resolution status.

2. Generate Realistic Synthetic Data
Hand-wrote 4–5 realistic cases with 4–6 interactions each, then used Python to scale that seed into ~50 cases with varied patterns across issue types, priorities, response times, and workloads.

3. Flatten and Engineer Metrics
Converted the nested JSON into two analysis-ready tables:
- Case-level (cases_analysis_ready.csv)
- Interaction-level (interactions_analysis_ready.csv)

Engineered key metrics:
- Time to first response
- Resolution time
- Interaction counts
- Reassignment flags
- Open backlog by advocate

4. Build Power BI Reports
Created three interconnected report views that share the same slicers (date, issue type, priority), enabling a navigation lead to filter once and explore multiple operational angles.

📊 The 3 Reports
All three views live in a single Power BI report with shared slicers for consistent filtering:

Report View	What It Answers
Average Time to First Response by Issue Type & Priority	How quickly are patients hearing back? Which segments are slower?
Case Detail: Resolution Time, Interactions, Reassignments	Why are certain cases taking longer? Where are handoffs happening?
Open Case Backlog by Advocate	Who is overloaded? Where should new work be routed?


⚙️ Key Metrics Tracked
-  Time to First Response — elapsed time from case open to first advocate interaction
-  Resolution Time — total time from case open to closure
-  Interaction Count — number of touches per case
-  Reassignments — how many times a case switched advocates
-  Open Backlog by Advocate — current workload distribution and priority mix

These metrics map directly to the operational questions advocacy teams ask every week.

🧠 Why This Matters
In advocacy and navigation roles, operational visibility is critical. Teams need to:

-  Spot bottlenecks before they become backlogs
-  Balance workloads fairly across advocates
-  Prioritize high-urgency cases that are at risk of delay
-  Understand where process friction (e.g., reassignments) is slowing resolution

This project simulates the reporting layer that enables those decisions.

🚀 Real-World Application
This structure mirrors how a data analyst at a healthcare company would:
-  Take messy operational data from case management systems
-  Shape it into clean, analysis-ready tables
-  Build repeatable dashboards that answer recurring leadership questions
-  Enable non-technical stakeholders to self-serve insights without repeated ad hoc requests

📁 Folder Structure

patient-advocacy-ops-tracker/
├── data/
│   ├── raw/                          # Intermediate exploratory outputs
│   │   ├── case_metrics_raw.csv
│   │   └── backlog_by_advocate_raw.csv
│   └── processed/                    # Final analysis-ready tables
│       ├── cases_analysis_ready.csv
│       └── interactions_analysis_ready.csv
├── notebooks/
│   └── advocacy_operations_tracker.ipynb   # Full Python pipeline
├── reports/                          # Power BI dashboards
│   ├── Average Time to First Response by Issue Type & Priority.pbix
│   ├── Case Detail Resolution Time, Interactions, Reassignments.pbix
│   └── Open Case Backlog by Advocate.pbix
├── initial_advocacy_cases.json       # Hand-written seed data
└── README.md


🔧 Tools Used: 
Python — synthetic data generation, flattening, metric engineering
JSON — structured data modeling
Kaggle Notebooks — development and experimentation environment
Power BI — interactive reporting and visualization with DAX and slicers


🎯 How to Explore the Project:
Start with the notebook (notebooks/advocacy_operations_tracker.ipynb) to see how the JSON seed is expanded and split into case and interaction tables.
Review the processed tables (data/processed/) to understand the final feature set used in reporting.
Open the Power BI files (reports/*.pbix) and use the shared slicers to filter by date, issue type, and priority, then flip between the three views to see backlog, response times, and case details for the same slice.

