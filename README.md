# datafun-04-jupyter

# Overview
Project 4 uses Jupyter to perform exploratory data analysis and present data stories.

# Start a New Project in GitHub & Clone it
In your browser, create a GitHub project repository with a default README.md. Clone your new repository down to your machine where you want your root project folder to be by running the following:
```
git clone URL
```

# Add .gitignore file
Use VS Code to create a new file with the name .gitignore and add at least the following entries:
```
.venv/
.vscode/
```

# Add empty requirements.txt file
Create an empty txt file in your root project folder

# Edit README.md
Edit your README.md file to record your commands, process, and notes. Use one hash space for the title.

# Git Add / Commit / Push to GitHub
Use your terminal to add your files to source control, commit your changes to git, and push them up to GitHub by running the following:
```
git add .
git commit -m "initial commit"
git push origin main
```

# Create and Activate Project Virtual Environment
Use your terminal to create your project virtual environment by running venv as a Python module (python -m venv) and providing the name the destination folder for the project virtual environment as .venv by running the following:
```
py -m venv .venv
.venv\Scripts\Activate
```

# Install Packages into Active Environment
Windows command to install project dependencies:
```
py -m pip install jupyterlab pandas pyarrow matplotlib seaborn
```

# Update requirements.txt
Run the following:
```
python -m pip freeze > requirements.txt
```

# Git add / commit / push

# Import Dependencies
Import dependencies for the project
```
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
```

# Exploratory Data Analysis
1. Load the dataset:
```
df = sns.load_dataset('iris')
```

2. Inspect the data:
```
print(df.head(10))
print(df.shape)
print(df.dtypes)
```

3. Initial Descriptive Statistics
```
print(df.describe())
```

# Initial Data Distribution for Numerical Columns
```
# inspect histogram by numerical column
df['sepal_length'].hist()

# inspect histograms for all numerical columns
df.hist()

# display plot
plt.show()
```

# Initial Data Distribution for Categorical Columns
```
# inspect value counts by categorical column
df['species'].value_counts()

# inspect value counts for all categorical columns
for col in df.select_dtypes(include=['object', 'category']).columns:
    # display count plot
    sns.countplot(x=col, data=df)
    plt.title(f'Distribution of {col}')
    plt.show()

# display plots
plt.show()
```
# Provide Observation

# Initial Data Transformation and Feature Engineering
```
# renaming column
df.rename(columns={'sepal_length': 'Sepal Length'}, inplace=True)
df.rename(columns={'sepal_width': 'Sepal Width'}, inplace=True)
df.rename(columns={'petal_length': 'Petal Length'}, inplace=True)
df.rename(columns={'petal_width': 'Petal Width'}, inplace=True)

# adding new column
df['Sepal Area'] = df['Sepal Length'] * df['Sepal Width']
df['Petal Area'] = df['Petal Length'] * df['Petal Width']
```
# Provide Observation

# Initial Visualizations
```
sns.pairplot(df, hue='species')
plt.show()
```
# Provide Observation

# Relationship Between Sepal Area and Petal Area
```
plt.figure(figsize=(8, 6))
plt.scatter(df['Sepal Area'], df['Petal Area'], color='blue', alpha=0.5)
plt.title('Relationship between Sepal Area and Petal Area')
plt.xlabel('Sepal Area')
plt.ylabel('Petal Area')
plt.grid(True)
plt.show()
```
# Provide Observation
