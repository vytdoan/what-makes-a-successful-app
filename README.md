# Google Play Store Data Analysis

## Overview

This project explores **what makes an app successful on the Google Play Store** using a dataset of more than 10,000 Android applications.

The analysis looks at factors such as **category, pricing, ratings, app size, target audience, and update activity** to see how they relate to app installs and overall performance.

The full analysis is available in:

`GooglePlayStoreAnalysis.ipynb`

---

## Project Objective

The main question behind this project is:

> **What characteristics are associated with a successful Google Play Store app?**

The analysis focuses on questions such as:

- Do higher ratings lead to more installs?
- Which app characteristics are most related to download performance?
- Do free apps get more installs than paid apps?
- Which categories are more suitable for paid apps?
- What price ranges perform better for paid apps?
- How does target audience relate to installs?
- Which categories have high popularity but lower ratings?
- Which app categories appear to be updated more frequently?

---

## Dataset

The project uses the **Google Play Store Apps** dataset originally sourced from Kaggle.

The original dataset contains:

- **10,841 rows**
- **13 attributes**
- **34 app categories**
- Free and paid applications
- Data collected through **August 2018**

Some of the main variables include:

- App
- Category
- Rating
- Reviews
- Size
- Installs
- Type
- Price
- Content Rating
- Genres
- Last Updated
- Current Version
- Android Version

After cleaning and removing duplicate or invalid records, the dataset contains approximately **9,659 unique apps**.

---

## Data Cleaning

Before starting the analysis, the dataset was cleaned and prepared for use.

### Main cleaning steps

1. **Removed a corrupt record**
   - One row contained values that were shifted into the wrong columns and could not be reliably recovered.

2. **Removed duplicate apps**
   - Duplicate apps were sorted by review count.
   - The record with the highest number of reviews was kept.

3. **Converted installs to numeric values**
   - Removed commas and `+` symbols.

4. **Converted prices to numeric values**
   - Removed `$` symbols.

5. **Standardized app size**
   - Converted megabyte and kilobyte values into a consistent numeric format.
   - `"Varies with device"` values were treated as missing.

6. **Handled missing values**
   - Rows were kept when they still contained useful information.
   - Missing values were excluded only when required for a specific analysis.

---

## Analysis

The project is divided into four main areas.

### 1. Data Quality & Outlier Analysis

The first part looks at the distributions of:

- Ratings
- Reviews
- Installs
- App size
- Price

This helps identify unusual values and understand how skewed the Google Play Store data is before moving into deeper analysis.

---

### 2. What Drives App Success?

This section looks at which app characteristics are most related to installs.

The analysis includes:

- Correlation between app metrics
- Regression analysis of install drivers
- Combined effects of multiple app characteristics
- Compounding effects of favorable success factors

One important finding is that **ratings and installs have only a weak correlation**. A highly rated app does not necessarily have a large number of installs.

The full model explains roughly **25% of the variation in log installs**. This suggests that other factors not included in the dataset, such as marketing, brand recognition, promotion, and app store optimization, may also play a major role in app success.

---

### 3. Pricing Strategy

This section compares free and paid apps to see how pricing relates to market reach.

The analysis looks at:

- Categories with a meaningful number of paid apps
- Performance of free versus paid apps
- Possible price ranges for paid apps

Overall, **free apps tend to reach significantly more users than paid apps**.

Among the categories analyzed, **Personalization** appears to be one of the stronger categories for experimenting with a paid model.

Within this category, the `$2 to $3` price range performs relatively well among price groups with enough observations. This does not mean it is automatically the best price, but it may be a useful range to test.

---

### 4. Market & Audience Positioning

The final section looks at how app category and target audience relate to performance.

The analysis includes:

- Median installs by content rating
- App quality versus popularity by category
- Category and target audience combinations
- Update activity across categories

The results show that there is **no single best content rating for every type of app**. Performance depends heavily on the app category.

The analysis also shows differences in update frequency between categories. This may reflect different levels of competition and different expectations for app maintenance.

---

## Visualizations

The notebook includes **11 main charts**:

1. Distribution of key app metrics
2. Correlation between app metrics
3. Factors related to app installs
4. Compounding effects of success factors
5. Categories that support paid pricing
6. Paid versus free app performance
7. Paid app price point analysis
8. Median installs by target audience
9. App quality versus popularity by category
10. Installs by category and content rating
11. Market momentum based on update recency

The visualizations are created mainly with **Matplotlib** and **Seaborn**.

---

## Key Findings

Some of the main findings from the analysis are:

- **Ratings alone are not a strong predictor of installs.**
- Category, pricing model, app size, and update activity help explain differences in app performance.
- **Free apps generally receive far more installs than paid apps.**
- Multiple favorable app characteristics can work together and have a stronger relationship with installs.
- Target audience performance depends heavily on the app category.
- Some categories have high download activity but relatively lower ratings, which may suggest opportunities for better-quality competitors.
- Update frequency varies between categories and may reflect different levels of competition and maintenance requirements.

---

## Technologies Used

The project was completed in **Python** using:

- Python
- Jupyter Notebook / Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

## Repository Structure

```text
.
├── GooglePlayStoreAnalysis.ipynb
└── README.md
```

The notebook also generates a cleaned dataset during preprocessing:

```text
googleplaystore_cleaned.csv
```

---

## How to Run the Project

### Option 1: Jupyter Notebook

Clone the repository:

```bash
git clone <your-repository-url>
cd <repository-name>
```

Install the required packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
GooglePlayStoreAnalysis.ipynb
```

Then run the notebook cells in order.

### Option 2: Google Colab

Upload `GooglePlayStoreAnalysis.ipynb` to Google Colab and run the cells in order.

The notebook includes a Google Colab file upload step for loading the raw dataset.

---

## Limitations

There are several limitations to keep in mind when interpreting the results:

- **Dataset age:** The dataset represents the Google Play Store as of August 2018, so the results may not represent the current app market.
- **Install counts:** Install values are given as ranges such as `1,000,000+` instead of exact download totals.
- **Missing factors:** The dataset does not include information such as marketing spend, brand recognition, user retention, advertising, or app store promotion.
- **Ratings:** Ratings are useful, but they do not fully represent app quality or user engagement.
- **Revenue:** Price and install data cannot fully represent revenue because apps may also earn money through ads, subscriptions, and in-app purchases.

---

## Future Improvements

Some possible ways to expand the project include:

- Using a more recent Google Play Store dataset
- Adding revenue and monetization data
- Including retention and engagement metrics
- Performing sentiment analysis on user reviews
- Studying competition within specific categories
- Adding marketing and brand-related variables
- Building a predictive model for app installs
- Comparing Google Play Store apps with Apple's App Store

---

## Team

**Group 11**

- Vy Doan
- Zane Bergen
- Liuling Guo
- Pei Chun Huang
- Nhung Collier

---

### AI Usage

AI tools were used to support parts of the project, including:

- Identifying possible data quality issues
- Assisting with Python development and debugging
- Exploring visualization ideas
- Reviewing analytical logic
- Helping organize findings and explanations

Final analytical decisions and interpretations were made by the project team.

---

## Disclaimer

This project was created for **educational and exploratory data analysis purposes**. Since the dataset is from 2018 and has several limitations, the findings should not be treated as current business, investment, or app launch advice.