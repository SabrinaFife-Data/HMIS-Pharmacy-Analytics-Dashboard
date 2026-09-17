# HMIS Pharmacy Analytics & Inventory Dashboard

## Project Overview
An executive-level Power BI analytics dashboard built to monitor prescription trends, patient treatment durations, and critical drug inventory reorder levels.

![Dashboard Preview](path-to-your-screenshot.png)

## Data Schema & Relational Model
- **admission:** Patient admission records & timelines
- **prescription:** Medication orders linked to admissions
- **drug:** Master drug catalog and categories
- **drug_inventory:** Current stock and safety reorder thresholds

## Key DAX Measures
```dax
Total Prescriptions = COUNTROWS('prescription')

Total Stock Quantity = SUM('drug_inventory'[current_stock])

Avg Treatment Duration = AVERAGE('prescription'[duration_days])

Low Stock Count = CALCULATE(COUNTROWS('drug_inventory'), 'drug_inventory'[inventory_status] = "Low Stock")
