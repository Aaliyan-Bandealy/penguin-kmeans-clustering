# Penguin Species Clustering using K-Means

##  Project Overview

This project applies **K-Means clustering** to the Palmer Penguins dataset to identify natural groupings based on physical characteristics.

Using unsupervised machine learning, penguins are segmented into clusters based on measurable biological features such as:

- Culmen Length (mm)
- Culmen Depth (mm)
- Flipper Length (mm)
- Body Mass (g)
- Categorical attributes (island, species, sex – encoded)

The objective is to demonstrate a complete clustering workflow including preprocessing, scaling, model selection, and cluster interpretation.

---

##  Objective

Unlike supervised learning, clustering does not use labeled outcomes.

The goals of this project are to:

- Identify natural structure in the dataset
- Determine the optimal number of clusters using the **Elbow Method**
- Apply K-Means clustering
- Interpret cluster characteristics using statistical summaries

---

##  Technologies Used

- Python
- Pandas
- Matplotlib
- Scikit-learn
- KMeans
- StandardScaler

---

##  Project Workflow

### 1️ Data Loading
- Loaded dataset from `penguins.csv`
- Inspected structure using `.head()` and `.info()`

---

### 2️ Feature Engineering
- Converted categorical variables into dummy variables using `pd.get_dummies()`
- Ensured binary encoding (0/1 format)

---

### 3️ Feature Scaling
- Applied `StandardScaler`
- Standardization ensures all features contribute equally to distance calculations

Since K-Means uses Euclidean distance, scaling is essential to prevent large-scale features from dominating clustering.

---

### 4️ Determining Optimal Number of Clusters

Used the **Elbow Method**:

- Ran K-Means for K = 1 to 9
- Recorded inertia (within-cluster sum of squared distances)
- Plotted inertia vs K
- Selected **K = 4** based on the elbow point

---

### 5️ Final Model Training

- Trained K-Means with `n_clusters = 4`
- Assigned cluster labels to each observation
- Appended cluster labels to the dataset

---

### 6️ Visualization

Generated scatter plot:

- X-axis: Cluster label
- Y-axis: Culmen Length
- Color-coded clusters

---

### 7️ Cluster Analysis

Computed average measurements per cluster:

```
stat_penguins = penguins_df[numeric_columns].groupby('label').mean()
```
This allows interpretation of biological differences between clusters.

---

##  Key Insights

- Four distinct clusters were identified
- Clear separation based on physical measurements
- Feature scaling significantly improves clustering stability
- Elbow Method provides a systematic way to select K

---
##  How To Run

### Install dependencies
```bash
pip install -r requirements.txt
```

### Run clustering script
```bash
python src/penguin_clustering.py
```
