# TP Spark Core : NYC Taxi Data Factory

Pipeline Lakehouse (architecture Medallion Bronze / Silver / Gold) sur les trajets des taxis jaunes de New York, année **2025** (janvier, avril, juillet, octobre), avec PySpark et Delta Lake en local.

Tout le TP est dans un seul notebook : [`notebooks/TP_Spark_Core_IME.ipynb`](notebooks/TP_Spark_Core_IME.ipynb), avec une section par séance.

## Arborescence

```
tp_spark_core/
  requirements.txt
  data/
    raw/          fichiers source (non versionnés, à télécharger)
    bronze/       bronze_trips (Delta)
    silver/       silver_trips (Delta)
    gold/         gold_borough, zones_clusters (Delta)
    quarantine/   quarantine_trips (Delta)
  notebooks/
    TP_Spark_Core_IME.ipynb
```

Les dossiers `data/` ne sont pas versionnés (plusieurs Go) : les tables Delta sont régénérées par le notebook.

## Installation

Prérequis : Java 17 et Python 3.11.

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Données

Depuis le portail [NYC TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page), déposer dans `data/raw/` :

- `yellow_tripdata_2025-01.parquet`
- `yellow_tripdata_2025-04.parquet`
- `yellow_tripdata_2025-07.parquet`
- `yellow_tripdata_2025-10.parquet`
- `taxi_zone_lookup.csv`

## Exécution

Ouvrir le notebook avec le kernel `.venv`, depuis le dossier `notebooks/` (tous les chemins commencent par `../data/`), puis tout exécuter.
