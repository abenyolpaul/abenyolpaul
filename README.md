## Hi there 👋
✅ Task 1: Load and Explore the Dataset
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris

# Load Iris dataset
try:
    iris = load_iris()
    df = pd.DataFrame(data=iris.data, columns=iris.feature_names)
    df['species'] = pd.Categorical.from_codes(iris.target, iris.target_names)
    print("✅ Dataset loaded successfully.\n")
except Exception as e:
    print(f"❌ Error loading dataset: {e}")

# Display first few rows
print("📄 First 5 rows of the dataset:")
print(df.head())

# Check data types and missing values
print("\n🔍 Data types:")
print(df.dtypes)

print("\n🧼 Missing values:")
print(df.isnull().sum())

# Clean dataset (no missing values in Iris, but here's how you'd handle it)
df_cleaned = df.dropna()

✅ Task 2: Basic Data Analysis
# Basic statistics
print("\n📊 Basic statistics:")
print(df_cleaned.describe())

# Group by species and compute mean of numerical columns
grouped = df_cleaned.groupby("species").mean()
print("\n📈 Mean values grouped by species:")
print(grouped)

# Interesting finding
print("\n💡 Insight:")
print("Setosa has significantly smaller petal length and width compared to Versicolor and Virginica.")

 ✅ Task 3: Data Visualization
       # Set style
sns.set(style="whitegrid")

# Line chart: simulate time-series by plotting petal length over index
plt.figure(figsize=(8, 5))
plt.plot(df_cleaned.index, df_cleaned["petal length (cm)"], label="Petal Length")
plt.title("📈 Petal Length Trend Over Index")
plt.xlabel("Index")
plt.ylabel("Petal Length (cm)")
plt.legend()
plt.tight_layout()
plt.show()

# Bar chart: average petal length per species
plt.figure(figsize=(8, 5))
sns.barplot(x="species", y="petal length (cm)", data=df_cleaned, ci=None)
plt.title("📊 Average Petal Length by Species")
plt.xlabel("Species")
plt.ylabel("Petal Length (cm)")
plt.tight_layout()
plt.show()

# Histogram: distribution of sepal length
plt.figure(figsize=(8, 5))
sns.histplot(df_cleaned["sepal length (cm)"], bins=20, kde=True)
plt.title("📉 Distribution of Sepal Length")
plt.xlabel("Sepal Length (cm)")
plt.ylabel("Frequency")
plt.tight_layout()
plt.show()

# Scatter plot: sepal length vs petal length
plt.figure(figsize=(8, 5))
sns.scatterplot(x="sepal length (cm)", y="petal length (cm)", hue="species", data=df_cleaned)
plt.title("🔬 Sepal Length vs Petal Length")
plt.xlabel("Sepal Length (cm)")
plt.ylabel("Petal Length (cm)")
plt.legend(title="Species")
plt.tight_layout()
plt.show()










