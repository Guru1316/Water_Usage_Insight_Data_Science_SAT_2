# 💧 Water Usage Insight
### Smart Water Consumption Analysis & Intelligence Platform

**DS Sprint Assessment | Challenge ID 19 | Data Science Project**

Water Usage Insight is a data analytics and decision-support project developed under the **AquaTrack Utilities** concept. It analyzes water consumption patterns, identifies unusual meter readings, examines relationships between water usage and weather, compares usage before and after maintenance, and explores machine learning for daily water-usage prediction.

The project transforms raw, synthetic water-utility datasets into structured analytical outputs, visualizations and actionable recommendations.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Objectives](#-objectives)
- [Key Features](#-key-features)
- [Project Workflow](#-project-workflow)
- [Dataset Description](#-dataset-description)
- [Technology Stack](#-technology-stack)
- [Project Structure](#-project-structure)
- [Installation and Setup](#-installation-and-setup)
- [Implementation Details](#-implementation-details)
- [Spike Analysis](#-spike-analysis)
- [Machine Learning Approach](#-machine-learning-approach)
- [Visualizations and Excel Analysis](#-visualizations-and-excel-analysis)
- [Key Findings](#-key-findings)
- [Generated Outputs](#-generated-outputs)
- [Business Recommendations](#-business-recommendations)
- [Limitations](#-limitations)
- [Future Enhancements](#-future-enhancements)
- [Conclusion](#-conclusion)

---

## 🔍 Overview

Water utilities collect large volumes of consumption data from meters, customer connections, billing systems, weather observations and maintenance records.

Analyzing these records separately makes it difficult to understand consumption patterns, identify unusual readings and prioritize investigations.

**Water Usage Insight** addresses this challenge through a structured data science workflow involving:

- Synthetic dataset generation.
- Data quality assessment and preprocessing.
- Integration of related datasets.
- Exploratory Data Analysis (EDA).
- Feature engineering.
- Statistical spike detection.
- Water-usage trend analysis.
- Before-and-after maintenance comparisons.
- Machine-learning experimentation.
- Visualization and Excel-based business analysis.

The project demonstrates how data analytics can support better water-resource management decisions.

> **Project type:** Academic data science prototype using synthetic data.

---

## 🎯 Problem Statement

Water utilities need a reliable way to understand consumption patterns and identify readings that may require further investigation. Raw meter readings alone do not provide sufficient context to compare localities, study changes over time or evaluate consumption around maintenance activities.

The objective of Water Usage Insight is to transform water-consumption records into meaningful insights that support anomaly investigation, demand analysis, maintenance evaluation and conservation planning.

---

## 🎯 Objectives

1. Generate related synthetic datasets representing a water utility environment.
2. Assess data quality and handle missing, duplicate, invalid and inconsistent records.
3. Integrate meter readings with connection, weather and maintenance information.
4. Analyze consumption by locality, connection type and month.
5. Examine linear relationships between water usage, temperature and rainfall.
6. Identify unusually high meter readings using statistical screening.
7. Compare water usage before and after recorded repairs.
8. Prepare features for machine-learning experimentation.
9. Communicate findings through charts, summary tables and Excel analysis.
10. Recommend practical actions based on the observed patterns.

---

## ✨ Key Features

### 1. Synthetic Dataset Generation

Uses generated utility-style records to simulate meter readings, customer connections, billing cycles, weather observations and maintenance activities.

### 2. Data Quality Assessment

Examines dataset dimensions, column types, missing values, duplicate records and distinct values.

### 3. Data Preprocessing

Standardizes connection IDs and categories, converts date fields, handles invalid usage values and removes duplicate records according to the implemented rules.

### 4. Dataset Integration

Combines relevant meter, connection, weather and maintenance information to create an integrated daily analysis table.

### 5. Exploratory Data Analysis

Summarizes water usage across localities, connection types and months.

### 6. Spike Analysis

Uses a connection-level statistical baseline to flag unusually high readings for further investigation.

### 7. Maintenance Analysis

Compares average usage in defined windows before and after recorded repairs.

### 8. Feature Engineering

Derives time-related variables and prepares numerical and categorical features for further analysis.

### 9. Machine-Learning Experimentation

The project presentation reports an exploratory Random Forest Regression evaluation for estimating daily water usage.

### 10. Visualization and Reporting

Generates PNG charts and CSV summaries for further inspection, including Excel-based analysis.

---

## 🔄 Project Workflow

```text
Synthetic Dataset Generation
            |
            v
     Five CSV Datasets
            |
            v
   Data Quality Assessment
            |
            v
     Data Preprocessing
            |
            v
    Dataset Integration
            |
            v
      Feature Engineering
            |
            v
 Exploratory Data Analysis
            |
            +----------------------+
            |                      |
            v                      v
      Spike Analysis        Repair Analysis
            |                      |
            +----------+-----------+
                       |
                       v
             Summary Tables & Charts
                       |
                       v
            Machine-Learning Evaluation
                       |
                       v
             Business Recommendations
```

*Note: The Random Forest evaluation is reported separately from the preprocessing and feature-export steps in `round2.py`. The workflow diagram represents the overall project, not a claim that every step is executed by that script.*

---

## 📂 Dataset Description

The project uses five synthetic CSV datasets covering **January to June 2026**.

| Dataset | Records | Attributes | Purpose |
|---|---:|---:|---|
| `meter.csv` | 10,793 | 3 | Daily water meter readings |
| `connections.csv` | 60 | 4 | Connection details and customer categories |
| `billing.csv` | 360 | 3 | Billing-cycle information |
| `weather.csv` | 181 | 3 | Daily weather observations |
| `maintenance.csv` | 6 | 4 | Maintenance and repair records |

*The counts above refer to the original generated datasets, before preprocessing.*

### Dataset Details

#### 1. Meter Dataset

Contains connection-level water consumption observations.

Typical fields include:

- `date`
- `connection`
- `usage_m3`

The `usage_m3` field represents recorded water usage in cubic metres.

#### 2. Connections Dataset

Contains descriptive information about each water connection.

Typical fields include:

- `connection`
- `locality`
- `type`
- `household_size_band`

Connection type distinguishes residential and commercial records.

#### 3. Billing Dataset

Contains billing-cycle information associated with connections.

Typical fields include:

- `connection`
- `billing_cycle`
- `charge`

This dataset is cleaned and exported by the preprocessing pipeline. It is not merged into the daily analysis table by the current `round2.py` implementation.

#### 4. Weather Dataset

Contains daily environmental observations.

Typical fields include:

- `date`
- `temperature`
- `rain`

These variables are used to explore relationships between weather and water usage.

#### 5. Maintenance Dataset

Contains maintenance-related records.

Typical fields include:

- `connection`
- `repair_date`
- `leak_report`

The maintenance data supports matched repair comparisons and connection-level maintenance features.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Main implementation language |
| Pandas | Data manipulation, integration and aggregation |
| NumPy | Numerical operations and missing-value handling |
| Matplotlib | Chart generation |
| Seaborn | Statistical visualization |
| Scikit-learn | Random Forest regression evaluation in the modelling workflow |
| Microsoft Excel / LibreOffice Calc | PivotTables, PivotCharts and manual analysis |
| Git and GitHub | Version control and project sharing |
| VS Code | Development environment |

---

## 📁 Project Structure

The project is organized as a Python-based data analysis workflow.

```text
Water_Usage_Insight/
│
├── data/
│   ├── meter.csv
│   ├── connections.csv
│   ├── billing.csv
│   ├── weather.csv
│   └── maintenance.csv
│
├── outputs/
│   ├── data_structure_summary.csv
│   ├── initial_quality_audit.csv
│   ├── clean_meter.csv
│   ├── clean_connections.csv
│   ├── clean_billing.csv
│   ├── clean_weather.csv
│   ├── clean_maintenance.csv
│   ├── analysis_daily.csv
│   ├── usage_descriptive_statistics.csv
│   ├── usage_by_locality.csv
│   ├── usage_by_connection_type.csv
│   ├── monthly_usage_by_type.csv
│   ├── weather_usage_correlations.csv
│   ├── detected_usage_spikes.csv
│   ├── before_after_repair.csv
│   ├── engineered_feature_matrix.csv
│   ├── feature_correlation_screening.csv
│   ├── unmatched_maintenance_records.csv
│   ├── usage_by_locality.png
│   ├── usage_by_connection_type.png
│   ├── usage_vs_temperature.png
│   ├── usage_vs_rainfall.png
│   ├── monthly_usage_trend.png
│   └── before_after_repair.png
│
├── round2.py
├── requirements.txt
└── README.md
```

The output filenames listed above correspond to the current implementation. Files are created when their respective code sections run successfully. Other assessment materials, such as the Excel workbook, presentation and notebook, may be maintained separately.

---

## ⚙️ Installation and Setup

### Prerequisites

Install the following:

- Python 3.10 or a compatible version supported by the project's dependencies.
- Visual Studio Code.
- Python extension for VS Code.
- The five required CSV datasets.

### Step 1: Clone the Repository

Replace the placeholder with your actual GitHub repository URL.

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd Water_Usage_Insight
```

Alternatively, download the repository as a ZIP file and extract it.

### Step 2: Create a Virtual Environment

**Windows:**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**Linux / macOS:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### Step 3: Install Dependencies

Create a `requirements.txt` file containing:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
```

Install the dependencies:

```bash
python -m pip install -r requirements.txt
```

### Step 4: Verify the Dataset Files

Ensure the following files exist inside the `data/` folder:

```text
meter.csv
connections.csv
billing.csv
weather.csv
maintenance.csv
```

The script expects the filenames and relevant column names used in its implementation.

### Step 5: Run the Python Script

```bash
python round2.py
```

The script reads the datasets from `data/`, processes them, generates summary tables and charts, and saves its outputs under `outputs/`.

### Step 6: Inspect the Results

Open the generated CSV files using Excel, LibreOffice Calc or a text editor.

Open the PNG files to view the charts.

If the script reports a missing file or column, verify the folder structure and dataset schema before rerunning it.

---

## 🧹 Implementation Details

### 1. Data Quality Assessment

The script examines:

- Number of rows and columns.
- Data types.
- Missing values.
- Unique values.
- Exact duplicate rows.

The audit outputs provide a baseline for understanding the quality of the original datasets.

### 2. Data Preprocessing

The current implementation includes:

- Date conversion using Pandas datetime functions.
- Standardization of connection IDs.
- Standardization of residential and commercial labels.
- Removal of exact duplicate meter rows.
- Conversion of negative usage values to missing values.
- Exclusion of meter records without valid dates, connection IDs or usage.
- Aggregation of repeated connection/date records using mean usage.
- Numeric conversion and validation of weather and billing fields.
- Separation of unmatched maintenance records.

These rules make the data more consistent for subsequent analysis.

### 3. Dataset Integration

Meter readings are joined with connection details using the connection ID and with weather observations using the date.

Maintenance features are also attached to the analysis table.

The resulting dataset is exported as:

```text
outputs/analysis_daily.csv
```

The presentation reports **10,742 integrated analysis rows**.

### 4. Feature Engineering

The current feature-engineering pipeline creates variables such as:

- Month.
- Month name.
- Day of the week.
- Weekend indicator.
- Year-month identifier.
- Days from repair.
- Estimated household size.
- Estimated usage per household member.

Categorical fields such as locality and connection type are encoded using one-hot encoding.

The resulting feature table is saved as:

```text
outputs/engineered_feature_matrix.csv
```

This output prepares the data for modelling but does not, by itself, train a predictive model.

### 5. Exploratory Data Analysis

The project calculates descriptive statistics and aggregates usage by locality, connection type and month.

It also calculates Pearson correlations between water usage, temperature and rainfall.

These analyses help identify patterns that may warrant further investigation.

---

## 📈 Spike Analysis

Spike Analysis identifies unusually high readings compared with a connection's observed usage pattern.

The current implementation calculates a connection-level median and standard deviation, then derives a score:

\[
z = \frac{x-\text{median usage}}{\text{standard deviation}}
\]

where:

- \(x\) is the observed water usage.
- Median usage is the connection's median across its available readings.
- Standard deviation measures the spread of the connection's readings.

The implemented rule flags a reading when:

\[
z \geq 3
\]

Flagged records are sorted by their score and exported to:

```text
outputs/detected_usage_spikes.csv
```

### Why Spike Analysis Matters

Unusually high readings may be associated with:

- Unexpected consumption.
- Potential leakage.
- Meter malfunction.
- Data-entry problems.
- Changes in usage patterns.

The flag is a screening signal, not a diagnosis. Every flagged record requires further investigation before a leak or other issue can be confirmed.

---

## 🤖 Machine-Learning Approach

The project presentation reports an exploratory **Random Forest Regressor** for estimating daily water usage.

### Objective

Predict a continuous numerical value:

`usage_m3`

### Selected Features

The reported model uses inputs such as:

- Connection type.
- Locality.
- Household-size category.
- Temperature.
- Rainfall.
- Month.
- Weekday.

### Why Random Forest?

Random Forest combines predictions from multiple decision trees. It can capture nonlinear relationships and interactions among input variables without requiring a single linear equation.

It is a reasonable baseline for tabular regression data.

### Reported Model Performance

The presentation reports the following results:

| Metric | Reported Value |
|---|---:|
| Mean Absolute Error (MAE) | 0.309 m³ |
| Root Mean Squared Error (RMSE) | 0.746 m³ |
| R² | 0.829 |
| Train/test split | 80% / 20% |

**Interpretation:**

- **MAE:** The average absolute difference between predictions and observed usage was reported as 0.309 m³.
- **RMSE:** The reported value was 0.746 m³; this metric gives greater weight to larger errors.
- **R²:** The reported score was 0.829, indicating that the model accounted for 82.9% of the variation relative to a mean-prediction baseline on the evaluated test set.

R² is not classification accuracy.

> **Reproducibility note:** These metrics are reported from the project's presentation/previous modelling results. The current `round2.py` preprocessing and feature-export script does not itself instantiate a Random Forest model, perform the train/test split, or calculate these metrics. A separate modelling implementation is required to reproduce them. The synthetic dataset and random split also limit conclusions about future real-world performance.

---

## 📊 Visualizations and Excel Analysis

The Python implementation generates charts that help explain consumption patterns.

| Visualization | Purpose |
|---|---|
| Usage by locality | Compares recorded usage totals across localities |
| Usage by connection type | Examines the distribution of readings across customer categories |
| Usage versus temperature | Explores the relationship between temperature and usage |
| Usage versus rainfall | Explores the relationship between rainfall and usage |
| Monthly usage trend | Shows how monthly totals change over time |
| Before-and-after repair chart | Compares average usage around repair dates |

### Excel-Based Analysis

PivotTables and PivotCharts provide an accessible way to summarize the data.

The assessment workbook includes analyses such as:

- Locality comparison.
- Residential versus commercial usage.
- Weather-related summaries.
- Spike summary and flagged-reading inspection.
- Repair analysis.
- Monthly and peak-period analysis.

These Excel summaries complement the Python workflow by making findings easier to review and present.

---

## 🔎 Key Findings

The following values are reported in the project's presentation and analysis.

### 1. Locality Usage

Lakewood recorded the highest locality total:

**5,885.547 m³**

Northview recorded the lowest locality total:

**382.0 m³**

Lakewood is a useful starting point for a detailed consumption review. However, locality totals should be interpreted alongside the number of connections and observations.

### 2. Residential vs. Commercial Usage

| Connection Type | Recorded Total |
|---|---:|
| Commercial | 10,810.887 m³ |
| Residential | 5,724.787 m³ |

Commercial connections account for the larger recorded total. This does not establish that commercial customers waste more water per customer, because connection counts and consumption requirements may differ.

### 3. Weather Relationships

| Variable | Reported Correlation with Usage |
|---|---:|
| Temperature | +0.063 |
| Rainfall | −0.025 |

Both correlations are close to zero, indicating very weak linear associations in the generated dataset.

These results do not establish causal relationships and do not rule out nonlinear effects.

### 4. Unusual Readings

The analysis reported:

- 36 flagged readings.
- Combined recorded usage of 187.632 m³ across those records.

These readings require verification; they are not 36 confirmed leaks.

### 5. Repair Comparison

Across five matched repair windows, the presentation reports:

| Measure | Average Usage |
|---|---:|
| Before repair | 0.767 m³ |
| After repair | 0.591 m³ |
| Mean percentage change | −23.6% |

The comparison is consistent with lower recorded usage after repair. It does not prove that repair caused the change.

### 6. Monthly Demand

| Month | Recorded Total |
|---|---:|
| February 2026 | 2,378.565 m³ |
| June 2026 | 2,978.466 m³ |

February was the lowest month and June the highest in the reported six-month analysis period.

The trend should be checked against longer-term data before making operational forecasts.

---

## 💡 Business Recommendations

Based on the observed patterns, the project recommends:

1. **Prioritize inspections:** Begin with localities and connections that warrant closer investigation based on their usage patterns.
2. **Review commercial accounts:** Investigate high-use accounts for practical water-efficiency opportunities.
3. **Verify unusual readings:** Check flagged records against meter histories, maintenance records and leak reports.
4. **Monitor repairs:** Continue comparing consumption after maintenance to understand whether changes persist.
5. **Promote conservation:** Use verified usage patterns to guide targeted conservation communication.
6. **Improve data quality:** Resolve unmatched maintenance IDs and maintain consistent records across systems.
7. **Validate the model:** Evaluate predictive performance on future observations and real utility records before deployment.

These recommendations are intended to support human decision-making rather than replace technical inspections.

---

## ⚠️ Limitations

The current project has several limitations:

- **Synthetic data:** The records are generated for an academic demonstration and are not verified real-world utility observations.
- **Limited time period:** The dataset covers six months, which is insufficient to establish long-term seasonal behaviour.
- **Anomaly screening:** Statistical flags do not confirm leakage or meter failure.
- **Repair comparisons:** Before-and-after differences do not establish causation.
- **Correlation analysis:** Weak linear correlations do not exclude nonlinear relationships or other contributing variables.
- **Model evaluation:** The reported random train/test split does not establish performance on future time periods.
- **Feature validation:** The final modelling pipeline must exclude target-derived features and prevent data leakage.
- **Deployment readiness:** The project does not currently establish production-grade monitoring, operational integration or automated leak diagnosis.

---

## 🚀 Future Enhancements

Potential improvements include:

- Integrating real, appropriately anonymized water-utility records.
- Adding time-based training and evaluation splits.
- Comparing Random Forest with Linear Regression, Decision Tree Regression and Gradient Boosting.
- Improving anomaly detection with robust statistical methods and domain-specific thresholds.
- Validating unusual readings against confirmed maintenance outcomes.
- Improving repair analysis with more historical records and appropriate controls.
- Developing an interactive dashboard with locality, date and connection filters.
- Adding automated reporting and alerts for verified high-priority readings.
- Tracking actual conservation outcomes during a monitored pilot.

These are future enhancements, not claims about features already implemented.

---

## 🏁 Conclusion

Water Usage Insight demonstrates how data preprocessing, exploratory analysis, statistical screening, machine-learning experimentation and visualization can transform synthetic water-consumption records into useful analytical findings.

The project identifies differences across localities and connection types, highlights unusual readings for investigation, explores repair-related usage changes and summarizes monthly demand.

Its main contribution is a structured decision-support workflow that helps prioritize further investigation and conservation opportunities. Validation with real utility data is the next step toward establishing its practical value.

---

## 👨‍💻 Development Environment

- **IDE:** Visual Studio Code
- **Language:** Python
- **Data format:** CSV
- **Analysis:** Pandas and NumPy
- **Visualization:** Matplotlib and Seaborn
- **Reporting:** Excel / LibreOffice Calc
- **Version control:** Git and GitHub

## 📄 License

Choose and add a license appropriate for your project before publishing or distributing the repository.

## 🙌 Acknowledgements

Developed as part of the DS Sprint assessment to demonstrate practical data science techniques for water-consumption analysis and decision support.

**Water Usage Insight — Turning Water Data into Actionable Insights.** 💧