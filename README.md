# Elevate-Labs-Task-5

README – Titanic Test Dataset Analysis (Complete Explanation)

This project performs Exploratory Data Analysis (EDA), data preprocessing, data cleaning, and visualization on the Titanic test.csv dataset.
The goal is to understand the data, clean it, prepare it for modeling, and visualize important patterns.

1️⃣ Importing Libraries
You imported the following libraries:
pandas → to load and handle tabular data
numpy → for numerical operations
matplotlib / seaborn → for graphs
warnings → to hide unnecessary warnings
These libraries are essential for any data analysis project.

2️⃣ Loading the Dataset
You loaded the Titanic test.csv dataset into a DataFrame:
df = pd.read_csv("test.csv")
You checked:
df.shape → 418 rows × 11 columns
df.head() → first few rows
df.columns → list of column names
df.size → total number of elements
df.index → index range
This helped you understand the basic structure of the data.

3️⃣ Exploratory Data Analysis (EDA)
✔ Checked data information using df.info()

This showed:
Which columns have missing values
What data types each column has
How many non-null values exist

✔ Descriptive statistics using:

df.describe(include="object") for categorical columns
df.describe(include="all") for full view
You learned:

Mean age ≈ 30

Fare range is large (0 to 512)

Name column has all unique values

Sex has two categories

Cabin has many missing values

4️⃣ Handling Missing Values

You found missing values in:

Age → 86 missing

Fare → 1 missing

Cabin → 327 missing

Then you fixed them:

✔ Filled missing Age with median
df['Age'] = df['Age'].fillna(df['Age'].median())

✔ Dropped Cabin column

Too many missing values, so it was removed.

✔ Filled missing Fare
df['Fare'] = df['Fare'].fillna(df['Fare'].median())


After this, the dataset had no missing values.

5️⃣ Data Cleaning & Preprocessing

You cleaned and standardized the data:

✔ Converted Age to integer
✔ Converted Fare to float
✔ Cleaned Name column (removed spaces)
✔ Cleaned Ticket column (uppercased and trimmed)
✔ Cleaned Sex column (capitalized “Male” / “Female”)
✔ Checked duplicates (found 0 duplicates)

This step made the dataset consistent and readable.

6️⃣ Feature Engineering

You created new useful columns:

✔ Age_Group

Child

Young

Adult

Senior

✔ Status

Added a column where every row has "Active"

These new columns help in visualization and understanding patterns in the data.

7️⃣ Visualizations (Graphs)

You used seaborn and matplotlib to visualize the dataset.

1️⃣ Pairplot

Shows relationships between:

Age

Fare

Pclass

SibSp

Parch

Status

Observations:

Higher fares usually belong to higher classes

Younger people appear more in certain groups

Pclass 1 passengers paid more

2️⃣ Histograms (Distribution Plots)
✔ Age Distribution

Most passengers are aged 20–40 years.

✔ Fare Distribution

Fare is right-skewed — many low fares, a few extremely high fares.

✔ Age by Sex

Shows how male and female passengers are spread across ages.

3️⃣ Boxplots
✔ Age vs Sex

Male and female have similar age ranges.

✔ Fare vs Pclass

Pclass 1 → expensive tickets

Pclass 3 → cheap tickets

Shows clear class differences.

4️⃣ Scatterplots
✔ Fare vs Age

Higher fare passengers are spread across all ages.

✔ Pclass vs Age

Shows passengers from all ages in each class.

8️⃣ Final Insights (Easy Explanation)

Most passengers are young adults.

Fare is not evenly distributed — rich passengers paid much more.

Pclass is strongly related to ticket price.

Age does not strongly decide survival but class and fare show patterns.

Cabin column is mostly empty, so it was removed.
