# Customer Segmentation using K-Means Clustering

## Overview:
This project demonstrates how to segment customers based on their behavior (e.g., Age, Income, Spending Score, and Gender) using the K-Means clustering algorithm. It applies data preprocessing, clustering, dimensionality reduction (PCA), and interactive visualizations to analyze and understand customer segments. The analysis allows businesses to tailor marketing strategies and optimize customer engagement.

## Project Workflow:
1. **Data Creation/Loading**: A sample dataset is either loaded or created with random values for customer attributes.
2. **Data Preprocessing**:
   - Missing values are forward-filled.
   - Categorical variables (e.g., Gender) are converted into numeric format.
3. **K-Means Clustering**:
   - The dataset is clustered into 5 groups using the K-Means algorithm.
4. **Dimensionality Reduction**:
   - PCA (Principal Component Analysis) is used to reduce the dataset to two dimensions for easy visualization.
5. **Interactive Visualizations**:
   - Interactive scatter plot, box plot, and bar chart are generated using **Plotly** for better exploration of the clustering results.

## Technologies Used:
- **Python** (Pandas, NumPy, Scikit-learn, Plotly, Matplotlib)
- **Jupyter Notebook** for interactive analysis
- **K-Means** for customer segmentation
- **PCA** for dimensionality reduction
- **Plotly** for interactive visualizations

## Steps to Run the Project:

### 1. Clone the repository:
```bash
git clone https://github.com/your_username/customer-segmentation
