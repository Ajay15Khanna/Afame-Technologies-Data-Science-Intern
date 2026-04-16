# 🎬 Movie Rating Prediction Using Python
### Data Science Internship Project — Afame Technologies

> **Predicting Indian movie ratings using machine learning regression techniques on IMDb data.**

---

## 📌 Project Overview

This project was completed as part of a **Data Science Internship at Afame Technologies**. The goal was to analyze a dataset of Indian movies sourced from IMDb and build a machine learning model that accurately predicts a movie's rating based on features such as genre, director, actors, year of release, duration, and number of votes.

The project encompasses the full data science pipeline — from raw data cleaning and exploratory data analysis (EDA) to feature engineering, model building, hyperparameter tuning, and result interpretation. It demonstrates practical skills in data preprocessing, visualization, and supervised machine learning.

**Problem Type:** Regression  
**Target Variable:** Movie Rating (continuous, scale of 1–10)

---

## 📂 Dataset Information

| Attribute         | Details                                      |
|-------------------|----------------------------------------------|
| **Source**        | Kaggle — IMDb India Movies Dataset           |
| **Domain**        | Indian Film Industry (Bollywood & Regional)  |
| **Format**        | CSV                                          |
| **Key Features**  | Name, Year, Duration, Genre, Rating, Votes, Director, Actor 1, Actor 2, Actor 3 |
| **Target**        | Rating (float)                               |

**Data Challenges Addressed:**
- Missing values handled via imputation and removal
- Categorical encoding of high-cardinality features (Genre, Director, Actors)
- Outlier detection in Duration and Votes columns
- Feature scaling for linear model compatibility

---

## 🛠️ Tools & Technologies Used

| Category                    | Tools / Libraries                            |
|-----------------------------|----------------------------------------------|
| **Language**                | Python 3.x                                   |
| **Data Manipulation**       | Pandas, NumPy                                |
| **Visualization**           | Matplotlib, Seaborn                          |
| **Machine Learning**        | Scikit-learn, XGBoost / LightGBM             |
| **Statistical Analysis**    | SciPy, Statsmodels                           |
| **Development Environment** | Jupyter Notebook                             |
| **Version Control**         | GitHub                                       |

---

## 🔄 Steps Followed

### 1. Data Collection & Understanding
- Loaded the IMDb India movie dataset from Kaggle
- Explored shape, data types, missing values, and summary statistics
- Identified the target variable (Rating) and potential predictor features

### 2. Data Cleaning & Preprocessing
- Removed or imputed missing values in Rating, Duration, Year, and Votes
- Cleaned string columns (stripped whitespace, standardized formatting)
- Converted Duration to numeric (minutes) and Year to integer
- Parsed and one-hot encoded the multi-valued Genre column

### 3. Exploratory Data Analysis (EDA)
- Plotted distribution of Movie Ratings and Votes
- Analyzed top directors (by volume and by rating) and top actors by appearances
- Investigated the relationship between Duration and Rating
- Generated a Correlation Matrix and Pairplot for numerical features
- Explored top-rated genres by mean rating

### 4. Feature Engineering
- One-hot encoded: Genre, Director, Actor 1, Actor 2, Actor 3
- Retained numerical features: Year, Duration, Votes
- Reduced dimensionality by keeping only high-frequency categorical levels

### 5. Model Building
- **Baseline Model:** Linear Regression
- **Second Model:** Random Forest Regressor
- **Third Model:** Gradient Boosting Regressor
- **Tuned Model:** Hyperparameter-tuned Random Forest (GridSearchCV)

### 6. Model Evaluation
- Metrics used: Mean Squared Error (MSE) and R-squared (R²)
- Visualized Actual vs. Predicted ratings (scatter plot)
- Compared train vs. test performance to check for overfitting
- Selected the **Tuned Random Forest** as the final model due to best generalization

### 7. Feature Importance Analysis
- Extracted and visualized the Top 10 most influential features
- Year, Votes, and Duration emerged as the most predictive features

---

## 📊 Key Insights

### Rating Distribution
- Movie ratings follow a near-normal distribution, peaking around **6–7**
- The common rating range is **5 to 7**; very few movies are rated below 2 or above 8

### Votes Distribution
- Votes are highly right-skewed — most movies receive fewer than 50 votes
- A small subset of popular movies accounts for the bulk of total votes

### Top Directors
- **Mahesh Bhatt** directed the most movies (39) among all directors in the dataset
- **Saif Ali Sayeed** has the highest maximum-rated movie (10.0)
- Other prolific directors: David Dhawan, Kanti Shah, Hrishikesh Mukherjee

### Top Actors
- **Mithun Chakraborty** has the most movie appearances (~227), followed by Dharmendra and Jeetendra
- The top 10 actors all have 110+ appearances, indicating highly prolific careers

### Top-Rated Genres
- **History, Romance** and **Documentary, Family, History** are the highest-rated genre combinations (~9.3 mean rating)
- Documentary sub-genres (Music, Thriller, Sport) consistently score above 8.6
- Investing in these genres is likely to yield critically acclaimed results

### Duration vs. Rating
- No strong linear relationship exists between movie duration and rating
- Duration alone cannot reliably predict a movie's quality

### Correlation Matrix
- Numerical variables (Year, Duration, Rating, Votes) are weakly correlated with each other
- The strongest correlation is between Year and Duration (-0.30) — older films tend to be longer
- Low multicollinearity is a positive sign for regression modeling

### Feature Importance (Random Forest)
The top predictors of movie rating are:
1. **Year** (most important, ~0.052)
2. **Votes** (~0.022)
3. **Duration** (~0.022)
4. **Genre_Drama** (~0.011)
5. **Genre_Action**, **Genre_Horror**, **Actor 1_Irrfan Khan**, **Actor 1_Jeetendra**

---

## 📸 Screenshots / Visualizations

| Visualization | Description |
|---|---|
| `Rating_Analysis.PNG` | Distribution of movie ratings with KDE curve |
| `Votes_Analysis.PNG` | Right-skewed distribution of vote counts |
| `Duration_vs_Rating.png` | Scatter plot showing no strong duration-rating relationship |
| `Correlation_Matrix.png` | Heatmap of correlations between numerical features |
| `Pairplot.png` | Multi-variable pairplot confirming weak inter-variable correlations |
| `Top_10_actors_with_most_movie_appearances.png` | Bar chart of most prolific actors |
| `Top_10_directors_with_most_movies_directed.png` | Bar chart of most prolific directors |
| `Top_10_directors_with_highest_rated_movies.png` | Directors with highest maximum-rated films |
| `Top_10_highly_rated_movie_genres.png` | Genre combinations with highest mean ratings |
| `Top_10_Feature_Importances.png` | Feature importance from Random Forest model |
| `Actual_vs_Predicted_Ratings.png` | Scatter plot of model predictions vs. actual ratings |

---

## ✅ Recommendations

Based on the analysis and model findings:

- **Year Matters:** Production teams should stay current with trends — release year is the single most predictive feature
- **Encourage Audience Engagement:** Votes are a key predictive signal; marketing strategies should encourage reviews and ratings
- **Genre Strategy:** Investing in History, Romance, Documentary, and Music genres is likely to yield higher-rated films
- **Director & Cast Selection:** Collaborating with experienced directors (Hrishikesh Mukherjee, Shakti Samanta) and well-established actors (Irrfan Khan, Amitabh Bachchan) positively influences ratings
- **Duration:** Aim for audience-preferred runtimes; extremely long or short films tend to have more varied ratings

---

## 🚀 Next Steps

- **Model Refinement:** Explore neural networks (MLP) or stacked ensemble models for improved accuracy
- **Feature Engineering:** Create aggregate features like Director's historical average rating, Actor's career average rating
- **Sentiment Analysis:** Incorporate user review text as NLP features
- **Real-Time Data:** Build a pipeline that updates the model with new IMDb entries periodically
- **Deployment:** Wrap the model in a Flask/FastAPI web app for live rating prediction

---

## 🔗 Project Links

- **GitHub Repository:** [https://github.com/Ajay15Khanna/Afame-Technologies-Data-Science-Intern](https://github.com/Ajay15Khanna/Afame-Technologies-Data-Science-Intern)
- **Notebook:** `Movie_Rating_Prediction_Project.ipynb`
- **Dataset:** `Movie_dataset.csv`

---

## 👤 Author

**Ajay Khanna**  
Data Science Intern — Afame Technologies  
📧 Connect on [LinkedIn](#) | 🐙 [GitHub](https://github.com/Ajay15Khanna/Afame-Technologies-Data-Science-Intern)

---

*This project was completed as part of the Afame Technologies Data Science Internship Program.*
