# Drug-Recommendation-System
# Advanced Drug Recommendation System

This project implements an Advanced Drug Recommendation System that suggests medications based on user-inputted medical conditions. It leverages patient reviews by analyzing sentiment, effectiveness, side effects, and overall ratings to provide a ranked list of drug recommendations.

## 💊 Overview

The system processes two datasets (training and testing) containing drug reviews. It cleans the data, performs sentiment analysis on patient reviews using VADER, and further analyzes reviews for aspects like effectiveness and side effects. Based on a weighted scoring mechanism incorporating average ratings, sentiment scores, effectiveness, side effect concerns, review counts, and usefulness counts, the system recommends the top N drugs for a given medical condition. It also handles fuzzy matching for condition names to improve user experience.

## ✨ Features

*   **Data Loading & Preprocessing:** Loads and cleans drug review data from CSV files.
*   **Sentiment Analysis:** Utilizes VADER (Valence Aware Dictionary and sEntiment Reasoner) to determine the sentiment (positive, negative, neutral) of patient reviews.
*   **Aspect-Based Sentiment Analysis:**
    *   Identifies mentions of drug effectiveness and their associated sentiment.
    *   Identifies mentions of side effects and their associated sentiment.
*   **Weighted Recommendation Score:** Calculates a comprehensive score for each drug based on:
    *   Average user rating
    *   Overall sentiment score
    *   Effectiveness score
    *   Side effects score (negatively weighted)
    *   Number of ratings
    *   Total useful count of reviews
*   **Fuzzy Condition Matching:** Suggests similar medical conditions if the user's input doesn't exactly match available conditions.
*   **Interactive Command-Line Interface (CLI):** Allows users to input a condition and receive formatted drug recommendations.
*   **Detailed Output:** Provides recommendations including:
    *   Drug name
    *   Average rating (with visual stars)
    *   Patient satisfaction (sentiment percentage with visual bar)
    *   Treatment effectiveness (percentage with visual bar)
    *   Side effects risk level (with emoji indicators)
    *   Number of patient reviews
    *   Sample patient reviews

## ⚙️ Prerequisites

*   Python 3.x
*   pip (Python package installer)

## 🛠️ Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/your-repository-name.git
    cd your-repository-name
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```bash
    python -m venv venv
    # On Windows
    venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```

3.  **Install the required Python libraries:**
    ```bash
    pip install vaderSentiment pandas scikit-learn numpy
    ```
    *(Note: `difflib` is part of the Python standard library and does not need to be installed separately.)*

## 📊 Dataset

The system uses two CSV files for training and testing:
*   `drugsComTrain_raw.csv`
*   `drugsComTest_raw.csv`

These files are expected to contain columns such as `condition`, `drugName`, `rating`, `review`, and `usefulCount`.

**Important:**
Make sure these files are present. You will need to update the paths to these files in the `main()` function within the script if they are not in `C:\Final project\project\`.

```python
# In the main() function, update these paths:
train_path = 'path/to/your/drugsComTrain_raw.csv'
test_path = 'path/to/your/drugsComTest_raw.csv'

##🚀 How to Run
Ensure you have installed all prerequisites and placed the dataset files in the correct location (or updated the paths in the script).
If you've extracted the Python code from the Jupyter Notebook into a .py file (e.g., drug_recommender.py), run it from your terminal:
python drug_recommender.py
