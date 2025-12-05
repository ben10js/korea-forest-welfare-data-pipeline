# Korea Forest Welfare Data Pipeline 🌲

## Project Overview
This project establishes a data engineering pipeline to analyze the spatial distribution of forestry welfare facilities across South Korea. It integrates fragmented data from 11 different government ministries, utilizing AI-assisted workflows to process unstructured formats (HWP, PDF) into a unified dataset for in-depth policy evaluation.

## Key Features
- **AI-Assisted Data Construction**: Leveraged **Google NotebookLM** to convert unstructured government documents into structured CSV/Excel formats, significantly reducing manual data entry time.
- **Geospatial Data Aggregation**: Automated the mapping and counting of forestry facilities (recreation forests, trails, leports) by administrative district (Si/Gun/Gu).
- **Address Parsing & Standardization**: Implemented robust logic to parse non-standard address strings into structured administrative units for spatial analysis.
- **Cross-Ministry Data Integration**: Unified heterogeneous data sources with varying column definitions into a single master dataset.

## Directory Structure
```
korea-forest-welfare-data-pipeline/
├── data/
│   ├── raw/            # (Ignored) Raw data from government ministries
│   ├── processed/      # (Ignored) Intermediate processed data
│   └── sample/         # Sample data with headers for reproducibility
├── notebooks/
│   ├── 01_data_extraction_and_mapping.ipynb  # Facility counting & mapping logic
│   └── 02_address_parsing_and_merging.ipynb  # Address parsing & data merging
├── results/
│   └── figures/        # Visualization outputs
└── README.md
```

## Getting Started
### Prerequisites
- Python 3.x
- Jupyter Notebook
- Pandas, NumPy

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ben10js/korea-forest-welfare-data-pipeline.git
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy openpyxl
   ```

### Usage
1. Place your raw Excel files in `data/raw/` (or use the provided sample in `data/sample/`).
2. Run the notebooks in order:
   - `01_data_extraction_and_mapping.ipynb`: To aggregate facility counts.
   - `02_address_parsing_and_merging.ipynb`: To parse addresses and merge datasets.

## Impact
- **Efficiency**: Reduced data construction time by utilizing LLM tools for unstructured data.
- **Policy Support**: Provided the foundational dataset for the '2025 Forestry Welfare In-depth Evaluation', enabling evidence-based analysis of regional service gaps.

## Author
- **Junsu Kim** (ben10js40@gmail.com)
