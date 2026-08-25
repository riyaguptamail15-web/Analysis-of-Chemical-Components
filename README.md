# Analysis of Chemical Components: Content-Based Cosmetic Recommendation System

A Machine Learning and Data Analytics project that recommends chemically similar cosmetic products by analyzing their ingredient compositions instead of user ratings or purchase history.

**Internship:** MedTourEasy (MTE) Data Analytics Internship

---

## Project Overview

Choosing the right skincare product is often difficult because ingredient lists are long and complex. Two moisturizers from different brands may have nearly identical formulations, while products with similar claims may contain completely different chemical compositions.

This project develops a **content-based recommendation system** that identifies similar cosmetic products using their ingredients. The workflow includes data preprocessing, Natural Language Processing (tokenization), feature engineering, dimensionality reduction using **t-SNE**, and an interactive visualization built with **Bokeh**.

---

## Problem Statement

Develop a recommendation system that can:

* Filter products based on category and skin type
* Process cosmetic ingredient lists using NLP techniques
* Convert ingredients into machine-readable numerical features
* Visualize chemically similar products using Machine Learning
* Validate recommendations through ingredient comparison

---

## Dataset Information

| Feature            | Value                     |
| ------------------ | ------------------------- |
| Dataset            | Sephora Cosmetics Dataset |
| Total Products     | 1,472                     |
| Filtered Products  | 190 Moisturizers          |
| Skin Type          | Dry Skin                  |
| Unique Ingredients | 2,233                     |

### Dataset Attributes

* **Brand** — Cosmetic brand name
* **Name** — Product name
* **Label** — Product category
* **Price** — Retail price
* **Rank** — Customer rating
* **Ingredients** — Complete ingredient list
* **Dry** — Indicates suitability for dry skin
* **Normal** — Indicates suitability for normal skin
* **Oily** — Indicates suitability for oily skin
* **Sensitive** — Indicates suitability for sensitive skin

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Bokeh
* Jupyter Notebook
* Git & GitHub

---

## Project Workflow

### Task 1 — Data Loading & Exploration

* Imported the Sephora cosmetics dataset using Pandas.
* Explored dataset structure, columns, and product categories.
* Performed initial exploratory data analysis.

### Task 2 — Data Filtering

* Filtered only **Moisturizers**.
* Selected products suitable for **Dry Skin**.
* Reset indexing to create a clean working dataset.

### Task 3 — Ingredient Tokenization

* Converted ingredient text to lowercase.
* Tokenized ingredient lists into individual ingredients.
* Generated a vocabulary of **2,233 unique ingredients**.

### Task 4 — Document-Term Matrix (DTM)

Created a binary matrix where:

* Rows represent cosmetic products.
* Columns represent unique ingredients.
* Values indicate ingredient presence (**1**) or absence (**0**).

### Task 5 — One-Hot Encoding

Implemented a custom one-hot encoder to convert each moisturizer into a **2233-dimensional binary feature vector** suitable for machine learning.

### Task 6 — Feature Matrix Generation

Populated the complete binary feature matrix for all **190 moisturizer products** using the one-hot encoder.

### Task 7 — Dimensionality Reduction using t-SNE

Applied **t-Distributed Stochastic Neighbor Embedding (t-SNE)** to reduce the 2233-dimensional feature space into two dimensions while preserving local similarity between products.

### Task 8 — Interactive Visualization

Developed an interactive scatter plot using **Bokeh**, where each point represents a moisturizer positioned according to its ingredient similarity.

### Task 9 & 10 — Hover Interaction & Visualization

Enhanced the visualization by adding interactive hover functionality displaying:

* Brand
* Product Name
* Price
* Customer Rating

The graph also supports zooming, panning, resetting, and saving.

### Task 11 — Recommendation Validation

Validated the recommendation system by comparing both **similar** and **dissimilar** products through ingredient overlap analysis, confirming the effectiveness of the content-based recommendation approach.

---

## Machine Learning Pipeline

1. Load & Explore Dataset
2. Filter Moisturizers for Dry Skin
3. Tokenize Ingredient Lists
4. Create Document-Term Matrix
5. Apply One-HHot Encoding
6. Generate Binary Feature Matrix
7. Reduce Dimensions using t-SNE
8. Visualize Product Similarity with Bokeh
9. Validate Recommendations using Ingredient Comparison

This project uses **unsupervised learning** because it identifies similarity patterns without labeled output classes.

---

## Results

* Filtered **190** moisturizers from **1,472** cosmetic products.
* Identified **2,233 unique ingredients**.
* Constructed a **190 × 2233** binary Document-Term Matrix.
* Applied **t-SNE** to visualize chemically similar products.
* Built an interactive recommendation map using **Bokeh**.
* Validated both similar and dissimilar formulations through ingredient overlap analysis.

---

## Visualization

The interactive **t-SNE scatter plot** below represents each moisturizer as a point in a two-dimensional space. Products positioned closer together have more similar ingredient compositions, while products farther apart represent chemically different formulations.

![t-SNE Visualization] (images/tsne_visualization.png)

---

## Validation Summary

### Similar Product Analysis (Products 32, 75 & 80)

The comparison showed varying levels of ingredient similarity:

* **Products 75 & 80** shared the highest number of common ingredients, indicating closely related moisturizing formulations.
* **Products 32 & 80** shared only one common ingredient (*Glycyrrhiza Glabra/Licorice Root Extract*).
* **Products 32 & 75** showed no exact token matches.

**Why 0 or 1 common ingredient?**

This project performs **basic tokenization** with exact string matching. Minor formatting differences—such as extra spaces, `*`/`**` symbols, singular vs. plural wording, or slight naming variations (e.g., `caprylic/capric triglycerides` vs. `caprylic/ capric triglyceride`)—are treated as different tokens. Therefore, the actual chemical similarity may be higher than the reported overlap, and advanced text normalization would improve matching accuracy.

### Dissimilar Product Analysis (Products 128 & 152)

Products **128 and 152** shared **0 common ingredients**, indicating genuinely different chemical formulations rather than formatting differences. This validates that products positioned far apart in the t-SNE space represent highly dissimilar ingredient compositions.

---

## Repository Structure

```text
Analysis-of-Chemical-Components/
│
├── analysis.ipynb              # Complete project notebook
├── cosmetics.csv               # Sephora cosmetics dataset
├── requirements.txt            # Required Python libraries
├── .gitignore                  # Ignored Jupyter checkpoint files
├── README.md                   # Project documentation
└── images/
    └── tsne_visualization.png  # Bokeh visualization screenshot
```

---

## Future Improvements

* Normalize ingredient synonyms and naming conventions.
* Implement cosine similarity for Top-5 product recommendations.
* Build a Streamlit web application for user interaction.
* Add ingredient search and product recommendation interface.

---

## Author

**Riya Gupta**

B.Tech Electronics & Communication Engineering

Data Analytics Project completed as part of the **MedTourEasy (MTE) Internship**.
MedTourEasy Internship (MTE)**.
