Project Details: Manufacturing FPY Analysis

## 1. Summary

This project simulates a manufacturing analytics scenario for a fictional guitar company and demonstrates how production data can be transformed into clear, decision-oriented insight through a focused dashboard.

I built a Python-based data generator to create realistic, relational datasets (production units, defects, root causes, suppliers, etc.), then modeled and visualized that data in Power BI to answer a central question:

Where are we losing yield, why is it happening, and where should improvement efforts be focused?

The final output is the first pass of a single-page dashboard that highlights (Default filtering: all Families, Lines, and Models):

- Current FPY performance (90.2% vs. target)
- Where failures are concentrated (Finishing stage)
- What is driving those failures (Glue curing errors)
- Whether issues are internal or supplier-driven (60.6% internal)

The key takeaway:
Yield loss is concentrated in a specific stage and driven primarily by internal process issues, indicating that improvements in process control and execution (particularly in Finishing) would have the greatest impact on overall performance.


## 2. Business Problem

Manufacturing teams rely on First Pass Yield (FPY) to understand how efficiently products move through production without requiring rework or scrap. However, raw production data alone does not answer the questions that matter:

- Which stage is creating the most risk?
- What specific defects are driving failures?
- Are issues primarily internal or supplier-driven?
- Where should improvement efforts be focused first?

For this project, I defined a realistic scenario:

A mid-sized guitar manufacturer is experiencing yield loss and rising rework costs. Leadership needs a clear, data-driven way to identify the primary sources of failure, understand their causes, and focus improvement efforts where they will have the greatest impact.

The challenge is to connect reporting metrics to a clear narrative that supports decision-making.

## 3. Methodology
Data Preparation (Python)

I created a structured dataset to simulate a manufacturing environment, including:

- Production units (one row per unit)
- Quality Inspections (pass/fail at each stage)
- Associated defects (supporting multiple defects per unit)
- Root cause classification (internal vs. supplier-linked)
- Suppliers and components

The data was designed to reflect realistic relationships between production stages, defect types, and failure outcomes, allowing for meaningful analysis without unnecessary complexity.

Data Modeling (Power BI)

I modeled the data using a relational structure to support analysis across:

- Production stages
- Defect types
- Root cause categories
- Supplier attribution

Key measures were developed using DAX, including:

- FPY %
- First-pass failure counts
- Distribution of failures by stage, defect, and root cause
- Context-aware percentages using filter-aware calculations
- Dashboard Design

The dashboard was designed as a single-page view with a clear analytical flow:

- KPI row for overall performance
- Stage-level breakdown of failures
- Identification of top defects
- Root cause segmentation (internal vs. supplier-linked)

A dynamic insight panel summarizes key findings and adjusts based on user selections, reinforcing the connection between data and interpretation.

## 4. Skills Demonstrated
- Data Engineering / Preparation
- Python (data generation, structured simulation)
- Pandas (data shaping and transformation)
- Relational data modeling
- Synthetic data design for realistic business scenarios

Business Intelligence
- Power BI dashboard development
- DAX measures:
  - Context-aware calculations
  - Percentage of total using REMOVEFILTERS
  - KPI aggregation logic
- Star schema design and relationship management

Analytics & Problem Solving
- Root cause analysis
- Failure segmentation (stage, defect, supplier)
- KPI design aligned to business questions
- Translating data into decisions, not just visuals

UX / Communication
- Information hierarchy in dashboard design
- Narrative-driven layout
- Dynamic insight generation based on user interaction

## 5. Results & Recommendations
Key Findings
- FPY: 90.2% (below target)
- Primary failure stage: Finishing (62 first-pass failures)
- Top defect: Glue curing error (18 occurrences)
- Root cause split:
  - Internal: 60.6%
  - Supplier-linked: 40.7%

What This Indicates:

Failures are not evenly distributed—they are concentrated within a specific stage and driven by a small number of defect types. A majority of issues originate internally, suggesting that process execution and control are the primary drivers of yield loss.

Recommended Focus Areas
1. Improve Finishing Process Control
   - Standardize glue curing conditions and introduce validation checkpoints prior to final assembly.
2. Address High-Impact Defects
   - Prioritize reduction of glue curing errors and rework-related damage through clearer process controls and operator guidance.
3. Reduce Internal Variability
   - Evaluate tooling practices and setup consistency to address defects such as improper tool use.

Secondary: Review Supplier Contributions
 - Investigate top contributing suppliers to ensure material consistency and incoming quality standards.

Expected Impact:

Because failures are concentrated, targeted improvements—particularly within the Finishing stage—would have a disproportionate effect on overall FPY. Reducing a small number of high-frequency defects could meaningfully improve yield, reduce rework, and increase throughput reliability.

## 6. Potential Extensions

If expanded, this analysis could be extended to support deeper monitoring and decision-making through:

- Time-series analysis (e.g., control charts for FPY and defect rates)
- Cost of Poor Quality (COPQ) to prioritize issues by financial impact
- Expanded supplier performance analysis and segmentation

These additions would extend the dashboard from diagnostic insight into ongoing process monitoring and optimization.
