# applied-data-science
Practical data science projects, tools, and applications
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
df = pd.read_csv('data/raw/sample_data.csv')

# Basic exploration
print(df.info())
print(df.describe())

# Visualize distributions
fig, axes = plt.subplots(2, 2, figsize=(12, 8))
for idx, col in enumerate(df.select_dtypes(include=[np.number]).columns[:4]):
    ax = axes[idx // 2, idx % 2]
    sns.histplot(df[col], ax=ax, kde=True)
    ax.set_title(f'Distribution of {col}')
plt.tight_layout()
plt.show()
