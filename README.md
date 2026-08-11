# Movie Recommendation System

> A hybrid movie recommendation system built with Python, Machine Learning, and Streamlit, combining Content-Based Filtering and Collaborative Filtering using SVD to generate personalized movie recommendations.

---

## Overview

This project implements a movie recommendation system using multiple recommendation approaches and integrates them into an interactive Streamlit application.

The system provides three recommendation modes:

- **Content-Based Filtering** — recommends movies similar to a selected movie based on its metadata.
- **Collaborative Filtering using SVD** — recommends movies based on user–movie rating interactions.
- **Hybrid Recommendation** — combines content similarity and collaborative filtering to provide more personalized recommendations.

The project demonstrates the complete workflow from data preprocessing and feature engineering to machine learning model development and application integration.

---

## Objectives

The main objectives of this project are to:

- Understand and implement different recommendation system techniques.
- Apply Natural Language Processing concepts to movie metadata.
- Use TF-IDF and Cosine Similarity for content-based recommendations.
- Apply Singular Value Decomposition (SVD) for collaborative filtering.
- Combine multiple recommendation approaches into a hybrid system.
- Build an interactive application for testing the recommendation models.
- Explore the transition from machine learning experimentation to an interactive application.

---

# Recommendation Approaches

## 1. Content-Based Filtering

The Content-Based model recommends movies that are similar to a movie selected by the user.

### Dataset

**TMDB 5000 Movie Dataset**

The dataset contains movie metadata including:

- Genres
- Keywords
- Overview
- Cast
- Director
- Movie ratings
- TMDB movie IDs

### Methodology

```text
Movie Metadata
      ↓
Data Cleaning & Preprocessing
      ↓
Feature Combination
      ↓
TF-IDF Vectorization
      ↓
Cosine Similarity
      ↓
Similar Movies
```

### Techniques Used

- Text preprocessing
- Feature engineering
- TF-IDF Vectorization
- Cosine Similarity

The resulting similarity scores are used to identify movies with similar content and characteristics.

---

## 2. Collaborative Filtering — SVD

The Collaborative Filtering model recommends movies based on user–movie rating interactions.

### Dataset

**MovieLens 100K**

The dataset contains user ratings for movies and is used to train the collaborative filtering model.

### Methodology

```text
User-Movie Ratings
        ↓
Data Preparation
        ↓
SVD Model
        ↓
Predicted Ratings
        ↓
Top-Rated Unseen Movies
        ↓
Recommendations
```

### Algorithm

The project uses **Singular Value Decomposition (SVD)** through the `Surprise` library.

The model predicts how highly a user may rate movies they have not rated yet and uses these predictions to generate recommendations.

---

## 3. Hybrid Recommendation System

The Hybrid model combines the two recommendation approaches:

```text
Content-Based Filtering
          +
Collaborative Filtering
          ↓
    Hybrid Recommendations
```

The goal is to combine:

- Movie similarity obtained from Content-Based Filtering.
- User preference predictions obtained from Collaborative Filtering.

This allows the system to consider both the characteristics of a movie and the user's potential preferences.

---

# System Architecture

```text
                    Movie Recommendation System
                              │
                ┌─────────────┴─────────────┐
                │                           │
        Content-Based                Collaborative
          Filtering                   Filtering
                │                           │
        Movie Metadata                User Ratings
                │                           │
          TF-IDF                      SVD Model
                │                           │
      Cosine Similarity              Predicted Ratings
                │                           │
                └─────────────┬─────────────┘
                              │
                         Hybrid Model
                              │
                              ↓
                     Movie Recommendations
                              │
                              ↓
                       Streamlit App
```

---

# Datasets

## TMDB 5000 Movie Dataset

Used primarily for the Content-Based Recommendation System.

The dataset provides movie metadata required for text-based similarity and feature construction.

**Source:**  
TMDB 5000 Movie Dataset — Kaggle

https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata

---

## MovieLens 100K

Used for the Collaborative Filtering and SVD model.

The dataset provides user–movie rating interactions used to learn user preference patterns.

**Source:**  
MovieLens 100K — GroupLens

https://grouplens.org/datasets/movielens/100k/

---

# Technologies & Tools

## Programming Language

- Python

## Data Processing

- Pandas
- NumPy

## Machine Learning

- Scikit-learn
- Surprise

## Recommendation Techniques

- TF-IDF
- Cosine Similarity
- Singular Value Decomposition (SVD)
- Hybrid Recommendation

## Application

- Streamlit

## Development & Version Control

- Jupyter Notebook
- Git
- GitHub

---

# Project Structure

```text
Movie-Recommendation-System/
│
├── app.py
├── README.md
├── requirements.txt
│
├── data/
│   └── ml-100k/
│       ├── u.data
│       └── u.item
│
├── models/
│   ├── svd_model.pkl
│   ├── tfidf_vectorizer.pkl
│   ├── tfidf_matrix.pkl
│   ├── cosine_sim_tfidf.pkl
│   └── cosine_sim_meta.pkl
│
├── notebooks/
│   └── movie_recommendation.ipynb
│
└── assets/
    └── Movies.jpg
```

> Note: The exact project structure may vary depending on the final organization of the repository.

---

# Streamlit Application

The project includes an interactive Streamlit application that allows users to explore the different recommendation approaches.

## Content-Based Mode

The user provides a movie title, and the system returns movies with similar content.

The results include information such as:

- Movie title
- Overview
- Genres
- Director
- Top cast
- Similarity score
- TMDB ID

---

## SVD Mode

The user provides a **User ID**, and the system generates movie recommendations based on predicted ratings.

The recommendation process follows:

```text
User ID
   ↓
Rating History
   ↓
SVD Model
   ↓
Predicted Ratings
   ↓
Recommended Movies
```

---

## Hybrid Mode

The user provides movies they like, and the system combines content similarity with collaborative filtering to generate recommendations.

```text
Movies the User Likes
          +
User Rating Behavior
          ↓
Content-Based + SVD
          ↓
Hybrid Recommendations
```

---

# Example Workflow

## Content-Based Recommendation

If the user selects:

```text
The Matrix
```

the system searches for movies with similar metadata and content characteristics.

---

## Collaborative Filtering

For a specific user:

```text
User
  ↓
Rating History
  ↓
SVD
  ↓
Predicted Ratings
  ↓
Recommendations
```

---

## Hybrid Recommendation

```text
Movies the User Likes
          +
User Preference Patterns
          ↓
Content-Based Filtering
          +
Collaborative Filtering
          ↓
Hybrid Recommendations
```

---

# Key Learning Outcomes

Through this project, I practiced and explored:

- Data cleaning and preprocessing
- Data preparation for recommendation systems
- Feature engineering
- Text feature extraction
- TF-IDF Vectorization
- Cosine Similarity
- Content-Based Filtering
- Collaborative Filtering
- Matrix Factorization
- SVD-based Recommendation
- Hybrid Recommendation Systems
- Model serialization using Pickle
- Building interactive machine learning applications with Streamlit
- Integrating machine learning models into an application workflow

---

# Future Improvements

Potential improvements include:

- Improve hybrid score normalization.
- Add recommendation evaluation metrics.
- Implement user cold-start handling.
- Improve movie title matching.
- Add movie posters and richer TMDB information.
- Improve recommendation diversity.
- Experiment with additional recommendation algorithms.
- Deploy the Streamlit application online.

---

# Conclusion

This project demonstrates how different Machine Learning approaches can be combined to build a practical movie recommendation system.

By implementing **Content-Based Filtering**, **Collaborative Filtering using SVD**, and a **Hybrid Recommendation approach**, the project explores multiple strategies for generating personalized movie recommendations.

The project also demonstrates the transition from developing machine learning models in a notebook to integrating those models into an interactive application using Streamlit.

---

# Author

**Rahma Mohamed**

Data Science Student | Machine Learning & AI

---

> This project was developed as part of my practical learning journey in Machine Learning, Recommendation Systems, and AI.
