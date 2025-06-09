# Customer Segmentation with K-Means

This project performs customer segmentation using **K-Means clustering** and **PCA** for visualization. It processes customer data (or generates a sample dataset), encodes categorical features, scales the data, clusters customers into 5 groups, and visualizes the result in 2D.

> 🧠 Useful for marketing analytics, customer profiling, and behavioral segmentation.

---

## 📌 Features

- Loads existing customer data or generates sample data if none is found
- Preprocesses and encodes categorical data (e.g., Gender)
- Scales features using `StandardScaler`
- Performs K-Means clustering with 5 clusters
- Reduces dimensions with PCA for visualization
- Saves clustered data to `segmented_customers.csv`
- Handles MKL memory leak on Windows (`OMP_NUM_THREADS=1`)

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Johnsondataeverywhere/customer-segmentation.git
cd customer-segmentation
