# 2024-03 Data Science for Himalayan Climbing Success

This project applies **data science** and **machine learning** techniques to analyze mountaineering records from **The Himalayan Database**, identifying key factors influencing summit success and providing actionable recommendations for climbers and related stakeholders.  
Developed entirely in **R (tidyverse)**, the project includes data cleaning, modeling, visualization, and result analysis.  
All analyses and figures are generated directly from the `.Rmd` source file, ensuring a **fully reproducible workflow**.

📄 **中文版说明**: [`README.zh.md`](README.zh.md)  
🧾 **Project Proposal**: [`01_Project_Proposal.pdf`](reports/01_Project_Proposal.pdf)  
📊 **Project Report (Main)**: [`02_Project_Report.pdf`](reports/02_Project_Report.pdf)  
🎞 **Project Presentation Slide**: [`03_Project_Presentation_Slide.pdf`](reports/03_Project_Presentation_Slide.pdf)

---

## 🎯 Project Objectives

1. Identify and quantify the key factors influencing summit success in Himalayan mountaineering;  
2. Provide data-driven recommendations for climbers and related organizations to enhance safety and preparation;  
3. Contribute to the broader understanding of high-altitude activities through data science.

---

## 🧩 Project Structure

```plaintext
├── 01_data/
│   ├── Himalayan_Database.zip       # Original database (contains 4 DBF data tables)
│   ├── peaks.csv                    # Peak information data
│   ├── exped.csv                    # Expedition-level data
│   ├── members.csv                  # Climber-level data
│   └── refer.csv                    # Reference index data
│
├── 02_src/
│   ├── 01_Project_Report_Source_Code.Rmd     # R Markdown source code (used to knit the report)
│   └── 02_Project_References.bib             # Bibliography file for citations in the report
│
├── 03_reports/
│   ├── 01_Project_Proposal.pdf               # Project proposal 
│   ├── 02_Project_Report.pdf                 # Main project report (generated from .Rmd)
│   └── 03_Project_Presentation_Slide.pdf     # Presentation slides
│
├── 04_pictures/                              # Supplementary images (not used in knitting)
│
├── 05_resources/
│   ├── 01_Appendix J - SQL Searches.pdf      # Official example SQL search queries for The Himalayan Database
│   └── 02_Himalayan Database Guide.pdf       # User guide and data access documentation for The Himalayan Database
│
├── LICENSE                                  # MIT License
│
├── README.md                                # English version
└── README.zh.md                             # Chinese version
```

## 🔍 Data and Methods

- **Data Source**: [The Himalayan Database](https://www.himalayandatabase.com)  
- **Data Size**: ~85,000 mountaineering records (1905–2023)  
- **Languages and Tools**: R, tidyverse, ggplot2, randomForest  
- **Modeling Method**: Random Forest (classification)  
- **Evaluation Metrics**: Accuracy = 0.84, AUC = 0.919  
- **Report Generation**:  
  The report and all visualizations are **automatically generated from the `.Rmd` file**, ensuring end-to-end reproducibility.

---

## 🧠 Workflow Overview

1. **Data Preprocessing** – cleaning and merging the peaks, expeditions, and members datasets  
2. **Feature Engineering** – renaming, missing value handling, and feature selection  
3. **Model Building & Tuning** – applying Random Forest with hyperparameter tuning using `tuneRF()`  
4. **Model Evaluation** – assessing model performance with accuracy and ROC-AUC metrics  
5. **Visualization** – producing feature importance plots and success rate distribution charts  

---

## 📊 Key Findings

| Key Feature | Insight |
|--------------|----------|
| **Oxygen Usage Level (`level_oxygen_usage`)** | The most influential factor; moderate oxygen use greatly increases summit success. |
| **Team Size (`n_team_members`)** | Medium-sized teams (2–10 members) achieve the highest success rate. |
| **Commercial Route (`if_commercial_route`)** | Commercial routes have overall higher success rates than non-commercial routes. |

---

## 🔧 Standards and Governance

- **Data Science Process**: CRISP-DM framework  
- **Data Governance & Ethics**: Privacy protection, anonymized data, and transparent analytical processes  
- **Development Environment**:  
  - R ≥ 4.3  
  - Key libraries: `tidyverse`, `randomForest`, `ggplot2`  
- **Reproducibility**: The entire project report is knitted directly from the `.Rmd` source file, ensuring consistent, reproducible analysis.

---

## 📚 References

Salisbury, R., Hawley, E., & Bierling, B. (2021). *The Himalaya by the Numbers: A Statistical Analysis of Mountaineering in the Nepal Himalaya, 1950–2019.*  
Salisbury, R. (2023). *Program Guide for Windows, Himal 2.6.*  
Tene, O., & Polonetsky, J. (2021). *Big Data Ethics: Balancing Risk and Innovation.* Wiley.

---

## 📜 License

This project is distributed under the [MIT License](LICENSE).

---

*Project completed as part of FIT5145: Foundations of Data Science at the Monash University, Semester 1, 2024.*
