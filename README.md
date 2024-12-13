# SocialVerse Recommendation System

## Overview

This project is a recommendation system designed to analyze user interactions and content data from the SocialVerse platform. It provides personalized recommendations based on user behavior, content similarity, and mood-based preferences using machine learning techniques such as collaborative filtering and content-based filtering.

---

## Features

1. **Data Collection**:
   - Fetches data from the SocialVerse API using endpoints for posts, user interactions, and engagement metrics.
   - Handles paginated API responses to gather large datasets.

2. **Data Preprocessing**:
   - Converts raw JSON responses into structured Pandas DataFrames.
   - Handles missing values and formats data for analysis.

3. **Recommendation Strategies**:
   - **Content-Based Filtering**: Uses TF-IDF and cosine similarity to recommend posts based on textual similarity in `post_summary`.
   - **Collaborative Filtering**: Implements SVD (Singular Value Decomposition) to predict user preferences based on engagement scores.
   - **Mood-Based Filtering**: Classifies content into moods (e.g., happy, sad, energetic) based on keywords in the `post_summary` field.
   - **Hybrid Recommendations**: Combines multiple strategies to provide a comprehensive recommendation list.

4. **User Interaction Matrix**:
   - Consolidates user engagement data (views, likes, ratings) into a matrix for advanced analytics.

5. **Model Evaluation**:
   - Cross-validates the SVD algorithm using RMSE and MAE for performance metrics.

---

## Technologies Used

- **Languages and Libraries**:
  - Python
  - Pandas
  - scikit-learn
  - Surprise Library (for collaborative filtering)
  - Requests (for API integration)
- **Machine Learning Techniques**:
  - TF-IDF Vectorization
  - Cosine Similarity
  - SVD (Singular Value Decomposition)
- **Data Processing**:
  - Data cleaning, merging, and feature engineering using Pandas.

---

## How It Works

### 1. Fetch Data from API
- The `fetch_data` and `fetch_all_data` functions handle API requests and process paginated responses.

### 2. Preprocess Data
- Missing values are filled with defaults.
- Key engagement metrics and user-item interaction data are aggregated.

### 3. Generate Recommendations
- **Content-Based**: Similar posts are recommended based on text descriptions.
- **Collaborative**: Predicts user preferences for unseen posts.
- **Mood-Based**: Suggests posts aligned with the user's mood.

### 4. Save Results
- DataFrames are exported to CSV for further analysis or reporting.

---

## Setup
git clone <repository-url>
cd <repository-folder>


HEADERS = {"Flic-Token": "<your-api-token>"}



### Prerequisites
1. Python 3.x
2. Install required libraries:
   ```bash
   pip install pandas scikit-learn surprise requests
