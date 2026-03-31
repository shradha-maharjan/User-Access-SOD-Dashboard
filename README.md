
## Project Overview
This project simulates a real-world IT Audit for Identity & Access Management (IAM) in a financial/enterprise system.

It demonstrates how traditional manual auditing can be transformed into automated, data-driven risk monitoring using modern analytics tools.

The solution identifies critical access control risks such as:
- Orphaned Accounts (terminated employees with active access)
- Segregation of Duties (SoD) Violations (toxic permission combinations)

The final output is an interactive Power BI dashboard designed for executives, auditors, and IT security teams.

## Power BI Dashboard

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/18ce93e2-5adb-4185-bf51-94239d78654d" />

---

## Objectives

The primary goals of this project are:

1. Detect Orphaned Accounts  
   - Identify users marked as terminated but still having system access  
   - Highlight failures in offboarding controls  

2. Identify SoD (Segregation of Duties) Risks  
   - Detect users with conflicting permissions such as:
     - Create Vendor + Approve Payment  
     - Dev Access + Prod Deploy  
   - Prevent fraud and unauthorized system manipulation  

3. Enable Continuous Monitoring  
   - Replace manual audit checks with automated analytics  
   - Provide real-time Key Risk Indicators (KRIs)  

---

## Tech Stack

| Tool        | Purpose |
|-------------|--------|
| Excel       | Data storage and initial structure |
| Power Query | Data cleaning, transformation, joins |
| Power BI    | Dashboard visualization and KPI reporting |
| Python      | Synthetic dataset generation (10,000+ records) |

---

## Dataset Structure

### 1. User_Master
- Contains user details (User_ID, Department, Job_Title, Status)
- Tracks active vs terminated employees

### 2. User_Permissions
- Maps users to system permissions

### 3. SoD_Risk_Matrix
- Defines toxic combinations of permissions
- Includes risk level and descriptions

---

## Data Processing Logic

### Orphaned Account Detection
- Join User_Permissions with User_Master on User_ID  
- Filter records where:
# Status = "Terminated"

- These represent unauthorized active accounts  

---

### SoD Violation Detection (Advanced Logic)
- Match permissions with SoD_Risk_Matrix (Permission_A)
- Perform a self-join to check if the same user also has Permission_B
- Output represents confirmed SoD violations  

---

## Dashboard Features

### KPI Cards
- Total SoD Violations  
- Total Orphaned Accounts  
- Dormant Account %  
- Total Users / Permissions  

### Visualizations
- Risk % by Department (Line Chart)  
- Permission Violations by Department (Bar Charts)  
- Risk Heatmap (Matrix View)  
- User-Level Risk Table  

### Interactivity
- Filters by:
- Department  
- Risk Level  
- Permission Type  

---



## Key Insights

- Identified high-risk SoD conflicts across departments  
- Detected terminated users with active permissions  
- Highlighted departments with highest risk exposure  
- Provided actionable visibility into access control gaps  

---

## Audit Findings (Sample)

| Finding            | Description |
|------------------|------------|
| Orphaned Accounts | Terminated users still have system access |
| SoD Violations    | Users have conflicting permissions |
| Dormant Accounts  | Users inactive for more than 90 days |

---

##  Business Impact

- Prevents fraud and unauthorized transactions  
- Strengthens internal controls (ITGC)  
- Supports compliance frameworks (SOX, COBIT, COSO)  
- Enables proactive risk management  

---

##  How to Run the Project

1. Open Power BI Desktop  
2. Load dataset (Excel/CSV)  
3. Apply transformations in Power Query  
4. Build relationships between tables  
5. Create DAX measures:
 - Orphan Count  
 - SoD Count  
 - Risk %  
6. Build dashboard visuals  

---

##  Future Enhancements

- Integrate with real-time logs (SIEM / Entra ID)  
- Automate alerts for high-risk users  
- Add role-based access control (RBAC) analysis  
- Deploy to Power BI Service for live monitoring  

---

##  What This Project Demonstrates

- IT Audit & Risk Assessment  
- Data Analytics for Security  
- Power BI Dashboard Design  
- Real-world IAM & SoD concepts  
- Automation of audit processes  

---
