# Citi Bike Demand Forecasting Pipeline

## Overview
This project implements an end-to-end machine learning pipeline to forecast Citi Bike ride demand at the station level using historical trip data. The workflow demonstrates a complete, production-oriented data science lifecycle, covering data ingestion, validation, transformation, feature engineering, modeling, evaluation, and automated training and inference pipelines. Both classical time-series models and modern machine learning approaches are explored to provide a comprehensive comparison of forecasting strategies.

---

## Data Ingestion and Processing
The pipeline begins by downloading monthly Citi Bike trip data from the official AWS S3 repository. Raw CSV files are extracted, loaded into pandas DataFrames, and converted into Parquet format for efficient storage and processing. The data is then validated and cleaned by parsing timestamps, computing trip durations, filtering unrealistic or invalid records, handling missing values, and selecting high-activity pickup locations. The resulting cleaned datasets are saved for downstream analysis and modeling.

---

## Time-Series Transformation and Feature Engineering
Validated ride data is aggregated into station-level time-series representations to capture temporal demand patterns. These time-series datasets are transformed into supervised learning formats by generating lag-based features, rolling statistics, and temporal indicators aligned with future demand targets. Multiple feature engineering strategies are implemented, including pipelines derived directly from raw trip data and from aggregated time-series data, enabling experimentation with different modeling assumptions and data representations.

---

## Modeling and Evaluation
The project establishes baseline forecasting models to provide interpretable performance benchmarks. Advanced machine learning models, including XGBoost and LightGBM, are then trained using engineered features to capture non-linear relationships and complex temporal patterns. Feature-enhanced and hyperparameter-tuned variants are evaluated using standard regression metrics such as Mean Absolute Error (MAE). Additionally, a classical ARMA time-series model is implemented to compare statistical approaches against machine learning-based methods.

---

## Feature Store and Production Pipelines
Engineered features are integrated with a feature store to support reproducibility, versioning, and consistency between training and inference workflows. The project includes automated pipelines for model training, batch prediction, inference, retraining with newly available data, and prediction retrieval. These components reflect real-world production machine learning practices and demonstrate how forecasting models can be maintained, updated, and deployed in a scalable manner.

---

## Notebook Execution Order (High-Level)
1. Data ingestion and validation  
2. Time-series construction  
3. Feature engineering and target creation  
4. Visualization and exploratory analysis  
5. Baseline model training  
6. Advanced machine learning models  
7. Hyperparameter tuning and evaluation  
8. Feature store integration  
9. Training, inference, and retraining pipelines  
10. Performance analysis and visualization  

---

## Notes
- Large datasets are stored locally and are not tracked in Git.
- Notebooks are designed to be executed sequentially.
- File paths assume a `data/` directory at the project root.
- Feature store and pipeline components require appropriate credentials and configuration.

---

This project demonstrates a scalable and production-aware approach to demand forecasting using real-world transportation data, combining sound data engineering practices with robust machine learning modeling techniques.
