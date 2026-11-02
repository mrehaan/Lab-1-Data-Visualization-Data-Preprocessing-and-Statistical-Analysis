# MSCS-634 Lab 1

## Data Visualization, Data Preprocessing, and Statistical Analysis Using Python

**Mohammed Rehaan**  
**005046243**  
**University of the Cumberlands**  
**MSCS-634-B01: Advanced Big Data and Data Mining**  
**Dr. Penmatsa**

## Purpose

This lab uses Pandas, Matplotlib, Seaborn, and Scikit-learn to explore and prepare the UCI Online Retail dataset. The data records product-line transactions from a United Kingdom-based online retailer between December 2010 and December 2011. It contains 541,909 rows and eight source attributes, including invoice date, quantity, unit price, customer identifier, and country.

The notebook completes the required dataset collection, visualizations, missing-value handling, duplicate removal, outlier detection through the IQR method, data reduction, Min-Max scaling, quantity discretization, and statistical analysis.

## Contents

- `Mohammed_Rehaan_MSCS_634_Lab_1.ipynb`: Executed lab notebook.
- `data/raw/Online Retail.xlsx`: Original UCI source file.
- `data/processed/online_retail_lab_cleaned.csv`: Cleaned and reduced data created by the notebook.
- `screenshots/`: Twenty-one labeled PNG files for the required notebook evidence.
- `requirements.txt`: Python packages needed to run the notebook.

## Key insights

The United Kingdom generates most of the recorded sales because it also contains most transactions. Monthly sales fluctuate across the year and increase sharply near the end of 2011. Most transaction lines have small quantities and lower unit prices, while a small number of high-value sales lines create a right-skewed sales distribution.

The original dataset has missing customer identifiers and product descriptions. Missing descriptions are replaced with `Unknown product description`, while rows without a customer identifier are removed because they cannot support customer-level retail analysis. Duplicate records, cancellation or zero-value lines, and IQR-identified sales-amount outliers are removed before the 10% sample is taken. The final file also includes scaled unit-price and sales-amount fields plus a four-level quantity band.

Sales amount is positively related to quantity and unit price because it is calculated by multiplying those variables. A later model should not assume that all three variables offer independent information.

## Decisions and challenges

The main challenge was separating negative quantities that represent returns or cancellations from ordinary sales. This lab focuses on completed positive sales, so those records were excluded after their count was reported. Large transactions were identified through the IQR rule and removed for the reduced lab dataset, although they could be retained for a separate business analysis of bulk orders.

## Source

Chen, D. (2015). *Online Retail* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33

## Running the notebook

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```
