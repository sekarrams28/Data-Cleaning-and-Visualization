# 🌦️ Weather Data Cleaning & Visualization

A Python-based data analytics project that collects real-world weather forecast data from the **Open-Meteo API**, performs data cleaning and preprocessing, conducts exploratory data analysis (EDA), and generates meaningful visualizations using **Pandas, Matplotlib, and Seaborn**.

The complete analysis is implemented in a **Jupyter Notebook**.

---

## 📌 Project Overview

Raw data is rarely ready for analysis. This project demonstrates an end-to-end workflow for transforming real-world API data into a clean, structured dataset and extracting meaningful insights from it.

### Workflow

```text
Open-Meteo API
      │
      ▼
Data Collection
      │
      ▼
Pandas DataFrame
      │
      ▼
Data Inspection
      │
      ▼
Data Cleaning
 ┌────┼─────────────┐
 ▼    ▼             ▼
Missing Values   Duplicates   Outliers
      │
      ▼
Feature Engineering
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Data Visualization
      │
      ▼
Insights & Findings
      │
      ▼
Cleaned Dataset
```

---

## 🎯 Objectives

The project aims to:

- Collect real-world weather data through an API
- Inspect and understand the dataset
- Handle missing values
- Detect and remove duplicate records
- Identify potential outliers using the IQR method
- Perform datetime processing
- Create new analytical features
- Perform exploratory data analysis
- Analyze weather patterns
- Study correlations between variables
- Create informative visualizations
- Export the processed dataset for further use

---

## 📊 Dataset

The project uses the **Open-Meteo Weather API**.

The API provides weather forecast information without requiring an API key.

### Location

**Chennai, India**

Coordinates used:

```text
Latitude  : 13.0827
Longitude : 80.2707
```

### Data collected

The project retrieves hourly forecast data for:

- Temperature
- Relative Humidity
- Precipitation
- Wind Speed
- Date and Time

The notebook can easily be modified to analyze another location by changing the latitude and longitude.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Jupyter Notebook | Development and analysis environment |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical computing |
| Requests | API data collection |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| Open-Meteo API | Weather data source |

---

## 🧹 Data Cleaning

The project performs several data-cleaning operations.

### Missing Values

Missing values are identified using Pandas:

```python
df.isnull().sum()
```

Numerical missing values are handled using median imputation.

### Duplicate Records

Duplicate rows are identified and removed:

```python
df.drop_duplicates()
```

### Datetime Processing

The API timestamp is converted into a Pandas datetime object:

```python
df["datetime"] = pd.to_datetime(df["datetime"])
```

Additional features are extracted:

- Date
- Hour
- Day
- Day number

### Outlier Detection

Potential outliers are detected using the **Interquartile Range (IQR)** method.

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Outliers are identified for:

- Temperature
- Humidity
- Precipitation
- Wind Speed

Outliers are analyzed rather than blindly removed because extreme weather values can be legitimate observations.

---

## 🔍 Exploratory Data Analysis

The project investigates several aspects of the weather data.

### Temperature Analysis

- Average temperature
- Maximum temperature
- Minimum temperature
- Daily temperature trends
- Hourly temperature patterns
- Temperature distribution

### Humidity Analysis

- Average humidity
- Humidity trends
- Relationship between humidity and temperature

### Precipitation Analysis

- Total precipitation
- Hourly precipitation
- Daily rainfall

### Wind Analysis

- Average wind speed
- Maximum wind speed
- Wind speed trends

### Correlation Analysis

The project analyzes relationships between:

```text
Temperature
Humidity
Precipitation
Wind Speed
```

using a correlation matrix and heatmap.

---

## 📈 Visualizations

The notebook generates:

- Temperature trend chart
- Humidity trend chart
- Precipitation chart
- Wind speed chart
- Daily temperature analysis
- Daily rainfall analysis
- Hourly temperature pattern
- Temperature distribution
- Temperature vs. humidity scatter plot
- Weather-variable correlation heatmap
- Box plots for outlier detection

---

## 📁 Project Structure

```text
weather-data-cleaning-visualization/
│
├── Weather_Data_Cleaning_Visualization.ipynb
├── cleaned_weather_data.csv
├── requirements.txt
├── .gitignore
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/weather-data-cleaning-visualization.git
```

### 2. Navigate to the project

```bash
cd weather-data-cleaning-visualization
```

### 3. Create a virtual environment

Windows:

```bash
python -m venv venv
```

Activate it:

```bash
venv\Scripts\activate
```

Linux/macOS:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🚀 Running the Project

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Weather_Data_Cleaning_Visualization.ipynb
```

Run the notebook from top to bottom.

The notebook automatically:

1. Connects to the Open-Meteo API
2. Retrieves weather data
3. Creates a Pandas DataFrame
4. Inspects the dataset
5. Cleans the data
6. Detects potential outliers
7. Performs feature engineering
8. Conducts exploratory analysis
9. Generates visualizations
10. Produces analytical insights
11. Exports the cleaned dataset

---

## 📤 Output

The project produces a cleaned CSV dataset:

```text
cleaned_weather_data.csv
```

This dataset can be used for:

- Further statistical analysis
- Machine learning
- SQL-based analysis
- Data engineering pipelines
- Dashboard development

---

## 📊 Example Insights

The analysis can answer questions such as:

- What is the average temperature during the forecast period?
- What is the hottest expected time?
- What is the coldest expected time?
- Which days have the highest rainfall?
- How does humidity vary throughout the day?
- Is there a relationship between temperature and humidity?
- What are the unusual observations in the dataset?
- How does wind speed change over time?

---

## 🧠 Learning Outcomes

This project demonstrates practical knowledge of:

- Python programming
- Data collection through APIs
- Data preprocessing
- Data cleaning
- Missing-value handling
- Duplicate detection
- Outlier detection
- Feature engineering
- Exploratory Data Analysis
- Statistical analysis
- Data visualization
- Data storytelling
- Working with Jupyter Notebook

---

## 🔮 Future Improvements

The project can be extended into a larger data engineering and analytics pipeline.

### Planned improvements

- Collect historical weather data
- Analyze multiple cities
- Automate daily data collection
- Store data in PostgreSQL
- Build an ETL pipeline
- Add SQL-based analytics
- Create an interactive Streamlit dashboard
- Add machine-learning-based weather prediction
- Schedule automated data ingestion
- Deploy the analytics application

### Future Architecture

```text
Weather API
     ↓
Python ETL
     ↓
Data Validation
     ↓
PostgreSQL
     ↓
SQL Analytics
     ↓
Pandas
     ↓
Visualization
     ↓
Dashboard
```

---

## ⚠️ Data Source Note

The project uses weather **forecast data** retrieved from Open-Meteo. The API data is continuously updated, but the values represent forecasts rather than direct sensor observations.

For more information about the API, visit the official Open-Meteo documentation.

---

## 👨‍💻 Author

**Ram**

Data Analytics & Data Engineering Portfolio Project

---

## 📄 License

This project is intended for educational and portfolio purposes.