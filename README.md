# EDA_BANKING
An Exploratory Data Analysis (EDA) project on public banking data involves examining, cleaning, and visualizing openly available banking datasets to uncover patterns, trends, and anomalies. Understand customer behavior, transaction patterns, deposit trends, or risk indicators in the banking sector using publicly available data.


Step 1 — Define the Business Problem


Step 2 — Data Acquisition & Loading

Action	                                                                 Code / Tool
Load CSV / Excel / DB	                                                   pd.read_csv(), pd.read_excel(), pd.read_sql()
Check shape	                                                             df.shape → e.g., (10000, 23)
Preview data	                                                           df.head(), df.tail()
Check column types	                                                     df.info()
Summary statistics                                                       df.describe()


Step 3 — Data Quality Check & Cleaning
This is the most time-consuming phase (~40–60% of effort):

Missing values
df.isnull().sum()          # count per column
df.isnull().sum().sum()    # total missing


Step-4 
Duplicates
df.duplicated().sum()
df.drop_duplicates(inplace=True)

Outlier detection

Step 5 — Bivariate & Multivariate Analysis
Understand relationships between variables:

Correlation Matrix
sns.heatmap(df.corr(), annot=True, cmap='coolwarm', center=0)
plt.title("Feature Correlation Heatmap")
plt.show()

Look for features highly correlated with the target (e.g., balance vs Exited).
Scatter Plots (numerical vs numerical)
sns.scatterplot(x='age', y='balance', hue='Exited', data=df)

Grouped Bar / Box Plots (categorical vs numerical)
sns.boxplot(x='product', y='balance', data=df)

Pivot Tables
pd.crosstab(df['occupation'], df['Exited'], normalize='index')



  
