# Set number of threads to 1 to avoid KMeans memory leak on Windows (MKL issue)
import os
os.environ["OMP_NUM_THREADS"] = "1"

# Imports
import pandas as pd
import numpy as np
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA
import matplotlib.pyplot as plt

# Load or Create Dataset
filename = 'customer_data.csv'
if not os.path.exists(filename):
    print(f"File '{filename}' not found. Creating a sample dataset.")
    np.random.seed(42)
    sample_data = pd.DataFrame({
        'Age': np.random.randint(18, 70, 200),
        'Income': np.random.randint(20000, 120000, 200),
        'SpendingScore': np.random.randint(1, 100, 200),
        'Gender': np.random.choice(['Male', 'Female'], 200)
    })
    sample_data.to_csv(filename, index=False)
    data = sample_data
else:
    data = pd.read_csv(filename)

# Preprocessing
data.ffill(inplace=True)  # Forward-fill missing values
data = pd.get_dummies(data)  # Convert categorical to numeric

# Scale the data
scaler = StandardScaler()
scaled_data = scaler.fit_transform(data)

# Apply K-Means Clustering
kmeans = KMeans(n_clusters=5, random_state=42, n_init=10)
data['Cluster'] = kmeans.fit_predict(scaled_data)

# Reduce dimensions using PCA for visualization
pca = PCA(n_components=2)
pca_components = pca.fit_transform(scaled_data)

# Plot the clusters
plt.figure(figsize=(10, 6))
plt.scatter(pca_components[:, 0], pca_components[:, 1], c=data['Cluster'], cmap='viridis', s=50)
plt.title('Customer Segmentation using K-Means Clustering')
plt.xlabel('PCA Component 1')
plt.ylabel('PCA Component 2')
plt.colorbar(label='Cluster')
plt.grid(True)
plt.show()

# Save the segmented data
data.to_csv('segmented_customers.csv', index=False)
print("Segmented data saved to 'segmented_customers.csv'.")
