# Customer Lookalike Analysis

This project performs a customer lookalike analysis by combining customer, product, and transaction data. The goal is to identify customers who have similar purchase behaviors and demographic features using a combination of data processing, feature engineering, and machine learning techniques.

## Project Structure

- `Customers.csv`: Contains information about customers including customer ID, region, and signup date.
- `Products.csv`: Contains details about products including product ID, category, and price.
- `Transactions.csv`: Contains transaction records including customer ID, product ID, and total value of each transaction.

## Steps

1. **Data Merging and Cleaning**:
   - The project merges the `Customers.csv`, `Products.csv`, and `Transactions.csv` datasets on appropriate IDs (`CustomerID` and `ProductID`).
   - The `TransactionDate` and `SignupDate` columns are converted to datetime format.

2. **Feature Engineering**:
   - Customer-level features are created by aggregating transaction data, including the total value spent by each customer, categories of products purchased, and the region of the customer.

3. **Data Encoding**:
   - Multi-label binarization is applied to the product categories purchased by each customer.
   - The `Region` column is label encoded to transform categorical values into numeric values.

4. **Cosine Similarity Calculation**:
   - A customer-feature matrix is created with product categories, total spending, and encoded region data.
   - Cosine similarity scores are calculated between customers to identify similar customers.

5. **Lookalike Identification**:
   - For each customer, the top 3 lookalikes are identified based on similarity scores.

6. **Output**:
   - The results are saved to a CSV file (`Lookalike.csv`) that contains the lookalike customers for the top 20 customers.

## Requirements

To run this project, you will need the following Python packages:

- pandas
- scikit-learn
- matplotlib
- seaborn

You can install the required dependencies using the following command:


pip install -r requirements.txt

Where requirements.txt contains the following:
pandas
scikit-learn
matplotlib
seaborn


How to Run
Clone the repository:

git clone (https://github.com/samvid753/Samvid_Verma_zeotap_assignment)
cd customer-lookalike-analysis

Run the Jupyter Notebook:

jupyter notebook customer_lookalike_analysis.ipynb

The results will be displayed in the notebook, and a CSV file with the customer lookalikes will be generated.

Output
A CSV file (Lookalike.csv) containing the CustomerID and their top 3 lookalikes based on the similarity of purchase behavior.
Notes
Make sure that the CSV files (Customers.csv, Products.csv, and Transactions.csv) are available in the same directory as the notebook, or update the file paths accordingly.
The lookalike identification is based on the cosine similarity of customer purchase behaviors and demographic features.
