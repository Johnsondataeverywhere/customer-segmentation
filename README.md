# Customer Segmentation with K-Means

This project performs customer segmentation using **K-Means clustering** and **PCA** for visualization. It processes customer data (or generates a sample dataset if none exists), handles preprocessing and encoding, scales features, clusters customers into 5 groups, and visualizes the clusters in 2D.

> 🧠 Helps businesses understand customer groups to improve marketing and sales strategies.

---

## Features

- Loads existing customer data or creates a sample dataset
- Handles missing values with forward-fill
- Encodes categorical features (e.g., Gender) using one-hot encoding
- Scales features with `StandardScaler`
- Applies K-Means clustering with 5 clusters
- Visualizes clusters using PCA in a 2D scatter plot
- Saves clustered data with assigned cluster labels to CSV

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Johnsondataeverywhere/customer-segmentation.git
cd customer-segmentation
