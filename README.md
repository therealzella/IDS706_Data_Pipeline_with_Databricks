# Data Pipeline Project

## Overview
This project implements a data pipeline using Databricks. The pipeline reads a CSV file, processes the data using PySpark, and writes the processed data to both Parquet and CSV formats as outputs. Additionally, a CI/CD pipeline is set up using GitHub Actions to ensure code quality through linting and testing.

## Project Structure
- `notebooks/`: Contains the Databricks notebook used for data processing.
- `requirements.txt`: Lists the dependencies required for the project.
- `.github/workflows/ci.yml`: GitHub Actions workflow for CI/CD.

## Data Source and Sink
- **Data Source**: Google Drive is used to store the input data file (`cereal.csv`), which is read into the pipeline for processing.
- **Data Sink**: The output of the pipeline is saved in both Parquet and CSV formats in the Databricks File System (DBFS).

## Pipeline Functionality
The data pipeline performs the following steps:
1. **Data Ingestion**: Reads data from `cereal.csv` stored in Google Drive.
2. **Data Processing**: Using PySpark, the data is cleaned, filtered, and some basic transformations are applied (e.g., calculating average calories by manufacturer).
3. **Data Output**: The processed data is saved in two formats: Parquet and CSV, in the DBFS.

## CI/CD Pipeline
The CI/CD pipeline is implemented using GitHub Actions. It performs the following tasks:
1. **Install Dependencies**: Installs the dependencies listed in `requirements.txt`.
2. **Linting**: Uses `flake8` to check code quality and styling.
3. **Testing**: Runs unit tests with `pytest` to validate the code functionality.

## Requirements
The required Python packages are listed in `requirements.txt`:
- `black`: Code formatting.
- `click`: Dependency of `black`, useful for command-line interfaces.
- `pytest`: Running tests.
- `pytest-cov`: Measuring test coverage.
- `pylint`: Linting Python code.
- `fastapi`: Web framework (if relevant to project).
- `flake8`: Linting tool.
- `pandas`, `numpy`: For data manipulation.

## Setup Instructions
1. **Clone the Repository**:
   ```sh
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Install Dependencies**:
   ```sh
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

3. **Run the Notebook**:
   - Open the Databricks notebook from the `notebooks/` directory.
   - Follow the steps in the notebook to read the input data, process it, and write the output.

4. **Run Tests and Linting**:
   - Run linting with `flake8`:
     ```sh
     flake8 .
     ```
   - Run tests with `pytest`:
     ```sh
     pytest
     ```
