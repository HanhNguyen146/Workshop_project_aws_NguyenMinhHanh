---
title: "Upload Data to Amazon S3"
date: 2026-07-30
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

### Data Storage Organization on AWS

In an MLOps architecture, **Amazon S3 (Simple Storage Service)** serves as the central "Data Lake". To process data and train models using SageMaker, raw data and processing source code must first be pushed to S3.

We will use a Python script with the `boto3` library to automate the process of pushing raw data and source code to the cloud, rather than doing it manually on the AWS Console. This ensures fast data synchronization and adheres to the MLOps principle of automation.

---

### 1. Prepare Local Directory

In your local project directory structure, ensure that the raw data and source code are in the correct locations:

- `data/raw/T1.csv`: The original, unprocessed SCADA sensor dataset.
- `src/preprocessing.py`: The Python script containing data cleaning and processing logic for SageMaker.
- `src/data_validation.py`: The script to validate data integrity.
- `scripts/setupS3.py`: The script to automatically push data to S3 using `boto3`.

---

### 2. Local Data Validation

Before pushing raw data to the Data Lake (S3), a critical MLOps principle is to ensure the quality of the Input Data. If "garbage data" is pushed to the cloud, it will waste SageMaker's compute resources and cause the entire downstream pipeline to fail.

The project uses the `src/data_validation.py` module to automatically run local tests on strict conditions:
1. **Required Columns:** Checks if the dataset contains all mandatory columns (ActivePower, Wind Speed, Wind Direction, Theoretical_Power_Curve, timestamp).
2. **Row Count:** Ensures the number of samples is large enough (minimum 100 rows) to be statistically significant.
3. **Missing Values:** Warns if the missing data ratio exceeds the allowed threshold (>30%) or throws an error if it's critically high (>50%).
4. **Data Types & Value Ranges:** Ensures all features have a numeric data type and fall within realistic physical limits (e.g., wind direction is strictly between 0-360 degrees).

Only when the report returns a **PASS** status is the raw data allowed to be uploaded to AWS.

---

### 3. Automate S3 Upload with Boto3

Instead of manually creating each folder in the AWS UI, the `setupS3.py` script will automatically connect to S3 using your IAM Role and push the files to their proper locations in the bucket.

Open a Terminal at the root of the project and run the S3 upload script:

```bash
# Ensure you are in the virtual environment
.\.venv\Scripts\python scripts/setupS3.py
```

**The execution process will display output similar to the following:**

```text
📂 Uploading raw data...
 ⬆️ data/raw/T1.csv → s3://amznce23/T1_AD/data/raw/T1.csv

📂 Uploading source code (src/)...
 ⬆️ src/preprocessing.py → s3://amznce23/T1_AD/scripts/src/preprocessing.py
 ⬆️ src/data_validation.py → s3://amznce23/T1_AD/scripts/src/data_validation.py

📂 Uploading entry-point script...
 ⬆️ src/preprocessing.py → s3://amznce23/T1_AD/scripts/preprocessing.py

🎉 Upload complete!
 Raw data : s3://amznce23/T1_AD/data/raw/T1.csv
 Scripts : s3://amznce23/T1_AD/scripts/
```

*(Note: The bucket name `amznce23` and prefix `T1_AD` are pre-configured in the `setupS3.py` file. You can adjust these parameters to match your own bucket if necessary).*

---

### 4. Verify Results on AWS Console

1. Access the **AWS Management Console** and open the **Amazon S3** service.
2. Find and click on your bucket (e.g., `amznce23`).
3. Navigate to the `T1_AD/` folder (or your configured project name).
4. You will see two important directory structures created, containing files:
   - `data/raw/`: Contains the `T1.csv` file.
   - `scripts/`: Contains the preprocessing scripts (`preprocessing.py`, `data_validation.py`...).

{{% notice success %}}
**Complete:**
Congratulations! Your raw data and source code have passed the validation checks and been safely uploaded to the Data Lake. The "raw materials" are now ready to be fed into SageMaker's automated data processing server in the next step.
{{% /notice %}}