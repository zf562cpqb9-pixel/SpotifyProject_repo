# SpotifyProject_repo
Analysis of Spotify Data from Kaggle Dataset.

# Spotify Popularity Prediction

## Project Description
This project predicts the popularity of Spotify tracks using audio features such as danceability, energy, loudness, and tempo. The goal is to build a predictive model that captures patterns in song features to estimate their popularity scores.

## Dataset
- **Source:** [Kaggle Spotify Tracks Dataset](https://www.kaggle.com/datasets/zaheenhamidani/ultimate-spotify-tracks-db)
- **Number of tracks:** ~114,000
- **Features include:** acousticness, danceability, energy, instrumentalness, liveness, loudness, tempo, valence, and popularity (target)
- **Target variable:** `popularity` (0–100)

## Installation & Usage
1. Clone the repository:

```bash
git clone https://github.com/zf562cpqb9-pixel/SpotifyProject_repo.git
cd SpotifyProject_repo
```
# 🎵 Spotify Popularity Prediction Project

## 📌 Project Overview

This project builds and evaluates machine learning models to predict Spotify song popularity using audio and acoustic features. The goal is to identify which musical characteristics most influence popularity and to compare the effectiveness of linear and nonlinear modeling approaches.

Two models were developed:
- Linear Regression (baseline model)
- Random Forest Regressor (optimized model)

The project includes feature engineering, model optimization, performance evaluation, visualizations, ethical considerations, and business recommendations.

---

## 📂 Dataset Description

The dataset contains Spotify track-level audio features, including:

- Danceability  
- Energy  
- Loudness  
- Acousticness  
- Instrumentalness  
- Tempo  
- Duration  

**Target variable:**
- Popularity (0–100)

---

## 🧹 Data Preprocessing

The following preprocessing steps were applied:

- Removed irrelevant index column (`Unnamed: 0`)
- Handled missing or problematic values
- Converted duration from milliseconds to minutes
- Scaled features where appropriate for linear modeling
- Split dataset into training and testing sets

---

## 🧠 Feature Engineering

To improve model performance, five engineered features were created to capture nonlinear relationships and interactions between audio characteristics:

### 1. Energy × Danceability (`energy_dance`)
Captures the interaction between energy and danceability. High values represent highly engaging songs that are both energetic and easy to move to, which are often associated with higher popularity.

---

### 2. Loudness-to-Tempo Ratio (`loudness_tempo_ratio`)
Represents production intensity relative to song tempo. A small constant was added to tempo to prevent division errors. This feature helps distinguish between fast but soft tracks and slow but loud tracks.

---

### 3. Standardized Loudness (`loudness_scaled`)
Applies z-score normalization to loudness. This ensures loudness is measured relative to the dataset distribution and improves model stability.

---

### 4. Acoustic Difference (`acoustic_diff`)
Measures the difference between acousticness and instrumentalness, capturing whether a track is more acoustic or electronic in nature.

---

### 5. Duration in Minutes (`duration_min`)
Converts track duration from milliseconds to minutes for better interpretability and scaling consistency.

---

## 🤖 Models Used

### 🔹 Linear Regression (Baseline Model)
- Assumes linear relationships between features and popularity
- Used as an interpretable baseline model
- Feature scaling applied

### 🔹 Random Forest Regressor (Optimized Model)
- Ensemble model capable of capturing nonlinear relationships
- Tuned using hyperparameters such as number of estimators and tree depth
- Provides feature importance for interpretability

---

## 📊 Model Performance

| Model              | RMSE   | MAE    | R²     |
|------------------|--------|--------|--------|
| Random Forest     | 14.86  | 10.53  | 0.55   |
| Linear Regression | 21.97  | 18.33  | 0.02   |

### Key Insight:
The Random Forest model significantly outperformed Linear Regression, indicating that song popularity is driven by complex nonlinear relationships between audio features.

---

## 📈 Key Visualizations

The project includes:

- Predicted vs Actual plots
- Residual analysis
- Feature importance ranking
- Model performance comparison

These visualizations confirm that Random Forest captures more meaningful patterns in the data.

---

## 🔍 Key Insights

- Energy, danceability, and their interactions are strong predictors of popularity.
- Linear models are insufficient for capturing complex musical relationships.
- External factors likely explain additional variance not captured in the dataset.

---

## ⚖️ Ethical Analysis & Responsible Deployment

This model may reflect bias present in the training dataset. If certain genres, artists, or styles are overrepresented, the model may perform better for those groups while underperforming for others. This could unintentionally reinforce inequalities in music recommendation systems.

Additionally, song popularity is influenced by external factors such as marketing, social trends, and artist recognition, which are not included in the dataset. This introduces unavoidable limitations in predictive fairness and completeness.

If deployed incorrectly, the model could negatively impact emerging artists by underestimating their potential popularity or misallocating promotional resources. To mitigate these risks, the model should be used as a decision-support tool rather than an automated decision system. Regular audits should be performed to evaluate fairness and performance across different music categories.

---

## 💼 Business Recommendations & Deployment Considerations

The model suggests that audio features such as energy, danceability, and their interactions strongly influence song popularity. These insights can be used to improve playlist curation, recommendation systems, and promotional targeting strategies.

However, the model should be used alongside human judgment rather than as a fully automated decision-maker. A hybrid approach ensures that borderline cases are reviewed carefully before final decisions are made. This is especially important in creative industries where context matters.

The model has limitations, including moderate predictive power (R² ≈ 0.55) and lack of external contextual features such as marketing and cultural trends. Therefore, predictions should be interpreted as probabilistic indicators rather than absolute truths, and the model should be retrained periodically to adapt to changing music trends.

---

## ⚠️ Limitations

- Does not include external industry factors (marketing, virality, artist popularity)
- Moderate predictive performance (R² ≈ 0.55)
- Sensitive to dataset bias and representation issues
- Linear Regression underperforms due to nonlinear feature relationships

---

## 🚀 How to Run This Project

### 1. Clone repository
```bash
git clone https://github.com/your-username/SpotifyProject_repo.git
cd SpotifyProject_repo
