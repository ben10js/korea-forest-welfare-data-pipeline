# Korea Forest Welfare Data Pipeline

## Overview
This project was developed to construct a comprehensive dataset for the "2025 Forestry Welfare In-depth Evaluation," aimed at identifying regional service gaps in Korea. It integrates fragmented spatial data from 11 different government ministries, which were originally stored in disparate and often unstructured formats like HWP and PDF. By combining Python-based data processing pipelines with AI-assisted preprocessing, specific facility information was standardized and mapped to administrative districts (Si/Gun/Gu) for policy analysis.

## Data
- **Source**: Public data from 11 Government Ministries (e.g., 산림청, 환경부).
- **Input**: 
  - Structured Excel files (`.xlsx`) containing facility lists and budgets.
  - Unstructured documents (HWP, PDF) converted into structured data using AI tools.
- **Contents**: 
  - Spatial locations (addresses) of forestry welfare facilities (Recreation Forests, Healing Forests, etc.).
  - Operational statistics including visitor counts, budget execution, and facility dimensions (2015-2025).
- **Output**: A unified master dataset aggregating facility counts and types by administrative district.

## Methods
- **AI-Assisted Processing**: Used **AI tools (e.g., NotebookLM)** to help convert unstructured government documents (HWP, PDF) into structured tables, while manually reviewing and correcting the outputs.
- **Data Engineering (ETL)**: Used `pandas` and `numpy` to extract data from multi-sheet Excel files and normalize inconsistent column headers.
- **Address Parsing & Standardization**: Implemented robust string processing logic to parse non-standard Korean addresses into standardized administrative units (Si/Gun/Gu) for accurate spatial aggregation.
- **Integration Logic**: Merged heterogeneous datasets based on location and facility type keys to create a single source of truth.

## Results
- **Unified Database**: Successfully consolidated over 10 years of dispersed forestry welfare data into a single analytical dataset.
- **Spatial Coverage**: Achieved 100% mapping of facilities to administrative districts, enabling precise regional inequality analysis.
- **Efficiency**: Significantly reduced manual data entry time by automating the parsing of irregular address formats and utilizing AI for unstructured text.

## How to run
1. **Environment Setup**:
   - Python 3.x
   - Jupyter Notebook

2. **Required Packages**:
   ```bash
   pip install pandas numpy openpyxl
   ```

3. **Execution Order**:
   1. Place the raw Excel files (e.g., `기관_시군구.xlsx`) in the `data/raw/` directory.
   2. Run `notebooks/01_data_extraction_and_mapping.ipynb` to extract facility lists and perform initial administrative mapping.
   3. Run `notebooks/02_address_parsing_and_merging.ipynb` to parse detailed addresses and merge visitor/budget statistics.

## What I learned
- **Handling Real-World Data**: Gained practical experience in cleaning "dirty data," specifically dealing with inconsistent address standards and missing values common in public aggregate data.
- **Hybrid AI Workflows**: Discovered the efficiency of combining traditional programming (Python) with modern AI tools (NotebookLM) to handle unstructured data that is difficult to process with code alone.
- **Data Modeling for Policy**: Understood how to design data schemas that align with specific policy evaluation metrics, such as distinguishing between National, Public, and Private operating entities.
