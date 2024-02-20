# Product Recommendation using Python

## Introduction
This repository contains code for performing item-to-item similarity and user-to-user similarity analysis using cosine similarity on transaction data from an online retail dataset. The analysis aims to find items that are similar to each other based on customer purchase behavior.

## Data
The dataset used in this analysis is from an online retail store and is stored in an Excel file named 'Online Retail.xlsx'. It contains the following columns:

1. `InvoiceNo`: Invoice number
2. `StockCode`: Stock code of the product
3. `Description`: Description of the product
4. `Quantity`: Quantity of the product purchased
5. `InvoiceDate`: Date and time of the invoice
6. `UnitPrice`: Unit price of the product
7. `CustomerID`: ID of the customer
8. `Country`: Country of the customer

## Preprocessing
1. Loading the dataset: The dataset is loaded into a pandas DataFrame.
2. Handling missing values: Rows with missing `CustomerID` values are removed from the dataset.
3. Pivot table creation: A pivot table is created to transform the data into a matrix format where rows represent customers, columns represent items (identified by `StockCode`), and values represent the quantity of each item purchased by each customer.
4. Binarization: The quantity values in the pivot table are binarized to represent whether an item was purchased by a customer or not.
5. Item-to-item similarity calculation: Cosine similarity is calculated between items based on the binarized pivot table.

## Analysis
Item-to Item Similarity Matrix:
-	Item-to-item similarity matrix: A heatmap visualization of the item-to-item similarity matrix is generated using seaborn. The matrix shows the pairwise cosine similarity between items.
-	Top similar items: For a given item (e.g., `StockCode` 23843), the top 10 similar items are identified based on cosine similarity scores.
-	Description lookup: The descriptions of the top similar items are retrieved from the dataset.
User-to-User Similarity Matrix:
-	A heatmap visualization of the user-to-user similarity matrix is generated using seaborn. The matrix shows the pairwise cosine similarity between customers, indicating how similar their purchase behaviors are.
-	Recommendations: For a given user, items are recommended based on the items purchased by similar users.


## Libraries and Modules
The analysis utilizes the following Python libraries and modules:
- pandas: For data manipulation and analysis.
- sklearn.metrics.pairwise.cosine_similarity: For calculating cosine similarity.
- seaborn: For creating visualizations.
- matplotlib.pyplot: For customizing and displaying plots.

## Instructions
To replicate the analysis:
1. Ensure you have Python installed on your system.
2. Install the required libraries using pip: `pip install pandas scikit-learn seaborn matplotlib`.
3. Download the dataset 'Online Retail.xlsx'.
4. Run the provided Python script, ensuring that the dataset file path is correctly specified.
5. Review the generated heatmap and top similar items.

## Conclusion
Item-to-item and user-to-user similarity analysis is a valuable technique for understanding product relationships and recommending similar items to customers. By leveraging cosine similarity on transaction data, businesses can enhance their recommendation systems and optimize product offerings.

## References
- Documentation for pandas: https://pandas.pydata.org/docs/
- Documentation for scikit-learn: https://scikit-learn.org/stable/documentation.html
- Documentation for seaborn: https://seaborn.pydata.org/
- Documentation for matplotlib: https://matplotlib.org/stable/contents.html
