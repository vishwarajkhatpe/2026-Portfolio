# 🎬 Unsupervised Movie Recommendation Engine (K-Means)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Sklearn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Complete-green)

## 📌 Executive Summary
This project is a **Content-Based Recommendation System** designed to solve the "Cold Start" problem in movie suggestions. Unlike Collaborative Filtering, which relies on user history, this engine utilizes **Unsupervised Machine Learning (K-Means Clustering)** to group movies based on latent patterns in metadata, such as Genres, Popularity, and Vote Averages.

This project demonstrates the end-to-end Data Science lifecycle, from complex data parsing to model inference.

## 🚀 Technical Architecture

### 1. Data Ingestion & Cleaning
- Parsed stringified JSON data for nested columns (Genres/Keywords).
- Handled missing values and sanitized data types for numerical computation.

### 2. Feature Engineering
- **Multi-Label Binarization:** Converted categorical genre lists into a binary feature matrix.
- **Min-Max Scaling:** Normalized numerical features (`Popularity`, `Vote Average`) to the [0, 1] range to prevent magnitude bias during distance calculations.

### 3. Model Selection & Tuning
- **K-Means Clustering:** Used to segment the high-dimensional feature space.
- **Hyperparameter Optimization:**
    - **Elbow Method:** Analyzed Inertia to determine the inflection point.
    - **Silhouette Analysis:** Validated cluster separation to ensure distinct grouping.
    - *Selected Optimal K: 10*

### 4. Inference Engine
- Developed a query function that identifies a movie's cluster and ranks intra-cluster peers by a weighted score of quality and popularity.

## 🛠️ Tech Stack
- **Language:** Python
- **Data Manipulation:** Pandas, NumPy
- **Machine Learning:** Scikit-Learn (KMeans, MultiLabelBinarizer, MinMaxScaler)
- **Visualization:** Matplotlib, Seaborn

## 📊 Key Results
- Successfully clustered movies into distinct archetypes (e.g., "Critically Acclaimed Dramas," "Blockbuster Action," "Niche Horror").
- Recommendation latency is minimal due to pre-computed cluster assignments.

## 💻 Installation & Usage

1. **Clone the repo**
   ```bash
   git clone [https://github.com/yourusername/movie-clustering-engine.git](https://github.com/yourusername/movie-clustering-engine.git)