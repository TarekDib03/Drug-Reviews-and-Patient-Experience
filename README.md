
## Drug Review Clustering & Patient Experience Analysis

📌 **Overview**

This project applies Natural Language Processing (NLP) and unsupervised machine learning to analyze patient drug reviews, with the goal of uncovering patterns in treatment effectiveness and side-effect experiences.

Using text data from patient reviews, the analysis identifies clusters of treatment experiences and evaluates whether patients form distinct groups or a continuous spectrum.

🎯 **Objectives**

- Transform unstructured text into meaningful numerical features
- Identify patient segments using clustering
- Analyze relationships between effectiveness, side effects, and satisfaction
- Provide interpretable, data-driven insights

🧰 **Methodology*

1. Text Preprocessing

- Lowercasing and noise removal
- Stopword filtering (standard + domain-specific)
- Phrase normalization (e.g., side_effects, no_side_effects)
- Lemmatization

2. Feature Engineering

- TF-IDF Vectorization (unigrams + bigrams)
- Captures important medical phrases (e.g., “abdominal pain”, “acid reflux”)

3. Dimensionality Reduction

- Truncated SVD applied to reduce high-dimensional sparse features
- Preserves key semantic structure while improving computational efficiency

4. Clustering

- K-Means Clustering applied on reduced feature space
- Tested multiple values of k using:
    - Elbow Method
    - Silhouette Score
    - Davies–Bouldin Index

5. Cluster Profiling

Clusters were analyzed based on:

- Effectiveness levels
- Side-effect severity
- Patient ratings
- Sentiment scores

📊 **Key Results*

1. Cluster Evaluation

- Silhouette Score: ~0.07 (low)
- Davies–Bouldin Index: ~3.12 (high)
- Elbow Curve: No clear inflection point

👉 Indicates weak cluster separation

🧠 **Key Insights**

- Patient experiences form a continuous spectrum, not distinct groups
- A 3-cluster solution was retained for interpretability:
    - High tolerability (dominant group)
    - Moderate burden
    - Higher adverse risk

- Patient ratings (~6.9–7.2) and sentiment (~neutral) remained consistent across clusters

👉 Suggesting:

Patients often tolerate side effects if treatment is effective

📈 **Visualization**

- Faceted bar charts (Plotly) showing:
    - Effectiveness vs Side Effects by Cluster

- Highlighted:
    - ⭐ Best-performing cluster
    - Clean labeling and percentage distributions

**Limitations**

- Weak cluster separation limits predictive use
- High overlap in language across reviews
- K-Means may not capture complex patterns in text data

💡 **Key Takeaway**

Patient treatment experiences are best understood as a continuum, where clustering reveals meaningful patterns of variation rather than rigid segments.

🛠️ **Tech Stack**

- Python
- Pandas, NumPy
- Scikit-learn
- NLTK
- Seabon, Matplotlib
