
**EDA & Data Visualization – Airbnb Listings**

---

## 📂 Overview
This project performs **Exploratory Data Analysis (EDA)** on an Airbnb dataset to uncover key patterns in pricing, availability, room types, reviews, and geospatial distribution of listings.

---

## 🛠️ Tools Used
- **Python**
- **Pandas** – for data wrangling
- **NumPy** – for numerical operations
- **Matplotlib / Seaborn** – for plotting
- **Jupyter Notebook** – for interactive data analysis

---

## 📈 Workflow Summary

### 1. **Data Loading & Initial Exploration**
- Dataset read using `pandas.read_csv()`
- Inspected with `.info()`, `.describe()`, `.isnull().sum()`

### 2. **Data Cleaning**
- Dropped null values and duplicates
- Converted `last_review` to datetime
- Cast `id` and `host_id` as object types
- Removed outliers in price (`price < 1500`)

### 3. **Univariate Analysis**
- Distribution plots for `price`, `availability_365`
- Count plots for `room_type`, `neighbourhood_group`

### 4. **Feature Engineering**
- Created new feature: `price_per_bed = price / beds`

### 5. **Bivariate & Multivariate Analysis**
- Bar plots of `price` by `room_type`
- Scatter plots for:
  - `availability_365` vs `rating`
  - `number_of_reviews` vs `price`
- Neighborhood-based price comparisons
- Geospatial scatter plot using `latitude` & `longitude`
- Review frequency trends by year (`review_year`)

### 6. **Correlation Analysis**
- Heatmap of numerical variables
- Pairplot of key numeric variables colored by `room_type`

---

## 📊 Key Insights

1. **Room Type Distribution**
   - Most listings are either "Entire home/apt" or "Private room".
   - Shared rooms are rare.

2. **Price Analysis**
   - Majority of listings are under $1500.
   - Entire homes tend to be priced significantly higher than private/shared rooms.

3. **Neighborhood Trends**
   - Certain `neighbourhood_group`s have consistently higher prices.
   - Listings are concentrated in specific latitude-longitude clusters.

4. **Review Activity**
   - `number_of_reviews` is strongly correlated with `reviews_per_month`.
   - Listings with high availability don’t always have high ratings.

5. **Correlation Patterns**
   - Strong correlations:
     - `number_of_reviews` ↔ `reviews_per_month`
     - `beds`, `bedrooms`, and `baths`
   - Weak correlation:
     - `price` ↔ `availability_365`

6. **Temporal Trends**
   - Review activity varies year-to-year and by `room_type`.

---

