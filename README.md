# CryptoClustering Challenge

Objective: Use Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

Part 1: Prepare the data
# Import required libraries and dependencies
# Load the data in# Use the `StandardScaler()` module from scikit-learn to normalize the data from the CSV fileto a Pandas DataFrame
# Display sample data
# Generate summary statistics
# Plot your data to see what's in your DataFrame

# Use the `StandardScaler()` module from scikit-learn to normalize the data from the CSV file
# Create a DataFrame with the scaled data
# Copy the crypto names from the original DataFrame
# Set the coin_id column as index
# Display the scaled DataFrame

Find the Best Value for k Using the Original Scaled DataFrame.
# Create a list with the number of k-values from 1 to 11
# Create an empty list to store the inertia values
# Create a for loop to compute the inertia with each possible value of k
# Inside the loop:
# 1. Create a KMeans model using the loop counter for the n_clusters
# 2. Fit the model to the data using `df_market_data_scaled
# 3. Append the model.inertia_ to the inertia list
# Create a dictionary with the data to plot the Elbow curve
# Create a DataFrame with the data to plot the Elbow curve
# Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
Summary: From the chart, it shows that the Elbow curve flattens out at k=4, indicating minishing returns in clustering quality, the best value for k should be 4.

Part 2: Cluster Cryptocurrencies with K-means Using the Original Scaled DataFrame
# Initialize the K-Means model using the best value for k
# Fit the K-Means model using the scaled DataFrame
# Predict the clusters to group the cryptocurrencies using the scaled DataFrame
# Print the resulting array of cluster values.
# Create a copy of the scaled DataFrame
# Add a new column to the copy of the scaled DataFrame with the predicted clusters
# Display the copy of the scaled DataFrame

# Create a scatter plot using hvPlot by setting
# `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`.
# Color the graph points with the labels found using K-Means and
# add the crypto name in the `hover_cols` parameter to identify
# the cryptocurrency represented by each data point.

Part 3: Optimize Clusters with Principal Component Analysis.
# Create a PCA model instance and set `n_components=3`.
# Use the PCA model with `fit_transform` to reduce the original scaled DataFrame
# down to three principal components.
# View the scaled PCA data
# Retrieve the explained variance to determine how much information
# can be attributed to each principal component.
# Create a new DataFrame with the PCA data.
# Copy the crypto names from the original scaled DataFrame
# Set the coin_id column as index
# Display the scaled PCA DataFrame

Part 4: Find the Best Value for k Using the Scaled PCA DataFrame
# Create a list with the number of k-values from 1 to 11
# Create an empty list to store the inertia values
# Create a for loop to compute the inertia with each possible value of k
# Inside the loop:
  # 1. Create a KMeans model using the loop counter for the n_clusters
  # 2. Fit the model to the data using `df_market_data_pca`
  # 3. Append the model.inertia_ to the inertia list
# Create a dictionary with the data to plot the Elbow curve
# Create a DataFrame with the data to plot the Elbow curve
# Plot a line chart with all the inertia values computed with
# the different values of k to visually identify the optimal value for k.
Summary: Cluster Cryptocurrencies with K-means Using the Scaled PCA DataFrame
# Initialize the K-Means model using the best value for k
# Fit the K-Means model using the PCA data
# Predict the clusters to group the cryptocurrencies using the scaled PCA DataFrame
# Print the resulting array of cluster values.
# Create a copy of the scaled PCA DataFrame
# Add a new column to the copy of the PCA DataFrame with the predicted clusters
# Display the copy of the scaled PCA DataFrame
# Create a scatter plot using hvPlot by setting
# `x="PC1"` and `y="PC2"`.
# Color the graph points with the labels found using K-Means and
# add the crypto name in the `hover_cols` parameter to identify
# the cryptocurrency represented by each data point.

Part 5: Visualize and Compare the Results
In this section, you will visually analyze the cluster analysis results by contrasting the outcome with and without using the optimization techniques.
# Composite plot to contrast the Elbow curves
# Create the Elbow plot for the original scaled data
# Create the Elbow plot for the PCA-transformed data
# Composite plot showing both Elbow dcurves
# Composite plot to contrast the clusters
# Scatter plot for the PCA-transformed data
# Composite plot showing both cluster visualizations
Summary: Two key impacts of using fewer features: reduced dimensionality and cluster separation. Reduced dimensionality through PCA simplifies the clustering process by focusing on the most important features (principal components) that explain most of the variance in the data. Cluster separation may be more compact with fewer features, but some detailed information might be lost compared to clustering using the original feature set.
