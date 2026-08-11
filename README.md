# 🎬 Movie Recommendation System

> A hybrid movie recommendation system built with **Python, Machine Learning, and Streamlit**, combining **Content-Based Filtering** and **Collaborative Filtering using SVD** to generate personalized movie recommendations.

---

## 📌 Project Overview

This project implements a **Movie Recommendation System** using multiple recommendation techniques.

The system provides three recommendation approaches:

* 🎯 **Content-Based Filtering** — recommends movies similar to a selected movie based on its metadata.
* 👥 **Collaborative Filtering (SVD)** — recommends movies based on user–movie rating interactions.
* 🔀 **Hybrid Recommendation** — combines both approaches to provide more personalized recommendations.

The project also includes an interactive **Streamlit web application** that allows users to explore the different recommendation approaches.

---

## 🎯 Objectives

The main objectives of this project are to:

* Understand and implement different recommendation system techniques.
* Apply **Natural Language Processing (NLP)** concepts to movie metadata.
* Use **TF-IDF and Cosine Similarity** for content-based recommendations.
* Apply **Singular Value Decomposition (SVD)** for collaborative filtering.
* Combine multiple recommendation approaches into a hybrid system.
* Build an interactive application for testing the recommendation models.

---

# 🧠 Recommendation Approaches

## 1. 🎯 Content-Based Filtering

The Content-Based model recommends movies that are similar to a movie selected by the user.

### Dataset

**TMDB 5000 Movie Dataset**

The dataset contains movie metadata such as:

* Genres
* Keywords
* Overview
* Cast
* Director
* Movie ratings
* TMDB movie IDs

### Methodology

The content-based recommendation pipeline is:

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

### Main Techniques

* **TF-IDF Vectorization**
* **Cosine Similarity**
* Text preprocessing
* Feature engineering

The similarity score is used to identify movies with similar content and characteristics.

---

# 2. 👥 Collaborative Filtering — SVD

The Collaborative Filtering model recommends movies based on **user–movie rating interactions**.

### Dataset

**MovieLens 100K**

The dataset contains user ratings for movies.

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

The model predicts how highly a user may rate movies they have not rated yet.

---

# 3. 🔀 Hybrid Recommendation System

The Hybrid model combines:

```text
Content-Based Filtering
          +
Collaborative Filtering
          ↓
    Hybrid Recommendations
```

The goal is to combine:

* **Movie similarity** from content-based filtering.
* **User preference predictions** from collaborative filtering.

This allows the system to consider both **what the movie is about** and **what the user is likely to enjoy**.

---

# 🔄 Overall System Pipeline

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

# 📊 Datasets

## TMDB 5000 Movie Dataset

Used primarily for the **Content-Based Recommendation System**.

Source:

[TMDB 5000 Movie Dataset — Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)

---

## MovieLens 100K

Used for the **Collaborative Filtering / SVD model**.

Source:

[MovieLens 100K — GroupLens](https://grouplens.org/datasets/movielens/100k/)

---

# 🛠️ Technologies & Tools

### Programming Language

* Python

### Data Processing

* Pandas
* NumPy

### Machine Learning

* Scikit-learn
* Surprise

### Recommendation Techniques

* TF-IDF
* Cosine Similarity
* Singular Value Decomposition (SVD)
* Hybrid Recommendation

### Application

* Streamlit

### Development

* Jupyter Notebook
* Git & GitHub

---

# 📁 Project Structure

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

> **Note:** The exact project structure may vary depending on the final organization of the repository.

---

# 🖥️ Streamlit Application

The project includes an interactive Streamlit interface where users can select the recommendation approach.

### Available Modes

### 🎯 Content-Based

The user enters a movie title, and the system returns movies with similar content.

The results include information such as:

* Movie title
* Overview
* Genres
* Director
* Top cast
* Similarity score
* TMDB ID

### 👥 SVD

The user enters a **User ID**, and the system generates movie recommendations based on predicted ratings.

### 🔀 Hybrid

The user provides movies they like, and the system combines content similarity with collaborative filtering to generate recommendations.

---

# 📈 Example

### Content-Based Recommendation

If the user selects:

```text
The Matrix
```

the system searches for movies with similar metadata and content characteristics.

### Collaborative Filtering

For a specific User ID:

```text
User → Rating History → SVD → Predicted Ratings → Recommendations
```

### Hybrid

```text
Movies the user likes
          +
User's rating behavior
          ↓
Content-Based + SVD
          ↓
Hybrid Recommendations
```

---

# 💡 Key Learning Outcomes

Through this project, I practiced:

* Data cleaning and preprocessing
* Exploratory data preparation
* Feature engineering
* Text feature extraction
* TF-IDF vectorization
* Similarity measurement
* Collaborative filtering
* Matrix factorization
* SVD-based recommendation
* Hybrid recommendation systems
* Model serialization using Pickle
* Building an interactive ML application with Streamlit

---

# 🚀 Future Improvements

Potential improvements include:

* Improve hybrid score normalization.
* Add better recommendation evaluation metrics.
* Implement user cold-start handling.
* Improve movie title matching.
* Add movie posters and richer TMDB information.
* Improve recommendation diversity.
* Experiment with additional recommendation algorithms.
* Deploy the Streamlit application online.

---

# 📌 Conclusion

This project demonstrates how different Machine Learning approaches can be combined to build a practical **Recommendation System**.

By implementing **Content-Based Filtering**, **Collaborative Filtering using SVD**, and a **Hybrid Recommendation approach**, the project explores different ways of generating personalized movie recommendations.

The project also demonstrates the transition from developing Machine Learning models in a notebook to integrating them into an interactive application using **Streamlit**.

---

## 👩‍💻 Author

**Rahma Mohamed**

Data Science Student | Machine Learning & AI Enthusiast

---

⭐ If you find this project useful, feel free to explore the repository and experiment with the recommendation models.

