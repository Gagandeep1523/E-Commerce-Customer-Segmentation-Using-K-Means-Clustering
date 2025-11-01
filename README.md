# E-Commerce-Customer-Segmentation-Using-K-Means-Clustering
# 📊 E-Commerce Customer Segmentation Using K-Means Clustering

## **Project Overview**
This project applies **K-Means clustering** to an E-commerce customer transaction dataset to identify **distinct customer segments** based on purchase behavior. The goal is to uncover patterns that help businesses target marketing campaigns, optimize retention strategies, and increase revenue.

The project includes:  
- Data preprocessing & aggregation  
- K-Means clustering & evaluation (Silhouette Score)  
- PCA for 2D visualization  
- Boxplots for feature distributions  
- Cluster profiling with business insights  
- Streamlit dashboard for interactive visualization and prediction  

---

## **Dataset**
The dataset used is **`ecommerce_transaction.csv`**, containing **50,000 rows and 8 columns**:

| Column | Description |
|--------|-------------|
| `Transaction_ID` | Unique transaction identifier |
| `User_Name` | Customer name/ID |
| `Age` | Customer age |
| `Country` | Customer country |
| `Product_Category` | Product category purchased |
| `Purchase_Amount` | Transaction amount |
| `Payment_Method` | Payment type |
| `Transaction_Date` | Date of transaction |

> After processing, a new dataset **`clustered_customers.csv`** is generated containing **customer-level aggregated features and cluster labels**.

---

## **Methodology**

### **1. Data Preprocessing**
- Removed duplicates and cleaned column names  
- Converted data types to proper formats  
- Aggregated data on **User_Name** to create customer-level metrics:  
  - `Total_Purchase` = sum of purchases  
  - `Avg_Purchase` = mean purchase  
  - `Num_Transactions` = number of purchases  

### **2. Feature Scaling**
- Standardized features (`Age`, `Total_Purchase`, `Avg_Purchase`, `Num_Transactions`) using `StandardScaler`

### **3. K-Means Clustering**
Silhouette scores tested across clusters:

| K | Silhouette Score |
|---|------------------|
| 2 | 0.306 |
| 3 | 0.258 |
| 4 | 0.242 |

**K = 2** performed best and was selected.

### **4. Dimensionality Reduction**
- PCA used to reduce dimensions to two components for 2D plotting

### **5. Cluster Insights**
Two customer segments identified:

✅ **Cluster 1 – High-Value Customers**  
- Higher spending  
- Higher average purchase  
- More transactions  
- Good for loyalty programs & personalized offers  

✅ **Cluster 0 – Moderate-Value Customers**  
- Lower total spending  
- Fewer transactions  
- Good target for marketing discounts & retention campaigns  

---

## **Visualizations**
- Boxplots for cluster distribution analysis  
- PCA scatter plot for cluster separation  

Visuals included in project report & Streamlit UI.

---

## **Streamlit Dashboard**
The Streamlit application enables:  
✅ Viewing clustered results  
✅ PCA visualization  
✅ Boxplots  
✅ Cluster statistics  
✅ Downloading `clustered_customers.csv`  
✅ Predicting cluster for new customer input  

### **Run the app**
```
streamlit run app.py
```

---

## **Project Structure**
```
kmeans-customer-segmentation/
│── data/
│    └── ecommerce_transaction.csv     # Original dataset (50K rows)
│── outputs/
│    └── clustered_customers.csv       # Output after clustering
│── app.py                             # Streamlit application
│── requirements.txt                   # Required libraries
│── README.md                          # Documentation
```

---

## **Tech Stack**
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- Matplotlib  
- Seaborn  
- Streamlit  

---

## **Key Takeaways**
- Customer segmentation enables targeted marketing strategies  
- K-Means identified distinguishable behavioral groups  
- PCA helped visualize cluster separation  
- Streamlit UI improves usability and interpretable reporting  

---

## **Future Improvements**
- Include additional behavioral features (RFM analysis)  
- Use supervised models to predict high-value customers  
- Add time-series segmentation  

---

✅ **Final Outputs**
- `clustered_customers.csv` → Final enriched dataset with segments  
- `app.py` → Interactive Streamlit application
