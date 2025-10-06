# 2024-03 喜马拉雅登山成功率分析与预测

本项目通过对 **The Himalayan Database** 的登山记录进行统计分析与机器学习建模，研究影响登顶成功率的关键因素，并提出优化登山策略的建议。  
项目使用 **R 语言（tidyverse）** 实现，包括数据清洗、建模、可视化与结果分析；所有分析均通过 `.Rmd` 源文件自动生成最终报告，实现 **可复现的分析流程**。  

📄 **英文版说明**：[`README.md`](README.md)  
🧾 **项目提案文件**：[`01_Project_Proposal.pdf`](reports/01_Project_Proposal.pdf)  
📊 **项目报告（主体）**：[`02_Project_Report.pdf`](reports/02_Project_Report.pdf)  
🎞 **项目演示文件**：[`03_Project_Presentation_Slide.pdf`](reports/03_Project_Presentation_Slide.pdf)  

---

## 🎯 项目目标

1. 利用数据科学方法识别影响登山成功率的关键因素；  
2. 为登山者和相关机构提供针对性的准备与安全建议；  
3. 提升登山活动的成功率与安全性，促进高原活动的科学研究。

---

## 🧩 项目结构

```plaintext
├── data/
│   ├── Himalayan_Database.zip       # 原始数据库（含4个DBF数据表）
│   ├── peaks.csv                    # 山峰信息数据
│   ├── exped.csv                    # 登山活动数据
│   ├── members.csv                  # 登山者信息数据
│   └── refer.csv                    # 文献索引数据
│
├── src/
│   ├── 01_Project_Report_Source_Code.Rmd     # 项目报告R Markdown源码（直接knit生成报告）
│   └── 02_Project_References.bib             # 报告中引用的文献文件
│
├── reports/
│   ├── 01_Project_Proposal.pdf               # 项目提案
│   ├── 02_Project_Report.pdf                 # 项目主体报告（由.Rmd自动生成）
│   └── 03_Project_Presentation_Slide.pdf     # 项目展示PPT
│
├── pictures/                                # 报告配图（不参与knit，仅作说明）
│
├── LICENSE                                  # MIT License
│
├── README.md                                # 英文版README
└── README.zh.md                             # 中文版README
```

## 🔍 数据与方法

- **数据来源**：[The Himalayan Database](https://www.himalayandatabase.com)  
- **数据规模**：约 85,000 条登山记录（1905–2023）  
- **语言与工具**：R, tidyverse, ggplot2, randomForest  
- **建模方法**：随机森林（Random Forest）  
- **指标**：Accuracy = 0.84，AUC = 0.919  
- **报告生成方式**：  
  所有分析、图表与结论均由 `.Rmd` 文件直接运行生成，保证了结果的完全可复现性。

---

## 🧠 核心分析流程

1. **数据预处理**：清洗并合并 peaks、exped、members 数据；  
2. **特征工程**：重命名字段、处理缺失值、选择关键特征；  
3. **建模与调参**：使用随机森林模型，通过 `tuneRF()` 自动优化参数；  
4. **模型评估**：基于 Accuracy 与 ROC-AUC 指标；  
5. **结果可视化**：生成特征重要性图、登顶率分布图等图表。

---

## 📊 主要发现

| 关键特征 | 影响 |
|-----------|------|
| **氧气使用水平 (`level_oxygen_usage`)** | 成功率提升最显著；适度使用可显著提高登顶率 |
| **团队人数 (`n_team_members`)** | 适中团队规模（2–10人）成功率最高 |
| **商业路线 (`if_commercial_route`)** | 商业化路线整体成功率更高 |

---

## 🔧 技术与标准

- **数据科学流程**：遵循 CRISP-DM 模型  
- **数据治理与伦理**：确保登山者隐私保护，仅发布匿名化结果  
- **开发环境**：  
  - R ≥ 4.3  
  - 主要依赖库：`tidyverse`, `randomForest`, `ggplot2`  
- **可复现性**：项目报告完全由 `.Rmd` 文件自动生成，确保分析流程一致可重现。

---

## 📚 参考文献

Salisbury, R., Hawley, E., & Bierling, B. (2021). *The Himalaya by the Numbers: A Statistical Analysis of Mountaineering in the Nepal Himalaya, 1950–2019.*  
Salisbury, R. (2023). *Program Guide for Windows, Himal 2.6.*  
Tene, O., & Polonetsky, J. (2021). *Big Data Ethics: Balancing Risk and Innovation.* Wiley.

---

## 📜 License

本项目基于 [MIT License](LICENSE) 开放。

---

*Project completed as part of FIT5145: Foundations of Data Science at the Monash University, Semester 1, 2024.*
