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
# Install pre-commit
pip install pre-commit

# Set up hooks
pre-commit install
# Run all tests
pytest

# Run specific test file
pytest tests/test_data_processing.py

# Run with coverage
pytest --cov=src tests/
# Format code with black
black src/ tests/

# Sort imports with isort
isort src/ tests/

# Check code quality
flake8 src/
def test_data_loading():
    from src.data.preprocessing import load_data
    df = load_data('sample.csv')
    assert not df.empty
    assert 'target' in df.columns
