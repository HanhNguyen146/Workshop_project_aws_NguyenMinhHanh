---
title: "Worklog Week 3"
date: 2026-06-15
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Structure the source code for data preprocessing and data validation.

* Convert the source code from Jupyter Notebook to independent Python scripts to automate the data cleaning process.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Reference Materials |
| --- | ---- | ---------- | --------------- | ------------------- |
| Mon | - Create the `src/preprocessing.py` file. <br> - Write the `load_data()` and `handle_missing_values()` functions to load and clean raw SCADA data. | 15/06/2026 | 17/06/2026 | <https://pandas.pydata.org/docs/> |
| Tue | - Program the `src/data_validation.py` module with the `validate_data()` function to automate input data integrity checks. | 16/06/2026 | 17/06/2026 | <https://docs.python.org/3/> |
| Wed | - Write the `data_validation.py` script to run independent testing without executing the entire pipeline. | 17/06/2026 | 18/06/2026 | <https://docs.pytest.org/> |
| Thu | - Integrate interpolation mechanisms to handle missing time-series data (lag) and preserve valid outliers. | 18/06/2026 | 19/06/2026 | <https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.interpolate.html> |
| Fri | - **Practice:** <br>&emsp; + Test the `data_validation.py` script locally via terminal. <br>&emsp; + Ensure it returns a 'PASS' status and handle any warnings before exporting the clean data. | 19/06/2026 | 19/06/2026 |  |

### Week 3 Achievements:

* Successfully converted the data cleaning pipeline from the experimental environment (Notebook) to standardized Python scripts (`src/preprocessing.py`).

* Successfully built an independent validation system (`data_validation.py`) to analyze error reports, ensuring the data always meets the input standards for machine learning models.