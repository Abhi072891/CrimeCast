# Dataset: Crime Category Prediction Challenge (v1.0)

## Overview
This dataset offers a comprehensive snapshot of criminal activities within the city. It encompasses various aspects of each incident, including date, time, location, victim demographics, and more.

By leveraging machine learning techniques, participants can analyze this rich dataset to predict crime categories, enhance law enforcement strategies, and bolster public safety measures.

**Task:** Develop models capable of accurately predicting the crime categories based on incident information.

Welcome to our challenge of predicting crime categories! In this competition, you'll analyze a dataset filled with information about crime incidents. You'll look at where the incidents happened, details about the victims, and other important factors.

Your goal is to use this data to predict the type of crime that occurred.

---

## Data Files (location in repository)
- `data/raw/` — raw files (original uploads, PDFs, XLS, or downloaded CSVs).
  - `train.csv` (raw training file — contains `crime_category` target)
  - `test.csv` (raw test file — target withheld)
- `data/processed/` — cleaned and processed CSV(s) used for modeling:
  - `train_clean.csv`
  - `test_clean.csv`
- `data/data_dictionary.csv` — column descriptions and types.
- `data/sample_submission.csv` — sample submission template for competition.

---

## Columns / Short Description
The dataset contains the following fields (target variable is `crime_category`):

- **Location:** Street address of the crime incident.  
- **Cross_Street:** Cross street of the rounded address.  
- **Latitude:** Latitude coordinates of the crime incident.  
- **Longitude:** Longitude coordinates of the crime incident.  
- **Date_Reported:** Date the incident was reported.  
- **Date_Occurred:** Date the incident occurred.  
- **Time_Occurred:** Time the incident occurred (24-hour).  
- **Area_ID:** LAPD's Geographic Area number.  
- **Area_Name:** Name of the LAPD Geographic Area.  
- **Reporting_District_no:** Reporting district number.  
- **Part 1-2:** Crime classification.  
- **Modus_Operandi:** Activities associated with the suspect.  
- **Victim_Age:** Age of the victim.  
- **Victim_Sex:** Gender of the victim.  
- **Victim_Descent:** Descent code of the victim.  
- **Premise_Code:** Premise code indicating the location of the crime.  
- **Premise_Description:** Description of the premise code.  
- **Weapon_Used_Code:** Weapon code indicating the type of weapon used.  
- **Weapon_Description:** Description of the weapon code.  
- **Status:** Status of the case.  
- **Status_Description:** Description of the status code.  
- **Crime_Category:** The category of the crime (Target Variable).

Full descriptions are available in `data/data_dictionary.csv`.

---

## Data acquisition
Raw data files were collected from public sources and/or processed from original files. See `docs/data_acquisition_log.md` for an exact log of sources, dates, and scripts used to obtain the data.

**Important:** `data/raw/` contains the original uploaded files; `data/processed/` contains cleaned files used for modeling.

---

## Cleaning & preprocessing
Cleaning steps and scripts are in `code/clean_data.py`. Key steps include:
1. Parsing and standardizing date/time fields.
2. Geolocation normalization (latitude/longitude checks).
3. Standardizing categorical fields (victim sex/descent, status codes).
4. Handling missing values and duplicates.
5. Feature engineering (e.g., `hour_of_day`, `weekday`, `is_weekend`).

---

## How to reproduce
1. Clone the repo.  
2. Put raw files into `data/raw/` (if not already present).  
3. Create a Python environment and install required packages (pandas, geopandas, requests, beautifulsoup4, etc.).  
4. Run `python code/clean_data.py` to create cleaned CSVs in `data/processed/`.  
5. Open `code/exploratory_notebook.ipynb` for EDA and model examples.

---

## Citation
Please cite the dataset like this:

