# Temporal Risk Identification & Behavioural Insight Mining in Mental Health

> **A scalable Apache Spark + PostgreSQL pipeline for predicting employee mental health risk using temporal and behavioural indicators.**

---

## Overview

A cloud-integrated big data pipeline that processes a 200,000+ record mental health survey dataset to identify when and why workplace mental health interventions should be prioritised. Raw data flows from **Azure Blob Storage** → **Apache Spark (PySpark)** → **PostgreSQL** → **Visualisation**, running as a fully automated end-to-end pipeline.

---

## Tech Stack

| Component | Technology |
|---|---|
| Distributed Processing | Apache Spark (PySpark) |
| Cloud Storage | Microsoft Azure Blob Storage |
| Database | PostgreSQL (via JDBC) |
| Environment | Google Colab |
| Visualisation | Matplotlib, Seaborn, Plotly, Tableau |

---

## Pipeline Architecture

```
Azure Blob Storage (raw CSV)
        │
        ▼
Apache Spark (PySpark)
  - Schema validation & imputation
  - Categorical encoding
  - Feature engineering
        │
        ▼
PostgreSQL (structured storage via JDBC)
        │
        ▼
Pandas + Plotly/Seaborn (visualisation & insights)
```

Single-click execution — running all notebook cells triggers the full ETL pipeline automatically.

---

## Key Findings

- Treatment-seeking behaviour peaks during **late evenings and weekends**, suggesting interventions should be scheduled outside standard work hours
- **Days spent indoors** is the strongest behavioural predictor of mental health treatment need
- **STL decomposition** reveals consistent weekly seasonality in treatment trends, enabling resource planning
- Growing stress shows irregular spikes aligned with seasonal or workload cycles

---

## Dataset

- **Source:** [Kaggle Mental Health Dataset](https://www.kaggle.com/) — ~200,000 anonymised records
- **Key Features:** Age, Gender, Treatment Status, Employer Support, Days Indoors, Growing Stress, Coping Struggles, Mood Swings, Social Weakness, Risk Score

> The dataset is not included in this repository. Download from Kaggle and upload to your Azure Blob container, then update the connection config in the notebook.

---

## Getting Started

### Prerequisites

```bash
pip install pyspark psycopg2-binary pandas matplotlib seaborn plotly
```

You will also need:
- An **Azure Blob Storage** account and container
- A running **PostgreSQL** instance
- The **PostgreSQL JDBC driver** JAR (configured in the Spark session)

### Running the Pipeline

1. Upload the dataset CSV to your Azure Blob container
2. Update the Azure connection credentials and PostgreSQL JDBC URL in the notebook
3. Open `Behavioural_Insight_Mining_in_Mental_Health_Code.ipynb` in Google Colab
4. Click **Run All** — the full pipeline executes automatically

---
