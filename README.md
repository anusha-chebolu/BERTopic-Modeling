# BERTopic Analysis of AI in Healthcare Discussions on Reddit

## Project Overview

This repository contains an analysis of public discussions surrounding the use of Artificial Intelligence (AI) in healthcare, as observed on Reddit. The study applies BERTopic modeling to extract predominant topics from a large corpus of Reddit comments. The analysis aims to provide insights into the public's perceptions and debates regarding AI's role in healthcare, offering a granular view of the topics being discussed.

## Data

### Data Collection

The data for this study was collected from 38 Reddit posts across 10 subreddits known for vibrant discussions on AI and healthcare, including:

- `/r/ChatGPT`
- `/r/singularity`
- `/r/medicine`
- `/r/technology`
- `/r/MachineLearning`
- `/r/ArtificialIntelligence`
- `/r/healthcare`
- `/r/AskReddit`
- `/r/datascience`
- `/r/OpenAI`

In total, 1,131 comments were extracted using the Python Reddit API Wrapper (PRAW). The data collection focused on first-level comments from posts made between April 2023 and April 2024.

### Data Preprocessing

The preprocessing steps included:

- **Filtering out bot contributions:** Comments from bots and flagged content (e.g., 'deleted' or 'removed') were excluded to ensure data quality.
- **Data Structuring:** The dataset was organized in a DataFrame, with columns for comment ID, username, the month and year of the comment, and the comment text.

## Analysis

### Topic Modeling with BERTopic

BERTopic, an unsupervised machine learning technique, was used to model the topics discussed in the Reddit comments. The process involved:

1. **Text Embedding:** Comments were transformed into embeddings using the pre-trained Sentence Transformer model `all-MiniLM-L6-v2`.
2. **Dimensionality Reduction:** The embeddings were reduced in dimensionality using UMAP (Uniform Manifold Approximation and Projection).
3. **Clustering:** HDBSCAN (Hierarchical Density-Based Spatial Clustering of Applications with Noise) was applied to group similar text embeddings into clusters, each representing a potential topic.
4. **Topic Extraction:** Topics were extracted and refined using components like `KeyBERTInspired` for keyword extraction and `MaximalMarginalRelevance` for improving topic distinctiveness.

The analysis identified 15 distinct topics, with key topics focusing on AI's impact on healthcare costs, patient care, diagnostic processes, and the business side of healthcare.

### Visualizations

- **Hierarchical Clustering:** Visualizes the clustering of topics based on the similarity of their constituent words.
- **Intertopic Distance Map:** Provides a visual representation of the different topic clusters and their relationships.
- **Bar Charts:** Show the significance of words within selected topics, illustrating the different aspects of AI in healthcare being discussed.
