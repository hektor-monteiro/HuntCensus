# Hunt Census - Open Clusters Catalog Comparison

This repository contains a Streamlit web application designed to visualize, analyze, and compare open cluster data from different astronomical catalogs, specifically focusing on the Hunt Catalog and comparing it with the Dias Catalog.

Access the live dashboard here: 🔗 [https://catalogscomparison.streamlit.app/](https://catalogscomparison.streamlit.app/)

## Features

* **Home:** General overview and introduction.
* **Hunt Catalog:** View fundamental parameters (age, distance, visual extinction, parallax, radial velocity) for open clusters from the Hunt catalog. Includes interactive Color-Magnitude Diagrams (CMD) and RA/DEC spatial distribution plots.
* **Compare - Dias Catalog:** Compare the fundamental parameters of specific open clusters between the Hunt and Dias catalogs side-by-side with overlaid CMDs.
* **All Clusters:** View scatter plots comparing distance, age, and Av across all common clusters between the catalogs.

## Prerequisites

Before cloning and running the application locally, you must have **Git LFS (Large File Storage)** installed to properly download the large Parquet data files used by the application.

* [Install Git LFS](https://git-lfs.com/)

## Installation and Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/hektor-monteiro/HuntCensus.git
   cd HuntCensus
   ```

2. **Download the data files via Git LFS:**
   This step is **crucial**. Without it, you will encounter `ArrowInvalid: Parquet magic bytes not found` errors.
   ```bash
   git lfs pull
   ```

3. **Set up a virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

4. **Install the dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Running the Application

To launch the Streamlit app locally, run the following command from the root of the repository:

```bash
streamlit run 01_🔵_Home.py
```

The application will open in your default web browser (typically at `http://localhost:8501`).

## Data Sources

* `data/parquet/clusters.parquet`: Fundamental parameters of open clusters.
* `data/parquet/members.parquet`: Stellar membership data.
* `data/log-results-eDR3.txt`: Fundamental parameters derived from our models for comparison.
* `data/membership_data_edr3/`: Individual cluster member data files used for model fitting.