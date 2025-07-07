# **Hack the GLOBE Data Challenge: Key Terms, Libraries, & Cross-Cutting Knowledge**

This document provides a lexicon of key terms, highlights essential Python libraries, and identifies crucial cross-cutting knowledge domains relevant to each [stage of the data science process](https://github.com/IGES-Geospatial/Hack-the-GLOBE-2025/blob/main/scaffolding/Further%20Reading/03%20Hack%20the%20GLOBE%20-%20Key%20Stages%20%26%20Objectives%20of%20the%20Data%20Science%20Process.md).

## **1\. Define the Problem & Data Acquisition**

### **Key Terms:**

* **Unstructured Data:** Text, images, audio, video, sensor data, log files, social media posts.  
* **Problem Statement:** A concise description of the issue to be addressed.  
* **Objective:** Specific, measurable, achievable, relevant, time-bound (SMART) goals.  
* **Data Source:** Origin of data (e.g., web scraping, APIs, databases, filesystems).  
* **API (Application Programming Interface):** A set of rules for how software components should interact.  
* **Schema:** The organization or structure of a database or data model.

### **Relevant Python Libraries:**

* **requests:** For making HTTP requests to APIs.  
* **BeautifulSoup / Scrapy:** For web scraping.  
* **pandas:** For initial data loading and basic manipulation (e.g., reading CSV, JSON).  
* **os, glob:** For file system navigation and file loading.

### **Cross-Cutting Knowledge & Domains:**

* **Domain Expertise:** Understanding the context and subject matter of the data (e.g., if analyzing medical text, basic medical knowledge is crucial).  
* **Ethical AI/Data Practices:** Awareness of bias, privacy, and responsible data use from the outset.  
* **Project Management:** Defining scope, timelines, and deliverables.

## **2\. Exploratory Data Analysis (EDA) & Preprocessing**

### **Key Terms:**

* **Exploratory Data Analysis (EDA):** An iterative process of analyzing data to summarize their main characteristics, often with visual methods.  
* **Data Profiling:** Examining the data available and collecting statistics/information about it.  
* **Data Types:** Numerical (int, float), Categorical (nominal, ordinal), Text, DateTime.  
* **Descriptive Statistics:** Mean, median, mode, standard deviation, variance, quartiles.  
* **Data Distribution:** How data values are spread across a range (e.g., normal, skewed).  
* **Missing Values (Null Values):** Data points that are not recorded or are absent.  
* **Imputation:** Filling in missing values with estimated ones.  
* **Outliers:** Data points significantly different from other observations.  
* **Noise:** Random error or variance in a measured variable.  
* **Data Consistency:** Uniformity and accuracy of data over time and across different datasets.  
* **Feature Engineering:** The process of creating new features from raw data to improve model performance.  
* **Metadata:** Data that provides information about other data.  
* **Correlation:** A statistical measure that indicates the extent to which two or more variables fluctuate together.  
* **Causation:** A relationship where one event (the cause) directly influences a second event (the effect).  
* **Multicollinearity:** A phenomenon in which two or more predictor variables in a multiple regression model are highly correlated.

### **Relevant Python Libraries:**

* **pandas:** Extensive library for data manipulation, profiling (.describe(), .info(), .value\_counts(), .isnull().sum()).  
* **numpy:** Numerical operations, handling NaN values.  
* **matplotlib.pyplot, seaborn:** For data visualization (histograms, box plots, scatter plots, heatmaps).  
* **scipy.stats:** For statistical tests (e.g., Z-score).  
* **scikit-learn:** For outlier detection algorithms (e.g., IsolationForest, LocalOutlierFactor).  
* **NLTK (Natural Language Toolkit), spaCy:** For text specific preprocessing (tokenization, stemming, lemmatization, stop word removal, POS tagging, named entity recognition). \[*Unlikely to be used in this hackathon, but it can be useful and offer more traceable/interpretable processing of natural language than, say, calling an LLM API. \-A.C.\]*  
* **Pillow (PIL Fork), OpenCV (cv2):** For image specific preprocessing (resizing, cropping, color conversion, feature extraction).

### **Cross-Cutting Knowledge & Domains:**

* **Statistics:** Understanding of distributions, hypothesis testing, correlation vs. causation.  
* **Data Visualization Principles:** Effective use of charts, color, and labels to convey information.  
* **Domain Expertise:** Critical for identifying relevant features, understanding data nuances, and interpreting outliers.  
* **Data Quality Management:** Best practices for ensuring data accuracy, completeness, and consistency throughout the analytical process.

## **3\. Data Preparation for Modeling**

### **Key Terms:**

* **Feature Scaling:** Methods to standardize the range of independent variables or features.  
* **Normalization:** Scaling data to a fixed range, typically 0 to 1 (Min-Max Scaling).  
* **Standardization:** Scaling data to have a mean of 0 and a standard deviation of 1 (Z-score normalization).  
* **Categorical Variables:** Variables that take on values from a fixed set of categories.  
* **One-Hot Encoding:** Converting categorical variables into a numerical format by creating binary columns.  
* **Label Encoding:** Assigning a unique integer to each category.  
* **Ordinal Encoding:** Label encoding where the integer order has meaning (e.g., small, medium, large).  
* **Dimensionality Reduction:** Reducing the number of random variables under consideration.  
* **Curse of Dimensionality:** Various problems that arise when working with high-dimensional data, such as sparsity and increased computational cost.  
* **Principal Component Analysis (PCA):** A linear dimensionality reduction technique.  
* **Eigenvalues/Eigenvectors:** Fundamental concepts in PCA, representing variance and directions.  
* **Scree Plot:** A plot used in PCA to determine the number of principal components to retain.  
* **t-SNE (t-Distributed Stochastic Neighbor Embedding):** A non-linear dimensionality reduction technique especially suited for visualizing high-dimensional datasets.  
* **UMAP (Uniform Manifold Approximation and Projection):** A more recent non-linear dimensionality reduction technique often faster than t-SNE.

### **Relevant Python Libraries:**

* **scikit-learn.preprocessing:** MinMaxScaler, StandardScaler, OneHotEncoder, LabelEncoder, OrdinalEncoder.  
* **scikit-learn.decomposition:** PCA.  
* **sklearn.manifold:** TSNE.  
* **umap-learn:** For UMAP implementation.

### **Cross-Cutting Knowledge & Domains:**

* **Linear Algebra:** Understanding vectors, matrices, and transformations (essential for PCA).  
* **Mathematical Foundations of ML Algorithms:** Knowledge of why scaling is necessary for certain algorithms (e.g., distance-based algorithms).  
* **Computational Efficiency:** Awareness of how dimensionality reduction can improve processing time.

## **4\. Modeling & Interpretation**

### **Key Terms:**

* **Unsupervised Learning:** Machine learning tasks that infer patterns from a dataset without reference to known, or labeled, outcomes.  
* **Clustering:** The task of grouping a set of objects in such a way that objects in the same group (a cluster) are more similar to each other than to those in other groups.  
* **K-Means Clustering:** An iterative algorithm that partitions n observations into k clusters.  
* **Centroid:** The center point of a cluster.  
* **Elbow Method:** A heuristic method for determining the optimal number of clusters in K-Means.  
* **DBSCAN (Density-Based Spatial Clustering of Applications with Noise):** A density-based clustering algorithm capable of finding arbitrarily shaped clusters and identifying noise points.  
* **Hierarchical Clustering:** Builds a hierarchy of clusters.  
* **Agglomerative Clustering:** A type of hierarchical clustering that starts with individual points as clusters and merges them.  
* **Anomaly Detection (Outlier Detection):** Identifying items, events, or observations that do not conform to an expected pattern.  
* **Model Evaluation:** Assessing the performance of a model.  
* **Internal Evaluation Metrics (Clustering):** Metrics that use only the inherent structure of the data (e.g., Silhouette Score, Davies-Bouldin Index).  
* **External Evaluation Metrics (Clustering):** Metrics that compare the clustering results to a known ground truth (e.g., Adjusted Rand Index, Homogeneity, Completeness).  
* **Interpretability:** The degree to which a human can understand the cause of a decision.  
* **Actionable Insights:** Conclusions derived from data analysis that can lead to specific, beneficial actions.  
* **Feature Importance:** The degree to which a specific feature contributes to a model's prediction or a cluster's definition.

### **Relevant Python Libraries:**

* **scikit-learn.cluster:** KMeans, DBSCAN, AgglomerativeClustering.  
* **scikit-learn.metrics:** silhouette\_score, davies\_bouldin\_score, adjusted\_rand\_score, homogeneity\_score, completeness\_score.  
* **eli5, LIME, SHAP:** For model interpretability (though more commonly used with supervised models, some concepts may apply). \[*@Advaith \- anything you can teach us about Captum?\]*

### **Cross-Cutting Knowledge & Domains:**

* **Machine Learning Fundamentals:** Core concepts of supervised vs. unsupervised learning.  
* **Algorithm-Specific Knowledge:** Understanding the assumptions and limitations of different clustering algorithms.  
* **Critical Thinking:** Interpreting quantitative results qualitatively.  
* **Business Acumen:** Translating analytical findings into relevant business or domain context.

## **5\. Communication & Reporting**

### **Key Terms:**

* **Data Visualization:** The graphical representation of information and data.  
* **Dashboard:** A visual display of all information relevant to achieving one or more objectives.  
* **Infographic:** A visual representation of information or data.  
* **Storytelling with Data:** Presenting data in a narrative format to convey insights effectively.  
* **Executive Summary:** A concise overview of a report or proposal, typically placed at the beginning.  
* **Documentation:** Written materials that explain the data, code, process, and findings.  
* **Reproducibility:** The ability to replicate the findings of a study or experiment.

### **Relevant Python Libraries:**

* **matplotlib.pyplot, seaborn:** For static and statistical plots.  
* **Plotly, Bokeh:** For interactive visualizations (useful for dashboards).  
* **WordCloud:** Specifically for generating word clouds from text.  
* **Jupyter Notebooks/JupyterLab:** For combining code, visualizations, and narrative in a single document (excellent for reporting and reproducibility).  
* **Markdown:** For structuring textual reports.

### **Cross-Cutting Knowledge & Domains:**

* **Communication Skills:** Verbal and written communication, presentation skills.  
* **Design Principles:** Understanding visual hierarchy, color theory, and user experience (UX) for effective visualizations.  
* **Technical Writing:** Clearly documenting code, methodologies, and results.  
* **Audience Empathy:** Tailoring communication to the technical and domain knowledge level of the audience. \[*If you’ve read this far, I’ll admit that* *I could do better with this \- and I’m relying on input from Hack the GLOBE students to help me “tune my model” \- A.C.\]*

