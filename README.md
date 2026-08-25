# Analysis of Chemical Components: Content-Based Cosmetic Recommendation System

A machine learning and data analytics project that recommends similar cosmetic products by analyzing their chemical ingredients instead of user ratings or purchase history.

This project was completed as part of the **MedTourEasy (MTE) Data Analytics Internship** using a real-world Sephora cosmetics dataset containing **1,472 skincare and beauty products**.

---

## Project Overview

Choosing skincare products can be confusing because ingredient labels are long and difficult to interpret. Two moisturizers may have nearly identical formulations even if they belong to different brands.

The objective of this project is to build a **content-based recommendation system** that identifies products with similar ingredient compositions. Products are converted into numerical representations using text processing techniques, visualized using machine learning, and compared through ingredient similarity.

---

## Problem Statement

Develop a recommendation system that:

- Filters products based on category and skin type
- Processes cosmetic ingredient lists
- Converts ingredients into machine-readable features
- Visualizes product similarity using dimensionality reduction
- Compares chemically similar cosmetic products

---

## Dataset

- **Source:** Sephora Cosmetics Dataset
- **Total Products:** 1,472
- **Category Used:** Moisturizers
- **Skin Type:** Dry Skin

Important features include:

| Column | Description |
|---------|-------------|
| Brand | Cosmetic brand |
| Name | Product name |
| Label | Product category |
| Price | Product price |
| Rank | Customer rating |
| Ingredients | Complete ingredient list |
| Dry | Suitability for dry skin |

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Bokeh
- Jupyter Notebook

---

## Project Workflow

### 1. Data Loading & Exploration

- Imported the dataset using Pandas
- Inspected data structure and column types
- Analyzed distribution of cosmetic categories

### 2. Data Filtering

- Selected only **Moisturizers**
- Filtered products suitable for **Dry Skin**
- Reset dataframe indexing for clean analysis

### 3. Ingredient Tokenization

- Converted ingredient lists to lowercase
- Split each ingredient string into individual tokens
- Created a dictionary of unique ingredients

### 4. Feature Engineering

- Constructed a **Document-Term Matrix (DTM)**
- Applied **One-Hot Encoding** to represent ingredient presence
- Generated binary feature vectors for every product

### 5. Machine Learning

Applied **t-SNE (t-Distributed Stochastic Neighbor Embedding)** to reduce hundreds of ingredient dimensions into two-dimensional coordinates while preserving local similarity between products.

### 6. Interactive Visualization

Built an interactive scatter plot using **Bokeh**, allowing users to:

- View product clusters
- Hover over products
- Display brand, product name, price, and rating

### 7. Product Comparison

Compared ingredient compositions of similar cosmetic products to validate recommendation quality.

---

## Machine Learning Concept

This project uses **unsupervised learning** for dimensionality reduction.

- **Input:** Ingredient-based binary vectors
- **Technique:** t-SNE
- **Output:** Two-dimensional representation of chemically similar products

The closer two products appear on the visualization, the more similar their ingredient compositions are likely to be.

---

## Key Learning Outcomes

- Data preprocessing
- Natural Language Processing (Tokenization)
- Feature Engineering
- One-Hot Encoding
- Document-Term Matrix creation
- Dimensionality Reduction with t-SNE
- Interactive Data Visualization
- Content-Based Recommendation Systems

---

## Repository Structure

Analysis-of-Chemical-Components/
├── analysis.ipynb
├── cosmetics.csv
├── README.md
├── requirements.txt
└── .gitignore

---

## Author

**Riya Gupta**

Data Analytics Project completed during the **MedTourEasy Internship (MTE)**.