# Overall Workplace Satisfaction Score

## Project Overview

This Power BI project is a comprehensive comparative analysis of employee satisfaction surveys conducted across two academic years (2021/22 and 2023/24) for **AGH University of Science and Technology**.

The report focuses on workplace satisfaction, IT infrastructure reliability, software innovation, and hybrid work capabilities.

**Disclaimer:** This project is a portfolio demonstration based on real-world requirements. To ensure data privacy and confidentiality, **all data has been fully anonymized**. The department names (e.g., WAiAP, WMN, WSS) are randomized placeholders, and the specific survey questions have been modified.

#### Report: [overall_workplace_satisfaction_score.pdf](https://github.com/user-attachments/files/23671922/overall_workplace_satisfaction_score.pdf)

## Dynamic Logic Demonstration

The animation below demonstrates the report's ability to dynamically recalculate insights based on the selected department. Notice how the Executive Summary text updates automatically, only displaying metrics that meet specific statistical criteria.

![PBIDesktop_FgXcEghycr](https://github.com/user-attachments/assets/b2d022b4-88c6-411b-a84a-acce923fa4bd)

## Business Requirements & Solutions

The primary stakeholder requirement was the ability to generate specific, high-level PDF reports for **each individual department** (Faculty) without manually recreating the report for every unit.

To achieve this, I implemented advanced logic within Power BI:

### 1. Automated Executive Summary (Smart Text)
The "Executive Summary" page writes itself based on the data context. It calculates the percentage change between the two audit periods and generates a sentence describing the trend.

**The Logic & Criteria:**
To ensure statistical relevance and avoid cluttering the report with insignificant fluctuations, I implemented complex DAX logic. A metric is only included in the summary if it meets **both** of the following conditions:
*   **Significance Threshold:** The percentage change (positive or negative) must be **greater than or equal to 5%**.
*   **Data Quality Control:** The sample size (N) must be **at least 30 respondents** in *both* the 2021/22 and 2023/24 surveys.

If a specific metric does not meet these criteria for the selected department, it is automatically excluded from the text summary.

### 2. Dynamic Contextual Highlighting
Instead of filtering the charts (which would remove the context of how a department performs compared to others), the report uses dynamic conditional formatting.
*   **The Solution:** When a specific department is selected for the report, its corresponding bar in the charts is highlighted in **Brown**, while all other departments remain in the background **Blue**. This allows stakeholders to see their specific performance ranking within the wider university context.

## Report Structure

The report is designed for export to PDF and includes:

*   **Page 1:** Title & Scope.
*   **Page 2:** Dynamic Executive Summary (Auto-generated text insights).
*   **Pages 3-8:** Detailed Visualizations comparing the two periods on:
    *   Overall Workplace Satisfaction.
    *   Innovation Rating of Software & Tools.
    *   Reliability of Corporate Equipment (Hardware).
    *   Availability of Meeting Spaces.
    *   Video Conferencing & Hybrid Work Quality.
    *   Network Stability & VPN Access.
*   **Pages 9-13 (Appendix):** Transparency data showing the exact research sample size for every department per question, ensuring the viewer understands the statistical weight of the scores.

## Tools & Technologies

*   **Microsoft Power BI Desktop**
*   **DAX (Data Analysis Expressions):** Used for calculating weighted averages, percentage changes, dynamic color coding logic, and generating the conditional text strings for the Executive Summary.
*   **Power Query (M):** Used for data cleaning and shaping the survey results for analysis.

## Key Skills Demonstrated

*   **Data Storytelling:** Transforming raw survey data into actionable insights regarding IT infrastructure and employee sentiment.
*   **Advanced DAX:** Creating dynamic text measures and conditional formatting rules based on slicer selection.
*   **Statistical Awareness:** Implementing filters to exclude statistically insignificant data (N < 30) from the executive summary.
*   **User-Centric Design:** Designing for specific stakeholder needs (individualized department reports).
