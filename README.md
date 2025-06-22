# connectivity-modes
Row Level Security
📌 Problem Statement
ABC is a globally recognized restaurant inspection agency that monitors hygiene and compliance across various facilities. Each facility is linked to a region, and inspectors are assigned based on regional distribution. The organization collects detailed records of inspections, sanitary grades (A, B, C), and violation codes. To enable data-driven decision-making and secure reporting, ABC needs a Power BI report that:

Visualizes inspections and violations by region.

Provides insights into sanitation performance by grade.

Implements role-based security so inspectors can only view relevant regional data.

The core challenge is to design a dynamic, role-aware report that offers clear visualizations while enforcing secure access at a regional level.
📊 Project Overview: Restaurant Inspections Dashboard
This Power BI dashboard delivers a region-wise view of restaurant inspection data with clear visuals and role-based access.

🔧 Key Objective 1: Data Visualizations
Clustered Column Chart:

Displays inspection volume by facility region.

X-axis: Number of inspections; Y-axis: Facility Region.

Chart Title: “Inspection Volume”.

Decomposition Tree for Violations:

Created Measure: Violation = COUNT('Restaurant Inspection Data'[violation_code])

Used in the Analyze field.

Explain By: facility_region (from Region Lookup) → violation_description (from Restaurant Inspection Data).

Custom Formatting:

Chart Title: “Violations by Region & Type” (white font, black background, centered).

Tree Primary Color: Blue #118DFF

Positive Data Bar Color: Yellow #e1c233

Tooltip Measure: % of Total Violations based on violation_code and serial_number.

Sanitation Grade Donut Chart:

Values: Grades A, B, C from sanitation_grade (Legend: from Sanitary Grade Lookup).

Title: “Sanitation Grade” (white font, black background, centered).

Color Settings:

A = #FFD710

B = #119E30

C = #E66C37

Legend: Off; Labels: On (set to Category).

Renamed Page: “Inspections & Violations”.

🎯 Key Objective 2: Report Refinement
Adjusted chart alignment, spacing, and applied consistent design formatting.

Ensured seamless layout with separation lines and appropriate chart styles.

🔐 Key Objective 3: Role-Level Security (RLS)
Created two roles:

Lead Inspector: Can view regions with Region Code 1–10.

Chief Inspector: Can view all regions (1–16).

Applied filters using DAX and tested in Power BI Desktop:

Verified the filtered views reflect correct data access.

Published the report to Power BI Service:

Overwrote existing dataset.

Used "Test as role" feature to confirm accurate row-level security for both roles.
