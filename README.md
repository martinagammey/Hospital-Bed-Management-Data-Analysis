# Hospital-Bed-Management-Data-Analysis
An exploratory data analysis Jupyter notebook designed to evaluate hospital resource utilization, staff performance, and patient satisfaction across various medical services. This analysis leverages historical data to identify trends in bed availability, admission/refusal rates, and staff attendance to support better operational decision-making.

## Overview
This project analyzes four key datasets to answer critical questions about hospital efficiency:

  • Staffing: Role distribution, departmental breakdown, and attendance consistency.
  
  • Patient Flow: Admission requests, actual admissions, refusals, and satisfaction scores.
  
  • Resource Utilization: Bed availability trends and service-specific demand.
  
  • Temporal Patterns: How metrics fluctuate by month and week throughout the year.
    
## Dataset Description

The analysis utilizes the following CSV files (expected path: /kaggle/input/hospital-beds-management/):

| File Name  | Description | Titles |
| ------------- | ------------- | ------------- |
| staff.csv  | Employee records and roles  | Department, Role, service |
| patients.csv  | Patient treatment records  | Condition, satisfaction, service | 
| services_weekly.csv  | Weekly service metrics  | month, week, patients_admitted, patients_request, patients_refused, available_beds, patient_satisfaction | 
| staff_schedule.csv  | Staff attendance logs  | week, service, present | 

## Prerequisites

Ensure the following Python libraries are installed in your environment (pre-installed in the Kaggle Python kernel):

  • pandas (Data manipulation)
  
  • numpy (Numerical operations)
  
  • matplotlib & seaborn (Data visualization)
  
  • statsmodels (Statistical modeling - imported but not used in the final plotting section)
    
## Installation

If running locally, install dependencies via pip:

``` bash
pip install pandas numpy matplotlib seaborn statsmodels
```

## Usage
  1. Load Data: The notebook automatically scans the /kaggle/input/ directory for the required CSV files.
  
  2. Data Cleaning:
        ◦ Missing values in Department and Role are filled with 'Unknown' and 'Not Assigned'.
        ◦ Missing Condition in patients is filled with 'Not Specified'.
        ◦ Duplicate rows are removed from all datasets.
     
  3. Visualization: Custom color palettes ("Candy" and "Dark") are applied to all charts for consistent branding.
  
  4. Analysis: The notebook generates the following visual reports:

     ◦ Monthly average patient satisfaction trends.

     ◦ Satisfaction scores broken down by service type.

     ◦ Staff attendance rates per service and over time.

     ◦ Admission rates and refusal rates per service.

     ◦ Stacked bar chart of total patient requests by month and service.

     ◦ Average bed availability per service.
     
## Key Metrics Analyzed

  • Admission Rate: $\frac{\text{Patients Admitted}}{\text{Patients Requested}}$
  
  • Refusal Rate: $\frac{\text{Patients Refused}}{\text{Patients Requested}}$
  
  • Attendance Rate: Mean of present flag grouped by service/week.
  
  • Satisfaction Score: Mean of patient_satisfaction or satisfaction columns.
    
## Custom Styling
The notebook defines two custom Seaborn palettes:

  • Candy Palette: ["#22EAFE", "#D180FF", "#FF80D6", "#FFF980"] (Used for positive metrics)
    
  • Dark Palette: ["#16101B", "#691372", "#818185", "#860631"] (Used for structural/darker themes)

Note: You can use any color pallette you like for this project. These are just the two I picked, and also in case anyone is wondering what type of code to write when using custom color pallettes.
    
## Notes
  • Environment: This code was originally developed for the Kaggle environment. If running locally, update the file paths in pd.read_csv() to match your local directory structure.
  
  • Warnings: All pandas/matplotlib warnings are suppressed to keep the output clean.
  
  • Data Integrity: The script includes basic .info(), .describe(), and .isna().sum() checks before processing.
  
## License
This analysis script is provided for educational and operational review purposes.

## Contributing
To extend this analysis:

  • Add correlation heatmaps between attendance and admission rates.
    
  • Implement statsmodels OLS regression to predict bed demand based on historical trends.
    
  • Create interactive dashboards using plotly.
