# Citi Bike User Behavior Analysis (January 2020)

## 📌 Project Overview
This project explores user riding behavior in New York City’s Citi Bike bike-share system using trip-level data from January 2020. The analysis focuses on how rider demographics, particularly age and gender relate to riding speed and usage patterns.

The goal of this project is to demonstrate exploratory data analysis, visualization, and insight generation using real-world transportation data.

**Key questions explored:**
- How does average riding speed change with age?
- Are there observable differences in riding behavior by gender?
- What does the age distribution of Citi Bike users look like?


## Dataset
- **Source:** Citi Bike public trip history data (January 2020)
- **Observations:** ~100,000 trips (subset for performance)
- **Key variables:**
  - Trip duration
  - Start and end station coordinates
  - Rider age
  - Rider gender

To improve performance and clarity, a subset of the original dataset was used while preserving overall distribution patterns.



## Methodology
The analysis followed a structured exploratory workflow:

1. **Data Loading & Inspection**
   - Imported trip-level data using tidyverse tools
   - Verified data structure, variable types, and missing values

2. **Feature Engineering**
   - Calculated trip distance using straight-line (geodesic) distance between stations
   - Derived average riding speed (meters/second)
   - Filtered extreme or implausible values (e.g., ages over 80–100)

3. **Data Grouping**
   - Aggregated average speed by age
   - Extended aggregation to include gender as a categorical variable
   - Converted numeric gender codes into factors for correct visualization

4. **Visualization**
   - Line charts to examine trends in average speed
   - Stacked bar charts to analyze demographic distribution



## 📊 Exploratory Analysis & Insights

### 1️⃣ Average Speed by Age
<img width="1344" height="960" alt="unnamed-chunk-10-1" src="https://github.com/user-attachments/assets/1cac314b-295b-4484-9a06-297bc64e59f0" />


**Key insights:**
- Average riding speed generally declines as age increases
- Younger riders (roughly ages 20–35) exhibit the highest average speeds
- Speed variation increases at older ages, suggesting smaller sample sizes and greater sensitivity to noise

This pattern aligns with expected differences in physical ability and riding behavior across age groups.



### 2️⃣ Average Speed by Age and Gender

<img width="1344" height="960" alt="unnamed-chunk-14-1" src="https://github.com/user-attachments/assets/3b8be826-137c-475a-b544-bfc53aae0d80" />

**Key insights:**
- Male-identifying users tend to ride slightly faster than female-identifying users across most age groups
- Despite level differences, both groups follow a similar age-related trend: speeds peak in early adulthood and gradually decline
- At older ages, trends become more volatile, indicating reduced sample sizes and higher uncertainty

These findings suggest that while gender differences exist, age plays a more consistent role in shaping riding behavior.


### 3️⃣  Age Distribution of Citi Bike Users
<img width="1695" height="1047" alt="image" src="https://github.com/user-attachments/assets/be26f1f3-50c4-4200-96e8-6646d1b6924c" />


**Key insights:**
- Citi Bike usage is concentrated among users between their mid-20s and early-40s
- Male-identifying users make up a larger share of riders across most age groups
- Female-identifying users follow a similar distribution shape but with lower overall counts

Understanding who uses the service provides important context for interpreting speed and behavior differences observed earlier.



## Overall Insights
- Riding speed decreases gradually with age across the user base
- Gender-based differences in average speed exist but are secondary to age-related trends
- Citi Bike users are primarily young to middle-aged adults, which likely shapes overall system usage patterns



## Limitations and Future Work
- **Distance estimation:** Trip distance was calculated using straight-line distance between stations, which likely underestimates true travel distance and affects speed calculations. Future work could incorporate routing data from mapping APIs for greater accuracy.
- **Temporal scope:** This analysis focuses on a single month. Extending the study across multiple months or seasons could reveal weather effects, commuting patterns, and seasonal demand.
- **Additional data sources:** Integrating membership type, trip frequency, or real-time station data could enable deeper analysis of user behavior and system efficiency.



## Tools & Technologies
- R
- tidyverse (dplyr, ggplot2)
- RMarkdown


