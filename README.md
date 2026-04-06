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
## Current Results

- **Model 1:** Random Forest Regressor — RMSE: 14.4022
- **Model 2:** Linear Regression — RMSE: 21.9726

### Observations
- Random Forest outperforms Linear Regression, likely because it captures nonlinear relationships between features and popularity.
- Additional feature engineering and hyperparameter tuning are planned for the final submission.

## Next Steps

- Engineer additional features such as genre encoding, artist popularity averages, and release year normalization.
- Optimize Random Forest with hyperparameter tuning and cross-validation.
- Explore temporal trends in song popularity to improve predictive accuracy.

## Context and Business Value

Machine learning is appropriate because popularity depends on complex relationships between audio features, mood, and tempo. This project demonstrates practical application of regression models, feature engineering, and data visualization, emphasizing real-world insights relevant to music industry stakeholders.
