# 🛍️ E-Commerce Customer Segmentation using Hierarchical Clustering

## 📌 Problem Statement

To cluster users of an e-commerce platform based on their behavior (e.g., time spent, items added to cart, purchase history) and identify distinct customer types using Hierarchical Clustering.

---

## 🗃️ Dataset

A realistic dummy dataset was created with 20 samples and 6 features:

- `Session_Duration`: Duration of the user session (minutes)  
- `Pages_Visited`: Number of pages visited in the session  
- `Items_in_Cart`: Number of items added to the cart  
- `Avg_Session_Value`: Average value of the session (in dollars)  
- `Time_Spent_on_Site`: Time spent on the site (seconds)  
- `Purchase_History`: Total number of past purchases  

---

## 🛠️ Technologies & Libraries Used

- Python  
- pandas, NumPy  
- scikit-learn  
- matplotlib, seaborn  
- scipy  

---

## ⚙️ Steps Performed

1. **Data Preparation**: Created a dummy dataset and converted it to a pandas DataFrame.  
2. **Standardization**: Used `StandardScaler` to normalize feature values.  
3. **Determine Optimal Clusters**: Used Dendrogram with `linkage(method='ward')`.  
4. **Apply Agglomerative Clustering**: Applied clustering with `n_clusters=2`, `metric='euclidean'`, and `linkage='ward'`.  
5. **Assign Cluster Names**:  
   - Cluster 0 → `Premium Customers`  
   - Cluster 1 → `One-Time Browsers`  
6. **Visualize the Result**:  
   - Created a scatter plot using `Session_Duration` vs `Avg_Session_Value`.

---

## ✅ Conclusion

This project demonstrates how unsupervised learning can reveal valuable customer patterns in e-commerce businesses, helping in better targeting and decision-making.

---
