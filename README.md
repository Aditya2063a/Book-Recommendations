# Book Recommendation System

## Overview
This project recommends books using a Nearest Neighbors model from scikit-learn based on features like average rating, ratings count, and language.

## Key Steps

- **Feature Engineering:**
  - **Bucketing Ratings:** Convert continuous `average_rating` into categories (e.g., "between 0 and 1", "between 1 and 2").
  - **One-Hot Encoding:** Encode bucketed ratings and `language_code` into dummy variables.

- **Feature Scaling:**
  - Normalize the combined features (dummy variables, `average_rating`, `ratings_count`) using MinMaxScaler.

- **Building the Model:**
  - Train a Nearest Neighbors model (6 neighbors, `ball_tree` algorithm) on the scaled features.

- **Recommendation Function:**
  - `BookRecommender(book_name)` finds the book index and returns a list of similar books by retrieving its nearest neighbors.

## Installation

Install the required libraries:

```bash
pip install numpy pandas seaborn matplotlib scikit-learn
```

## Algorithm
1. **Feature Engineering:**
   - **Bucketing Ratings:** Convert continuous `average_rating` values into buckets (e.g., "between 0 and 1", "between 1 and 2", etc.).
   - **Encoding:** One-hot encode the bucketed ratings and `language_code`.

2. **Feature Scaling:**
   - Normalize the combined features (dummy variables, `average_rating`, and `ratings_count`) using `MinMaxScaler` so that all features contribute equally.

3. **Model Building:**
   - Train a Nearest Neighbors model (6 neighbors using the `ball_tree` algorithm) on the scaled features to find similar books.

4. **Recommendation Function:**
   - The `BookRecommender(book_name)` function finds the index of the input book, retrieves its nearest neighbors, and returns a list of similar book titles.
