# 📚 Book Recommendation System
**Course:** IFT 511 – Analyzing Big Data  
**Student:** Raghu Menni Lokanadhanaidu  
**Project Task:** Build a recommender system that suggests books based on users’ previous ratings and preferences.  
**Tools Used:** Python, Pandas, Sklearn, Math, Collections  

---

## 📘 Project Overview
This project implements a **collaborative filtering–based recommender system** that predicts which books a user might enjoy based on their reading history and ratings.  

The system analyzes user behavior and preferences, identifies users with similar reading patterns using **cosine similarity**, and recommends books that those similar users highly rated but the target user has not yet read.

The end goal is to create a **personalized recommendation engine** capable of handling large datasets efficiently.

---

## 🧩 Project Steps

### **Step 1 – Task Selection and Data Cleaning**
The first step focuses on data loading, cleaning, and transformation.

**Process:**
- Loaded book rating data from `Ratings.csv` using **pandas**.  
- Mapped each `User-ID` and `ISBN` to unique numerical indices for efficient computation.  
- Structured ratings in a dictionary format:  
  ```python
  {user_index: {book_index: rating}}
Converted cleaned data into LIBSVM format, which is required for model training and similarity computation later.

Generated output file: user_booklibsvmnew.libsvm

Key Outcome:
Created a structured, ready-to-use dataset representing user-book rating relationships for the recommendation engine.

Step 2 – Data Analysis and Recommendation Algorithm

This step implements the actual recommendation system using collaborative filtering.

Core Functions:

read_library_data() – Loads books and user histories from the dataset.

calculate_reader_similarity() – Computes cosine similarity between users.

generate_book_suggestions() – Finds top recommendations for a given user based on nearest neighbors.

create_recommendation_file() – Generates the final recommendation output CSV.

Algorithm Summary:

Each user’s reading pattern is represented as a preference vector.

The cosine similarity between two users’ vectors determines how similar their tastes are.

For each user:

Find the 10 most similar users (neighbors).

Collect books those neighbors rated highly but the target user hasn’t read.

Compute a weighted recommendation score for each unseen book:

score
=
∑
(
neighbor similarity
×
neighbor rating
)
score=∑(neighbor similarity×neighbor rating)

Output the top 5 recommended books for each user.

Generated Output File:
library_suggestions.csv

Output Format:

User_ID	Book_ID	Book_Title	Recommendation_Score
1	245	The Da Vinci Code	9.7
2	312	To Kill a Mockingbird	8.9
3	178	1984	7.6
🧠 Key Features

Collaborative Filtering Approach: Uses user-user similarity to make recommendations.

Cosine Similarity Metric: Measures how similar two users’ preferences are.

Dynamic Scoring: Produces a weighted score between 1 and 10.

Scalable Design: Efficiently processes large book rating datasets.

Automated Output: Exports recommendations into a structured CSV file.

🔍 Insights & Observations

High similarity users produce strong recommendation matches with scores near 10.

Mid-range scores (5–8) indicate moderate alignment in reading preferences.

Lower scores (<4) typically represent weak or less relevant suggestions.

The recommender system effectively identifies reading clusters and shared interests among users.

📂 Repository Contents

IFT511_ProjectStep_I-3.docx – Step 1: Data cleaning and LIBSVM data preparation.

IFT511_ProjectStep_II.docx – Step 2: Recommendation system algorithm and implementation.

Ratings.csv – User ratings dataset.

Books.csv – Book metadata file.

user_booklibsvmnew.libsvm – Processed user-book ratings in LIBSVM format.

library_suggestions.csv – Final personalized recommendations.

README.md – Project documentation (this file).

🏁 Conclusion

This project successfully demonstrates how collaborative filtering can be applied to build an intelligent, data-driven recommendation system.
By leveraging user similarity and preference patterns, the system generates accurate book suggestions that reflect individual reading tastes.
It serves as a foundational model for more advanced systems in personalized content recommendation and data-driven decision support.

© 2024 | Raghu Menni Lokanadhanaidu | IFT 511 – Analyzing Big Data
