# Data Quality Validation script
This script is designed to perform automated data quality checks on an e-commerce dataset.
## Purpose
this script validates data quality across key dimension :  
**completeness**:Missing values and missing months in the data range
**Accuracy** : Outlier in Quantity and price and total amount using IQR 
**Consistency**: Total amount mismatch  
**Timeliness**:Orders with future dates   
**Uniqueness**:Duplicate orderID and CustomerID

## What this script check
1.   **Missing Values**  
        - check for nulls in all columns   
        - prints count of missing values per column
2.      **Missing months**   
    
3.   **TotalAmount Validation**  
        - calculates :Quantity * Unit price   
        - compare it with the existing TotalAmount  
        - Detect Mismatches and groups them by:  
         - product category
         - Customer Location
         - order Date


4.   **Duplicated Checks**  
        -Duplicate OrderID  
        -Duplicate customerUD
        -identifies fully duplicated rows

5.    **Quantity outlier**    
        -Detect Quantity Values less than 0 or greater than 100  
6.   **Price outlier**  
        -Detect price values less than 0 or grater than 1000   

7.    **outliers detection** 
        -Detect outliers in Quantity and pricw and totalamount  usin IQR method
       
6.   **Futures Dates**  
        - Identifies any OrderDate values later than todays date  


## Insights from cleaned and original data  
a seperated dataframe was created to apply data cleaning operations like duplicated removal ,outlier removal.monthly totalamount was calculated befor and after cleaning.   

Key findings:  
- cleaned data showed lower and more consistent totals  
-outliers in the original data inflated monthly totals up to 50000  
-cleaned data had more stable trend,peaking around 35000    
-missing months like november and december 2025 were identified and addressed


## How to run  
1 open this script in Google Colab   
2 Make sure your dataset is located at: /content/drive/MyDrive/ecommerce-dataset.csv  
3 Run all sells from top to bottom   
4 Results will be printed directly in the output cells   

## Output
1.   clear print statements for each validation
2.   Tables showing invalid or inconsistent records  
3.   count of duplicated ,missing values and outlier

## Notes
-you can change the price and quantity limits if your business rules are different   
-Make sure the CSV file path matches your Google Drive location














