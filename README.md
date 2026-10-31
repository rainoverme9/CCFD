# Credit Card Fraud Analysis with Neo4j

A university project developed for the **New Generation Data Models and DBMS** course at the **University of Milan**. The project explores how a **graph database** can represent and analyze synthetic credit-card transactions, including fraudulent activity, using **Neo4j** and **Cypher**.

The work covers dataset simulation, graph modeling, CSV data import, analytical queries, and performance evaluation across three dataset sizes.

> **Scope:** This is a database design and analysis project, **not** a trained machine-learning fraud classifier. All transaction data is synthetic.

## Project Overview

- **Data generation:** Simulate customers, payment terminals, and transactions with geographic and spending characteristics; assign fraud labels using three predefined scenarios.
- **Graph model:** Represent customers and terminals as nodes, and transactions as relationships carrying amounts, timestamps, and fraud labels.
- **Neo4j implementation:** Import CSV data using Cypher and APOC, with indexes and batched transaction loading.
- **Graph queries:** Explore customer similarities, transaction anomalies, multi-hop customer connections, and enriched graph relationships.
- **Performance analysis:** Compare loading and query execution times on datasets of increasing size.

## Technologies

**Python · Jupyter Notebook · Neo4j · Cypher · APOC · Pandas · NumPy**

## Graph Data Model

The graph represents each transaction as a directed `MAKE_TRANSACTION` relationship from a `Customer` node to a `Terminal` node, storing the transaction identifier, timestamp, amount, and fraud label as relationship properties.

The graph is further extended with additional transaction attributes and a `BUYING_FRIENDS` relationship based on shared terminals and customer behavior.

## Datasets

The project uses three synthetic datasets, each with 2,000 customers and 350 payment terminals.

| Dataset | Period | Transactions |
|---|---:|---:|
| 50 MB | 90 days | 315,861 |
| 100 MB | 180 days | 631,830 |
| 200 MB | 365 days | 1,280,958 |

Dataset sizes refer to approximate in-memory usage.

The repository includes the 50 MB dataset as an example. Larger datasets can be regenerated from the notebook.

## Project Structure

- `Credit_Card_Fraud_Analysis.ipynb` — Dataset simulation, graph import, and Cypher queries.
- `dataset50MB/` — Sample synthetic CSV dataset.
- `docs/Project_Report.pdf` — Full technical report.
- `docs/Project_Presentation.pdf` — Project presentation.
- `requirements.txt` — Python dependencies.
- `.env.example` — Example Neo4j connection configuration.

## Getting Started

1. Install Python and configure a local Neo4j database with the APOC plugin enabled.
2. Install the dependencies using `python -m pip install -r requirements.txt`.
3. Copy `.env.example` to `.env` and enter the local Neo4j credentials.
4. Copy the provided CSV files into Neo4j's configured import directory.
5. Launch Jupyter Lab and open `Credit_Card_Fraud_Analysis.ipynb`.
6. Execute the connection, import, and analysis sections.

The original project used Neo4j 5 and APOC 5. Some queries depend on the current date and may require adjusting their time window to match the generated dataset.

## Documentation

The complete methodology, database design, Cypher queries, performance measurements, and results are available in the accompanying project report and presentation in the [Project Presentation](docs/CCFD.pdf).

## Authors

**Elisa Campana and Elena Mazzilli**

## References

Synthetic transaction generation methodology based on the [Fraud Detection Handbook — Simulated Dataset](https://frauddetectionhandbook.github.io/frauddetectionhandbook/Chapter_3_GettingStarted/SimulatedDataset.html).

## Academic Context

Developed as a university project for the **New generation data modela and DBMSs** course at the University of Milan.