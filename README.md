# Analysing Fandango Movie Ratings

## Project Overview

In 2015, data journalist **Walt Hickey** published an investigation suggesting that **Fandango's movie ratings were artificially inflated**, with many films displaying higher star ratings than their underlying numerical scores. This project recreates and evaluates that investigation using publicly available movie rating data from **FiveThirtyEight**.

Using Python, Pandas, and Matplotlib, the project compares Fandango's ratings with IMDb, Rotten Tomatoes, and Metacritic to determine whether statistical evidence supports the claim of rating bias.

---

## Dataset Information

**Dataset:** FiveThirtyEight – Fandango Movie Ratings

The project uses two datasets:

### 1. fandango_score_comparison.csv

Contains movie ratings from multiple review platforms for 146 films released in 2015.

Platforms included:

- Fandango
- IMDb
- Rotten Tomatoes
- Metacritic

The dataset also includes normalised ratings on a common 0–5 scale for fair comparison.

### 2. fandango_scrape.csv

Contains 510 movies scraped directly from the Fandango website, including:

- Displayed star ratings
- Hidden numerical ratings
- Vote counts

This dataset supports the investigation into how ratings were displayed on the Fandango website.

---

# Project Objectives

The project aimed to:

- Understand the rating scales used by different movie review platforms.
- Compare Fandango's displayed star ratings with the underlying numerical ratings.
- Compare Fandango's ratings with IMDb, Rotten Tomatoes, and Metacritic.
- Visualise rating distributions across review platforms.
- Determine whether statistical evidence supports the claim that Fandango's ratings were biased.

---

# Tools & Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Jupyter Notebook

---

# Project Workflow

## 1. Data Loading

Both datasets were imported into Python using Pandas before exploring their structure and contents but, the scrape dataset was not used in this project.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

fandango = pd.read_csv("fandango_score_comparison.csv")
scrape = pd.read_csv("fandango_scrape.csv")
```

Dataset dimensions and data types were inspected to understand the available variables.

---

## 2. Understanding the Rating Scales

Each review platform originally used different rating systems.

| Platform | Original Scale | Normalised Scale Used |
|-----------|---------------:|----------------------:|
| Rotten Tomatoes | 0–100 | 0–5 |
| Metacritic | 0–100 | 0–5 |
| IMDb | 0–10 | 0–5 |
| Fandango | 0–5 | 0–5 |

The normalised columns enabled direct comparisons between all platforms.

---

# Analysis

## Fandango Displayed Ratings vs Hidden Rating Values

The project investigated the difference between:

- Displayed Star Rating
- Underlying Numerical Rating

using the following variables:

- `Fandango_Stars`
- `Fandango_Ratingvalue`
- `Fandango_Difference`

### Visualisation

A bar chart was produced showing the distribution of rating differences.

### Findings

- Displayed ratings were never lower than the underlying rating.
- Most films displayed ratings between **0.1** and **0.4** stars higher than the hidden numerical score.
- Very few films showed no difference between the two values.

This indicates that Fandango consistently rounded ratings upwards when presenting them to users.

---

## Comparing Review Platforms

The normalised ratings from each platform were compared:

- Fandango
- IMDb
- Rotten Tomatoes
- Metacritic

### Average Ratings

| Platform | Average Rating |
|-----------|---------------:|
| Fandango | **3.85** |
| IMDb | **3.37** |
| Rotten Tomatoes | **3.04** |
| Metacritic | **2.94** |

### Findings

Fandango produced the highest average movie ratings across all four review platforms.

The difference between Fandango and Metacritic approached one full star on the normalised five-point scale.

---

# Visualisations

Three visualisations were created to compare the review platforms.

## 1. Average Movie Rating by Review Platform

Purpose:

- Compare average ratings across all review platforms.

Finding:

- Fandango consistently reported higher average ratings than competing websites.

---

## 2. Rating Distribution (Box Plot)

Purpose:

- Compare the spread and variability of ratings.

Finding:

- Fandango ratings were concentrated around higher values with relatively little variation.
- Rotten Tomatoes and Metacritic displayed much broader distributions with lower median ratings.

---

## 3. Rating Density Comparison

Purpose:

- Compare the overall distribution of ratings.

Finding:

- Fandango's rating distribution was shifted noticeably towards higher ratings.
- IMDb occupied a middle position.
- Rotten Tomatoes and Metacritic showed greater variation and lower overall ratings.

---

# Evidence of Rating Bias

The analysis provides strong evidence supporting Walt Hickey's original investigation.

Key observations include:

- Fandango consistently reported higher average ratings than IMDb, Rotten Tomatoes, and Metacritic.
- Displayed star ratings were systematically equal to or higher than the underlying numerical ratings.
- Most displayed ratings exceeded the hidden rating value by between **0.1** and **0.4** stars.
- Rating distributions were concentrated around four stars, while competing review platforms displayed broader and generally lower rating distributions.

Although the analysis cannot determine why the differences occurred, the statistical evidence indicates that Fandango presented films more favourably than competing review platforms during the period analysed.

---

# Key Findings

- Fandango recorded the highest average rating (**3.85/5**) of all review platforms.
- IMDb produced the second-highest average rating (**3.37/5**).
- Rotten Tomatoes (**3.04/5**) and Metacritic (**2.94/5**) were considerably more conservative.
- Displayed Fandango star ratings were consistently higher than their underlying numerical ratings.
- Distribution analysis further supported the conclusion that Fandango ratings exhibited a positive bias.

---

# Skills Demonstrated

## Python

- Data manipulation
- Data exploration
- Statistical comparison
- Feature analysis

## Pandas

- DataFrame manipulation
- Summary statistics
- Data filtering
- Data comparison

## Data Visualisation

- Bar charts
- Box plots
- Density plots
- Distribution analysis

## Exploratory Data Analysis (EDA)

- Descriptive statistics
- Distribution comparison
- Cross-platform analysis
- Bias investigation

## Data Journalism

- Investigative data analysis
- Evidence-based conclusions
- Statistical storytelling
- Critical evaluation of published claims

---

# Conclusion

This project demonstrates how exploratory data analysis can be used to evaluate a real-world investigative journalism claim using publicly available data. By comparing movie ratings across multiple review platforms, the analysis found consistent evidence that Fandango's displayed ratings were systematically more favourable than both their underlying numerical values and competing review websites. The project highlights the importance of transparent data presentation and demonstrates practical skills in statistical analysis, data visualisation, and evidence-based decision making.

---



## Author

**Steven Tapscott**

This project forms part of my Data Analytics & Data Science portfolio, demonstrating practical Python skills in exploratory data analysis, statistical comparison, data visualisation, and investigative analytics using real-world datasets.
