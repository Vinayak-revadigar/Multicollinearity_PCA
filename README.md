# Multicollinearity_PCA
"Exploring the Variance Retained: A Comparative Analysis of PCA on Multicollinear and Non-Multicollinear Datasets"

Process Flow
1. We import the necessary libraries: `numpy` for numerical operations and `PCA` from `sklearn.decomposition` for performing Principal Component Analysis.

2. We set a random seed using `np.random.seed(0)` to ensure reproducibility of results.

3. We define the number of samples (`n_samples`) and the number of features (`n_features`) for our dataset.

4. We create a correlation matrix using the `correlation_matrix` variable. This matrix represents the correlations between features in the dataset. In this case, we have a strong positive correlation between all pairs of features, with correlation coefficients ranging from 0.6 to 1.0.

5. We generate a random dataset (`multicollinear_data`) based on the correlation matrix using the `np.random.multivariate_normal` function. This function generates samples from a multivariate normal distribution.

6. We initialize the PCA object (`pca_multicollinear`) with `n_components=2`, indicating that we want to retain only 2 principal components.

7. We fit the PCA model to the multicollinear dataset using `pca_multicollinear.fit(multicollinear_data)`. This step calculates the principal components and their corresponding explained variances.

8. We calculate the variance retained by summing the explained variances of the selected principal components (`pca_multicollinear.explained_variance_ratio_`) and store it in the variable `variance_retained_multicollinear`.

9. Next, we move on to generating a non-multicollinear dataset. We again set the random seed and define the number of samples and features.

10. We generate a random dataset (`non_multicollinear_data`) using the `np.random.rand` function. This dataset contains uncorrelated features, as we generate random values between 0 and 1 for each feature.

11. We initialize another PCA object (`pca_non_multicollinear`) with `n_components=2` for the non-multicollinear dataset.

12. We fit the PCA model to the non-multicollinear dataset using `pca_non_multicollinear.fit(non_multicollinear_data)`.

13. We calculate the variance retained for the non-multicollinear dataset by summing the explained variances of the selected principal components (`pca_non_multicollinear.explained_variance_ratio_`) and store it in the variable `variance_retained_non_multicollinear`.

14. Finally, we create a dictionary (`variance_retained_dict`) to store the variance retained for each dataset, with keys representing the dataset names and values representing the variance retained.

15. We print the variance retained for two components for each dataset using a loop and the `variance_retained_dict`. This provides a comparison of the variance retained between the multicollinear and non-multicollinear datasets.

This code demonstrates the process of generating and analyzing two datasets: one with strong multicollinearity and another with uncorrelated features. The PCA is performed on both datasets, and the variance retained is calculated to compare the effectiveness of PCA in capturing the original information in the data.

