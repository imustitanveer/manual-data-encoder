# ManualDataCoder

A tool for manually encoding and labeling individual values in dataset columns.

## Overview
This repository includes a Python notebook that allows you to load data, find unique values in each column, and manually encode them numerically. It provides a straightforward way to handle categorical data by assigning numerical codes to different categories.

## Dataset
The dataset used in this repository is "Mental Health Trends in the Age of Social Media" by Syed Anwar, created in January 2024, and sourced from Kaggle.

## Features
- Load the dataset into a Pandas DataFrame.
- Display the DataFrame to verify it is loaded correctly.
- Find and count the unique values in specific columns.
- Encode categorical values numerically.
- Save the updated DataFrame to a new CSV file.

## Usage
Below are snippets illustrating how to use the features in the Python notebook:

### Load the Data
```python
import pandas as pd

# Load the CSV data into a DataFrame
df = pd.read_csv('smmh.csv')

# Display the DataFrame to verify it's loaded correctly
print(df)
```

### Find Unique Values
```python
unique_values = df['3. Relationship Status'].unique()  # This gets the unique values
unique_count = df['3. Relationship Status'].nunique()  # This counts the number of unique values

print(f"Number of distinct values in the column: {unique_count}")
print("Unique values in the column:", unique_values)
```

### Encode Values Numerically
```python
# Replace 'Male' with 0 and 'Female' with 1 and so on, in the 'Gender' column
df['2. Gender'] = df['2. Gender'].replace({'Male': 0, 'Female': 1, 'Nonbinary': 2, 'Non-binary': 2, 'NB': 2, 'Non binary': 2, 'Trans': 3, 'unsure': 4})

# Save the updated DataFrame back to a CSV file
df.to_csv('coded_dataset.csv', index=False)

# Print the updated DataFrame to verify changes
print(df)
```

## Included Files
- `manual_data_coder.ipynb`: The Jupyter notebook containing the code.
- `smmh.csv`: The original dataset file.

## License
This project is licensed under the MIT License.

## Acknowledgements
- Dataset by Syed Anwar, "Mental Health Trends in the Age of Social Media," January 2024, Kaggle.
```

This `README.md` file provides an overview of the repository, the dataset used, features, usage instructions with code snippets, included files, and acknowledgements.
