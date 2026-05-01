# SDG Prediction with Sentence Transformers

## Project Overview
This project demonstrates how to classify text descriptions of projects to their most relevant Sustainable Development Goals (SDGs) using **Sentence Transformers** and **cosine similarity**. It provides a robust framework for automatically tagging projects, which is crucial for organizations like Digital Public Goods Alliance (DPGA) in categorizing initiatives. The solution emphasizes **explainability** by showing similarity scores and includes a simple **interactive user interface** for real-time predictions.

## Features
- **Semantic Similarity**: Utilizes `SentenceTransformer` to convert project descriptions and SDG definitions into high-dimensional vectors (embeddings).
- **Top-3 Prediction**: Identifies the top 3 most relevant SDGs for a given project description based on cosine similarity.
- **Explainability**: Provides similarity scores for each predicted SDG, offering transparency into the model's decisions.
- **DPG-based Dataset**: Evaluated on a simulated dataset inspired by Digital Public Goods (DPG) projects for practical relevance.
- **Interactive UI**: A simple Colab-based interface using `ipywidgets` for easy, real-time testing of project descriptions.

- ## This is a lightweight MVP of an SDG classification system.
- 
  Instead of training a heavy model, it uses semantic similarity via embeddings to map project descriptions to SDGs.
  This approach is:
- Fast
- Low-cost
- Suitable for API-based deployment

- ## Limitations:
- 
- Short SDG descriptions reduce accuracy
- No multi-label classification yet
- No domain-specific fine-tuning

## Setup and Usage

### 1. Run the Colab Notebook
Open this Colab notebook and run all cells sequentially. The notebook will:
- Install necessary libraries (`sentence-transformers`, `pandas`, `scikit-learn`).
- Load the Sentence Transformer model (`all-MiniLM-L6-v2`).
- Define the SDGs and their embeddings.
- Provide functions for SDG prediction and evaluation.
- Set up and evaluate the model on an example dataset and a DPG-based dataset.
- Launch an interactive UI for real-time predictions.

### 2. Interactive SDG Prediction UI
After running all cells, an interactive input box will appear. You can:
- **Enter a Project Description**: Type any project idea or description into the text area.
- **Click 'Predict SDG'**: The model will then display the top 3 predicted SDGs, their descriptions, and the similarity scores.

## Code Structure
- **`sdgs` dictionary**: Stores SDG codes and their textual descriptions.
- **`SentenceTransformer('all-MiniLM-L6-v2')`**: Loads the pre-trained model for generating embeddings.
- **`sdg_embeddings`**: Embeddings of all SDG descriptions.
- **`_predict_sdg_with_details(text)`**: Core function to predict top SDGs with their similarity scores for a given text.
- **`predict_sdg(text)`**: Returns the top predicted SDG (code and description).
- **`predict_sdg_top3(text)`**: Returns a list of top 3 SDG codes.
- **`evaluate(df)`**: Function to assess model performance on a DataFrame of projects, providing detailed output including predicted top 3 and accuracy.
- **`df_dpg`**: The simulated DPG-based dataset used for evaluation.
- **`ipywidgets` UI**: The interactive component allowing users to input text and get instant SDG predictions.

## Evaluation Results
The model's performance is evaluated using Top-3 Accuracy, which checks if the actual SDG is among the top 3 predicted SDGs. On the simulated DPG dataset, the model achieved a **Top-3 Accuracy of 0.6**.

### Example Evaluation Output:
```
--- Evaluation on DPG Dataset ---
Project: Developing open-source software for sustainable agriculture
Predicted Top 3:
  - SDG 11: Sustainable cities and communities (Similarity: 0.2528)
  - SDG 12: Responsible consumption and production (Similarity: 0.1995)
  - SDG 13: Climate action (Similarity: 0.1877)
Actual: SDG 2
--- For accuracy calculation, checking against: ['SDG 11', 'SDG 12', 'SDG 13']
...
Top-3 Accuracy: 0.6
```

## Conclusion
This project provides a practical and explainable solution for automated SDG classification, valuable for impact assessment and project categorization in various domains, especially within the context of Digital Public Goods.
