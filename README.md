# Population Data Analysis

This project analyzes a dataset containing population data across various countries and continents. It visualizes the distribution of countries by continent using bar charts and the distribution of population for the year 2023 using histograms. The dataset provides insights into global population distribution, density, and growth trends.

## Dataset

The dataset used contains the following columns:

- **rank**: Rank of the country based on population.
- **cca3**: ISO 3166-1 alpha-3 country codes.
- **country**: Name of the country.
- **continent**: Continent where the country is located.
- **2023 population**: Population of the country in 2023.
- **2022 population**: Population of the country in 2022.
- **2020 population**: Population of the country in 2020.
- **2015 population**: Population of the country in 2015.
- **2010 population**: Population of the country in 2010.
- **2000 population**: Population of the country in 2000.
- **1990 population**: Population of the country in 1990.
- **1980 population**: Population of the country in 1980.
- **1970 population**: Population of the country in 1970.
- **area (km²)**: Area of the country in square kilometers.
- **density (km²)**: Population density per square kilometer.
- **growth rate**: Population growth rate.
- **world percentage**: Percentage of the world's population.

## Project Structure

- `README.md`: Project documentation file.
- `population_analysis.ipynb`: Main Jupyter notebook for data analysis and visualization.
- `dataset.csv`: Source dataset containing population data for each country.

## Requirements

To run this project, you need the following Python libraries installed:

- `pandas`
- `matplotlib`
- `seaborn`

These libraries are generally pre-installed in Kaggle notebooks. If running locally, install them using:

```bash
pip install pandas matplotlib seaborn
```

## Analysis Steps

1. **Load the Dataset**: Load the dataset using Pandas and inspect the first few rows and columns.
2. **Bar Chart - Countries by Continent**: Create a bar chart showing the number of countries by continent.
3. **Histogram - 2023 Population**: Create a histogram to display the distribution of the population for the year 2023.

## Code Examples

### 1. Bar Chart - Number of Countries by Continent

This bar chart visualizes the number of countries within each continent.

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv('dataset.csv')

# Count countries by continent
continent_counts = df['continent'].value_counts().reset_index()
continent_counts.columns = ['Continent', 'Number of Countries']

# Plot
plt.figure(figsize=(10, 6))
sns.barplot(x='Continent', y='Number of Countries', data=continent_counts, palette='Set2')
plt.title('Number of Countries by Continent')
plt.xlabel('Continent')
plt.ylabel('Number of Countries')
plt.xticks(rotation=45)
plt.show()
```

### 2. Histogram - Distribution of 2023 Population

This histogram shows the distribution of populations in 2023 across countries.

```python
plt.figure(figsize=(10, 6))
sns.histplot(df['2023 population'], bins=20, kde=True, color='skyblue')
plt.title('Distribution of 2023 Population')
plt.xlabel('Population')
plt.ylabel('Frequency')
plt.grid(axis='y')
plt.show()
```

## Results

- **Countries by Continent**: Shows how countries are distributed across continents.
- **2023 Population Distribution**: Displays the population distribution and highlights countries with larger populations.

## License

This project is open-source and available under the MIT License.

## Acknowledgments

Thanks to [Kaggle](https://www.kaggle.com/) for providing an interactive environment for data analysis.

