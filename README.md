# Movie-Prediction
# 🎬 Movie Recommendation System

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)

A content-based movie recommendation engine that suggests films similar to a user's selection. This project demonstrates end-to-end machine learning skills, from data preprocessing to building an interactive web application deployed with Streamlit.

<!-- **🔗 [Try the Live Web App!](https://your-username-movie-recommender.streamlit.app/)** *<-- Update this link after deployment*

![Streamlit App Demo](images/streamlit-demo.gif) *<!-- Add a GIF/screenshot of your app here -->

---

## 📖 Project Overview

In a world of endless content, effective recommendation systems are crucial for user engagement. This project builds a practical content-based filtering engine that analyzes movie features (genres, keywords, cast, crew) to find the most similar matches to a user's input. It solves the real-world business problem of helping users discover new content they will likely enjoy, thereby increasing platform retention and satisfaction.

## 🎯 Features

- **Intuitive Interface:** Users can select a movie from a dropdown menu or search by title.
- **Personalized Recommendations:** Get the top 10 most similar movies based on cosine similarity of combined features.
- **Interactive Results:** Results are displayed with posters, titles, and overviews for a user-friendly experience.
- **Locally Deployed:** The application is deployed using Streamlit locally.

## 🛠️ Tech Stack & Tools

- **Programming Language:** Python
- **Libraries:**
  - `pandas`, `numpy` - Data manipulation and analysis
  - `scikit-learn` - For TF-IDF Vectorization and Cosine Similarity
  - `streamlit` - For building and deploying the web application
- **Dataset:** [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) from Kaggle.
<!-- **Version Control:** Git & GitHub-->
- **Deployment:** Streamlit local host

## 📁 Dataset

- **Source:** [TMDB 5000 Movie Dataset on Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)
- **Files Used:** `tmdb_5000_movies.csv`, `tmdb_5000_credits.csv`
- **Size:** ~5,000 movies with extensive metadata including budget, genres, keywords, cast, crew, and ratings.

## 🧮 Methodology

### 1. Data Loading & Preprocessing
- Merged the `movies` and `credits` datasets on the `title` column.
- Handled missing values in critical columns like `overview`, `genres`, and `keywords`.
- Extracted the top 5 actors (`cast`), the director (`crew`), and relevant `keywords` and `genres` from JSON-like string columns.

### 2. Feature Engineering
- Created a **"tags"** feature—a combined string containing the movie's **genres, director, top 5 actors, and keywords**.
- This single string encapsulates the essence of the movie for the model to process.
- Example: `'action adventure fantasy christopher nolan christian bale heath ledger michael caine superhero secret identity chaos'` for *The Dark Knight*.

### 3. Model Building (Content-Based Filtering)
- **Vectorization:** Applied **TF-IDF (Term Frequency-Inverse Document Frequency)** to the "soup" feature to convert text into a numerical matrix, weighting important words more heavily.
- **Similarity Matrix:** Computed the **cosine similarity** matrix between all movies based on their TF-IDF vectors. This matrix measures how similar any two movies are in this feature space.

### 4. Application Development & Deployment
- Built an interactive UI using **Streamlit** with a movie selector and recommendation button.
- The app takes a user's movie choice, finds its index in the dataset, and returns the titles and metadata of the 10 movies with the highest cosine similarity score.
- Deployed the application on Streamlit locally.

## 🚀 How to Run This Project Locally

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/yashparudiya/movie-recommendation-system.git
    cd movie-recommendation-system
    ```

2.  **Create a virtual environment and install dependencies:**
    ```bash
    # Create a virtual environment (optional but recommended)
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate

    # Install required packages
    pip install -r requirements.txt
    ```

3.  **Download the dataset:**
    - Download the dataset from [Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata).
    - Place the files `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv` in the project directory.

4.  **Run the Streamlit application:**
    ```bash
    streamlit run app.py
    ```
    The app will open in your default web browser.

## 📈 Results & Output

The system successfully recommends highly relevant movies. For example:
- Input: **"The Dark Knight Rises"**
- Output: **The Dark Knight, Batman Begins, Inception, Batman v Superman, Captain America: Civil War ,etc..**

These results are validated by genre similarity, shared actors (Christian Bale, Tom Hardy), and shared directors (Christopher Nolan).

<!--[Recommendation Example](images/recommendation-example.png) *<!-- Add a screenshot here -->*

## 💡 Key Learnings & Insights

- **Business Impact:** A well-tuned recommendation system can significantly improve user experience, leading to increased watch time and customer retention on streaming platforms.
- **Feature Engineering is Key:** The quality of recommendations is directly tied to the quality of the features created. Combining genres, director, and cast was crucial for capturing the "essence" of a movie.
- **Simplicity vs. Complexity:** Content-based filtering is powerful and interpretable for a single domain (like movies), though hybrid models (mixing collaborative filtering) could be a natural next step for even better accuracy.
- **End-to-End Deployment:** This project highlighted the complete ML lifecycle—from problem framing and data cleaning to model building and, most importantly, deployment and user interaction.

---

## 📞 Contact & Connect

**Yash Parudiya**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin)](https://www.linkedin.com/in/yashparudiya/)
[![Email](https://img.shields.io/badge/Email-Contact%20Me-red?logo=gmail)](mailto:yashparudiya@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?logo=github)](https://github.com/yashu028)

**Feel free to reach out for questions, collaborations, or just to talk data!**

---

## 🤝 Contributing

Contributions and ideas are always welcome! Feel free to fork this project and submit a Pull Request.

## 📜 License

This project is for portfolio purposes. The dataset is sourced from TMDB and Kaggle.
