# 🎬 NLP-Powered Movie Recommender System

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![NLP](https://img.shields.io/badge/Domain-NLP-purple)
![Sklearn](https://img.shields.io/badge/Library-Scikit--Learn-orange)

## 📌 Executive Summary
This project implements a **Content-Based Filtering System** leveraging **Natural Language Processing (NLP)**. By analyzing movie plot summaries ("overviews"), the system understands semantic similarities between films, allowing for nuanced recommendations that go beyond simple genre matching (e.g., distinguishing a "Space Opera" from a "Hard Sci-Fi" thriller).

## 🧠 Technical Approach

### 1. Text Preprocessing
- Ingested raw text data from the Movie Metadata dataset.
- Handled `NaN` values and performed text sanitization to prepare for vectorization.

### 2. Vector Space Modeling (TF-IDF)
- Utilized **Term Frequency-Inverse Document Frequency (TF-IDF)** to convert unstructured text into a sparse matrix.
- **Why TF-IDF?** It penalizes frequently occurring words (stop words) and highlights unique, descriptive keywords (e.g., "Heist," "Alien," "Time-Travel"), ensuring higher quality matching.

### 3. Similarity Computation
- Calculated the **Cosine Similarity** between movie vectors using a Linear Kernel.
- Resulted in a square matrix ($N \times N$) quantifying the semantic relationship between every movie pair in the database.

### 4. Recommendation Logic
- Built a retrieval system that:
    1. Maps movie titles to matrix indices.
    2. Fetches similarity scores.
    3. Sorts and returns the top $N$ most relevant films.

## 🛠️ Tech Stack
- **Language:** Python
- **NLP Techniques:** TF-IDF Vectorization, Cosine Similarity
- **Libraries:** Scikit-Learn, Pandas, NumPy
- **Data Visualization:** Seaborn

## 🔍 Example Output
**Input:** *The Dark Knight Rises*
**Output:**
1. *The Dark Knight* (92% Similarity)
2. *Batman Begins* (87% Similarity)
3. *Batman Returns* (Semantically related plot points)

## 💻 Installation & Usage

1. **Clone the repo**
   ```bash
   git clone [https://github.com/yourusername/nlp-movie-recommender.git](https://github.com/yourusername/nlp-movie-recommender.git)

```

2. **Install dependencies**
```bash
pip install pandas numpy scikit-learn matplotlib seaborn

```


3. **Run the Analysis**
* Open `Movie_Recommendation_NLP.ipynb`.
* Run the cells to generate the TF-IDF matrix.
* Call `get_recommendations("Movie Title")` to see results.



## 🚀 Future Enhancements

* **Advanced Embeddings:** Replacing TF-IDF with **BERT** or **Word2Vec** to capture deep contextual meaning.
* **Approximate Nearest Neighbors (ANN):** Implementing FAISS to reduce inference time from  to  for production scalability.

---

**Author:** Vishwaraj

*Final Year Engineering Student (AIML)*

