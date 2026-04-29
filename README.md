# Manufacturing FPY Dashboard (Power BI)

## Overview

This project simulates a manufacturing analytics scenario for a fictional guitar company and demonstrates how production data can be transformed into clear, decision-oriented insight.

**Core question:**
Where is yield loss occurring, and what process changes would have the greatest impact?

---

## Key Insights (Default filtering: all Families, Lines, and Models)

- FPY: 90.2% (below target)
- Failures are concentrated in the **Finishing** stage
- Top defect: **Glue curing error**
- Majority of issues are **internal (60.6%)**

**Conclusion:**  
Yield loss is driven primarily by internal process issues within a specific stage, indicating that improvements in process control would have the greatest impact.

---

## Dashboard Preview

### Default View
![Default View](screenshots/default_view.png)

### "Finishing" Stage Selected in chart (updates Top 5 defects, Root Cause Category, and Top 5 Suppliers visuals)
![Finishing Stage](screenshots/finishing_stage_selected.png)

### Filtered Example (Duskwind Series - updates KPI row and all visuals)
![Filtered View](screenshots/filtered_to_duskwing_series.png)

### Slicer Panel
![Slicer Panel](screenshots/slicer_panel_showing.png)

### Tooltip Example
![Tooltip](screenshots/top_contributers_tooltip.png)

---

## Tools Used

- Power BI: star schema data modeling, DAX measures, conditional formatting, custom tooltip pages
- Python: synthetic data generation
  - Pandas: DataFrame construction and CSV output across 9 structured files
  - uuid, random, dateutil: unit ID generation, seeded randomization, and date arithmetic

---

## Approach

 - Generated 2,000+ production unit rows and 11,000+ inspection rows across 9 CSV files simulating 14 months of guitar manufacturing operations
 - Modeled 45 defect types and 35 root causes with stage-aware selection logic, preventing defects from appearing at production stages where they couldn't realistically be detected
 - Applied weighted root cause attribution per defect, distinguishing supplier-driven, internal, and shared responsibility
 - Calibrated scrap probabilities per defect type, ranging from near-certain scrap for structural wood failures to rare scrap for finish and process defects
 - Modeled relationships between stages, defects, and root causes in Power BI
 - Built DAX measures for FPY and failure distribution
 - Designed a single-page dashboard focused on clarity and decision support

---

## Full Project Write-Up

For a detailed breakdown of the business problem, methodology, and recommendations:

👉 [View Full Project Details](project_details.md)
