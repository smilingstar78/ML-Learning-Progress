# Principal Component Analysis (PCA)

Today is 10th May, 2025 Saturday and I learnt about PCA:

Principal Component Analysis (PCA) is a technique used to reduce the dimensionality of data while preserving as much variance as possible.

## Steps in PCA

### 1. Mean-Centering
Center the data by subtracting the mean of each feature.

```
mean = df.mean()
centered_data = df - mean
```
### 2. Covariance Matrix
Compute the covariance matrix to measure how features vary together.

```cov_matrix = np.cov(centered_data.T)```

### 3. Eigenvalues & Eigenvectors

Find the eigenvalues and eigenvectors of the covariance matrix. Eigenvectors are the principal components.

```
eigenvalues, eigenvectors = np.linalg.eig(cov_matrix)
```

## 4. Sort Eigenvalues & Eigenvectors

Sort eigenvalues in descending order and rearrange eigenvectors accordingly.

```
eigenvalue_index = eigenvalues.argsort()[::-1]
eigenvectors_sorted = eigenvectors[:, eigenvalue_index]
```

### 5. Select Principal Components

Select the top 
𝑘
k eigenvectors (components) that explain the most variance.

```
eigenvectors_selected = eigenvectors_sorted[:, :k]
```

### 6. Project Data

Project the centered data onto the selected eigenvectors to reduce dimensions.

```
transformed_data = centered_data.dot(eigenvectors_selected)
```

### 7. Visualization

Plot the transformed data to visualize in reduced dimensions.

```
import matplotlib.pyplot as plt
plt.scatter(transformed_data[:, 0], transformed_data[:, 1])
plt.show()
```

### Conclusion

PCA helps reduce dimensionality and retain the most significant features in data. It’s useful for visualization, noise reduction, and preprocessing before machine learning.
