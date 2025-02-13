# Patient Data Extraction and Analysis

This repository contains Jupyter Notebook files for extracting, processing, and analyzing patient data using OCR (Optical Character Recognition) and computer vision techniques. The project utilizes EasyOCR and OpenCV to extract information from medical forms and structures the data in a JSON format.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Example Output](#example-output)

---

## Overview
This project automates the process of extracting structured patient information from scanned medical documents. It:
- Detects and extracts text from predefined bounding boxes using OCR.
- - Detects handwritten or printed numbers inside circles using computer vision.
- Structures extracted data into JSON format.
- Saves the processed data for further analysis.

---

## Features
- **Bounding Box Detection**: Manually draw the region of interest bounding boxes and note the coordinates 
- **OCR-based Text Extraction**: Uses EasyOCR to extract text from images.
- **Circle Detection for Numeric Inputs**: Uses OpenCV to detect and read circled values.
- **JSON Structuring**: Outputs extracted data in a structured JSON format.


---

## Installation
### Prerequisites
Ensure you have Python installed (>= 3.8) and install the required libraries:

```bash
pip install easyocr opencv-python numpy matplotlib pandas json
```

### Clone the Repository
```bash
git clone https://github.com/yourusername/patient-data-extraction.git
cd patient-data-extraction
```

---

## Usage
### Running the Notebooks
1. Open Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Navigate to the project folder and open the notebooks:
   - `Boundingbox.ipynb` (To Define the regions and extract the coordinates for the same)
   - - `patient_analysis.ipynb` (Extract text using OCR from predefined regions and pushes the Data to DB)
   - `Schemas.ipynb` (structured, consistent, and validated data representation)
   - `TableCreation.ipynb` (structuring and creating tables in the database to store patient data. )
3. Run the notebooks step by step to process an image and extract structured data.


---

## Project Structure
```
patient-data-extraction/
│── Boundingbox.ipynb       # To Define the regions and extract the coordinates
│── Schemas.ipynb           # structured, consistent, and validated data representation
│── TableCreation.ipynb     # structuring and creating tables in the database to store patient data. 
│── patient_analysis.ipynb  # Detects bounding boxes and extracts text and store in DB
│── example.png             # Sample input image
│── output.json             # Extracted JSON data
│── requirements.txt        # Dependencies for the project
│── README.md               # Project documentation
```

---

## Example Output
{
    "patient_name": "Akhil",
    "dob": "lo",
    "date": "Ie/o3/2025",
    "injection": "No",
    "exercise_therapy": "No",
    "difficulty_ratings": {
        "bending": null,
        "putting_on_shoes": null,
        "sleeping": null
    },
    "patient_changes": {
        "since_last_treatment": "",
        "since_start_of_treatment": "",
        "last_3_days": ""

---




---



---







## Database Schema
### `patient_details` Table
| Column        | Type         | Description            |
|--------------|-------------|------------------------|
| patient_id   | INT (PK)     | Unique patient ID     |
| patient_name | VARCHAR(100) | Name of the patient  |
| dob          | VARCHAR(100) | Date of Birth        |

### `treatment_details` Table
| Column         | Type         | Description                |
|--------------|-------------|----------------------------|
| treatment_id | INT (PK)     | Unique treatment ID       |
| patient_id   | INT (FK)     | Reference to patient ID   |
| date         | VARCHAR(100) | Treatment date            |
| injection    | VARCHAR(100) | Injection details         |
| exercise_therapy | VARCHAR(100) | Therapy details      |

### `difficulty_ratings` Table
| Column                | Type         | Description                     |
|----------------------|-------------|---------------------------------|
| rating_id           | INT (PK)     | Unique rating ID               |
| patient_id          | INT (FK)     | Reference to patient ID        |
| date                | VARCHAR(100) | Date of assessment            |
| bending_or_stooping | VARCHAR(100) | Difficulty rating             |
| putting_on_shoes    | VARCHAR(100) | Difficulty rating             |
| sleeping            | VARCHAR(100) | Difficulty rating             |



