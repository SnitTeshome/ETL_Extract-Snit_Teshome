# *ETL_Extract-Snit_Teshome*  
## **DSA2040_LAB 3 – Practicing Extraction in ETL_**

---

## *Table of Contents*  
- *[Overview](#overview)*  
- *[Project Objective](#project-objective)*  
- *[Tools & Technologies](#tools--technologies)*  
- *[How to Use](#how-to-use)*  
- *[Repository Structure](#repository-structure)* 
- *[How to Reproduce](#how-to-reproduce)*  
- *[Repository URL](#repository-url)*  
- [License](#license)

---

## *Overview*

### *Historical Description of the Car Sales Dataset*

*This dataset represents simulated used car sales data over two months (April–May 2025). It includes purchases by major automotive dealers, rental companies, and vehicle auction services such as AutoNation, CarMax, Enterprise Holdings, and Manheim.*

*The dataset features popular car brands like Toyota, Honda, Ford, Hyundai, and Chevrolet, with model years ranging from 2015 to 2023. It records key details such as vehicle age, mileage, price, and payment types, offering a realistic view of market diversity and buyer preferences.*

#### *Key Attributes*

- *Date of Sale:* *The date on which the car transaction occurred, showing when the vehicle was purchased.*  
- *Dealer:* *Represents the company or automotive group that sold or distributed the vehicle.*  
- *Car Make and Model:* *Describes the manufacturer (e.g., Toyota, Ford) and specific model of the vehicle, indicating brand preference and market variety.*  
- *Manufacture Year:* *Indicates the year the vehicle was made, providing context for its age and potential value depreciation.*  
- *Odometer Reading:* *Shows the total distance the vehicle had traveled before the sale, an important factor influencing its condition and price.*  
- *Sale Price:* *The amount (in USD) for which the vehicle was sold, indicating market demand and valuation.*  
- *Payment Method:* *Specifies how the transaction was completed—via cash, credit, or loan—reflecting diverse financing choices.*  
- *Last Updated:* *The timestamp of the most recent update to the record, helping track edits or corrections.*

---

## *Project Objective*

*Reinforce understanding of **Full Extraction** and **Incremental Extraction**  and also  **Full Transformation** and **Incremental Transformation** by creating an ETL notebook that performs both extraction and transform types on a realistic dataset, capturing only new or changed data incrementally.*

---

## *Tools & Technologies*
- *Python*  
- *pandas*  
- *NumPy*  
- *Jupyter Notebook*  

---

## *How to Use*

1. *Clone the repository*  
2. *Open the Jupyter Notebook* `etl_extract.ipynb`  
3. *Run cells step-by-step to observe Full and Incremental Extraction*  
4. *Dataset used:* `car_sales_data_may_2025.csv`  
5. *Track extraction checkpoints via* `last_extraction.txt`


## *Repository Structure*

```plaintext
ETL_Extract_Snit_Teshome/
├── etl_extract.ipynb                        # Jupyter Notebook with ETL implementation
├── car_sales_data_may_2025.csv             # Dataset file
├── Out_put_Extraction/                     # Folder for extraction outputs
│   ├── car_sales_full_extraction_output.csv          # Output of full extraction (saved CSV)
│   ├── car_sales_incremental_extraction_output.csv    # Output of incremental extraction (saved CSV)
├── last_extraction.txt                     # Timestamp for incremental extraction
├── Out_put_Transformaion/                     # Folder for extraction outputs
│   ├── transformed_full_output.csv          # Output of full extraction (saved CSV)
│   ├──transformed_incremental.csv.csv
├── etl_load.ipynb              #Notebook focuses on loading.     
├── loaded_data/                     # Folder for extraction outputs
│   ├── full_data.parquet         # Output of full extraction (saved CSV)
│   ├──incremental_data.parquet
├── README.md                               # Project documentation
└── .gitignore                              # Git ignore file

```
---
 *`04_last_extraction.txt` is tracked once and then ignored using `.gitignore` and `git update-index` to prevent unnecessary commits while keeping it in the repo.*

---


## *How to Reproduce*

- *Run the notebook* `etl_extract.ipynb` *in your Jupyter environment.*  
- *Ensure the files* `car_sales_data_may_2025.csv` *and* `last_extraction.txt` *are in the working directory.*  
- *Follow the notebook sections:*  
  - ***Step 1:*** *Generate or load the dataset*  
  - ***Section 1:*** *Perform full extraction of all data*  
  - ***Section 2:*** *Perform incremental extraction based on last extraction timestamp*  
  - ***Section 3:*** *Update the extraction timestamp after incremental extraction*  
---
## *Lab 5 – Load Section*

_In this section, the transformed car sales records were loaded and saved in an optimized format for storage and future analysis._

## *Loading Method Used*  
_The data was loaded using Python's `pandas` library. The transformed CSV files were read and then converted to Parquet format, which offers efficient storage and is well-suited for analytical workflows._

## *Data Files Processed* 
- _`transformed_full.csv` was converted to `full_data.parquet`._  
- _`transformed_incremental.csv` was converted to `incremental_data.parquet`._
## *Sample Code*

```python
import pandas as pd

# Full transformed data
full_df = pd.read_csv("transformed_full.csv")
full_df.to_parquet("full_data.parquet", index=False)

# Incremental transformed data
incremental_df = pd.read_csv("transformed_incremental.csv")
incremental_df.to_parquet("incremental_data.parquet", index=False)

# Verifying the Parquet files
pd.read_parquet("full_data.parquet").head()
pd.read_parquet("incremental_data.parquet").head()
```

## *Output Location for Loading*

_The output files were saved in Parquet format within the current repository directory. These files are ready to be used for downstream analytics, integration into data platforms, or long-term storage alongside this project._

- _`full_data.parquet`_  
- _`incremental_data.parquet`_

## *Repository URL*

[https://github.com/SnitTeshome/ETL_Extract-Snit_Teshome](https://github.com/SnitTeshome/ETL_Extract-Snit_Teshome)

## *License*

This project is licensed under the [MIT License](https://github.com/SnitTeshome/ETL_Extract-Snit_Teshome?tab=MIT-1-ov-file).

© 2025 Snit Kahsay Teshome