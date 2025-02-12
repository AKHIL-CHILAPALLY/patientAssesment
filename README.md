# Patient Details Processing with PySpark

## Overview
This project is designed to extract patient details from PDFs using PySpark and store them in a structured database. It utilizes image processing, OCR, and MySQL to handle patient data effectively.

## Features
- Extracts patient details from scanned images using OpenCV and EasyOCR.
- Defines database schemas for patient details, treatments, and difficulty ratings.
- Automates table creation and data storage in MySQL.

## Project Structure
```
.
├── patient_analysis.ipynb   # Extracts patient details from images
├── Schemas.ipynb            # Defines MySQL schemas
├── TableCreation.ipynb      # Creates MySQL tables
├── README.md                # Project documentation
```

## Dependencies
- Python 3.x
- PySpark
- OpenCV
- EasyOCR
- pymysql
- Jupyter Notebook

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/patient-details-processing.git
   cd patient-details-processing
   ```
2. Install dependencies:
   ```bash
   pip install opencv-python easyocr pymysql pyspark
   ```

## Usage
1. Run `Schemas.ipynb` to define the database structure.
2. Run `TableCreation.ipynb` to create tables in MySQL.
3. Run `patient_analysis.ipynb` to extract and store patient details.

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

## Future Enhancements
- Automate PDF parsing with PySpark.
- Enhance OCR accuracy using deep learning models.
- Implement a front-end dashboard for real-time monitoring.

## License
This project is open-source and available under the [MIT License](LICENSE).

