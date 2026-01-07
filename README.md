# Unsupervised Learning Project: Anime Recommender System

![Python](https://img.shields.io/badge/Python-3776AB.svg?style=for-the-badge&logo=Python&logoColor=white)

![Anime](https://github.com/claudiaewilson/Unsupervised_Learning_Project/blob/main/anime_1.png)

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Methodology Overview](#methodology-overview)
4. [Model Evaluation Summary](#model-evaluation-summary)
5. [Packages](#packages)
6. [Environment Setup](#environment-setup)
7. [Team Members](#team-members)

---

## 1. Project Overview <a id="project-overview"></a>

Recommender systems play a critical role in modern digital platforms by helping users navigate overwhelming amounts of content. Streaming services such as Netflix, Amazon Prime, Disney+, and Showmax rely on recommendation algorithms to personalise user experiences, increase engagement, and reduce decision fatigue.

In this project, multiple **recommender system approaches** are explored and evaluated for a collection of anime titles. The primary objective is to predict **how a user will rate an anime they have not yet reviewed**, using historical user–item interactions and anime metadata.

The dataset is sourced from **myanimelist.net** and contains thousands of users and anime titles, making it well suited for collaborative and content-based recommendation techniques.

![Anime](https://github.com/claudiaewilson/Unsupervised_Learning_Project/blob/main/anime_2.png)

---

## 2. Dataset <a id="dataset"></a>

The dataset consists of anime metadata and user rating data split across three files:

### Supplied Files
- **`anime.csv`** – Anime metadata
- **`train.csv`** – Historical user ratings
- **`test.csv`** – User–anime pairs requiring rating prediction

### File Descriptions

**anime.csv**
- `anime_id` – Unique identifier for each anime
- `name` – Anime title
- `genre` – Comma-separated list of genres
- `type` – Format (TV, Movie, OVA, ONA, etc.)
- `episodes` – Number of episodes
- `rating` – Average community rating (out of 10)
- `members` – Number of users associated with the anime

**train.csv**
- `user_id` – Anonymised user identifier
- `anime_id` – Anime identifier
- `rating` – User rating (out of 10); `-1` indicates watched but not rated

**test.csv**
- `user_id` – Anonymised user identifier
- `anime_id` – Anime identifier requiring a predicted rating

---

## 3. Methodology Overview <a id="methodology-overview"></a>

The project follows an end-to-end recommender system workflow:

1. **Exploratory Data Analysis (EDA)**  
   - Analysis of rating distributions, sparsity, and anime popularity

2. **Feature Preparation & PCA (Exploratory)**  
   - Dimensionality reduction applied to numerical anime features for exploratory understanding

3. **Recommender System Modelling**
   - User-based collaborative filtering (demonstrated on a sampled dataset)
   - Item-based collaborative filtering (primary scalable model)
   - Content-based filtering using anime metadata

4. **Evaluation & Validation**
   - Train–validation split
   - Performance measured using **MAE** and **RMSE**
   - Sparse user–item matrices used for scalability

5. **Rating Prediction**
   - Final predictions generated for unseen user–anime pairs in `test.csv`

---

## 4. Model Evaluation Summary <a id="model-evaluation-summary"></a>

All models were evaluated on a validation subset using MAE and RMSE.

| Model | MAE | RMSE |
|-----|-----|-----|
| Baseline (Global Mean) | 1.232 | 1.573 |
| User-Based Collaborative Filtering | 1.186 | 1.535 |
| **Item-Based Collaborative Filtering** | **0.499** | **0.685** |
| Content-Based Filtering | 1.025 | 1.380 |

**Key Findings:**
- Item-based collaborative filtering significantly outperformed other approaches
- User-based CF was limited by sparsity and scalability
- Content-based filtering proved useful for cold-start scenarios
- Item-based CF was selected as the final model for prediction

---

## 5. Packages <a id="packages"></a>

Key libraries used in this project include:

- `Python 3.11`
- `Pandas`
- `NumPy`
- `Matplotlib`
- `Scikit-learn`
- `SciPy`

---




#### Additional Resources to create a README file:
- [Make a README](https://www.makeareadme.com/)
- [GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)
- [FreeCodeCamp](https://www.freecodecamp.org/news/how-to-write-a-good-readme-file/)

