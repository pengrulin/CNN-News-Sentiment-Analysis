# CNN Articles Sentiment Analysis

## Overview
This project leverages Natural Language Processing (NLP) to analyze CNN articles published from 2011 to 2022. The goal is to uncover the underlying sentiment and tone of the news reports to better understand the platform's messaging and potential biases. By cleaning and processing the dataset, applying tokenization, stop word removal, stemming, and lemmatization, we will utilize the NLTK sentiment analyzer to gauge the sentiment across various text fields. Additionally, market basket analysis and timeline visualizations will be employed to identify patterns in sentiment across different article sections and over time.

## Installation
To set up your environment for running the `CNN_Articles_Sentiment_Analysis.ipynb` notebook, follow these steps:

1. **Create a `requirements.txt` file** with the following contents:
   ```
   pandas
   numpy
   nltk
   scikit-learn
   matplotlib
   seaborn
   ```
2. **Install the required packages** by running:
   ```bash
   pip install -r requirements.txt
   ```
3. **Download NLTK Data:**
   Run the following commands in a Python shell to download the necessary NLTK datasets:
   ```python
   import nltk
   nltk.download('vader_lexicon')
   nltk.download('stopwords')
   nltk.download('punkt')
   ```

## Project Structure

### Part 1: Data Exploration and Cleaning
- **Dataset Details:**  
  The dataset is sourced from Kaggle (CNN Articles, Raw Data) and comprises 38,000 rows and 9 columns. The columns include:
  - `author`
  - `date_published`
  - `part_of`
  - `article_section`
  - `url`
  - `headline`
  - `description`
  - `keywords`
  - `alternative_headline`
  
- **Cleaning Steps:**  
  - **Drop Irrelevant Columns:** Remove the `url` column as it is not needed for sentiment analysis.
  - **Data Integrity Checks:** Identify and address missing values and standardize text strings.
  - **Text Cleaning:** Remove special characters and punctuation to ensure consistency.
  - **Challenges Addressed:**  
    - Handle 'Anonymous' entries in the `author` column.
    - Address a small number of missing values (0.02% in the `article text` column).
    - Perform undersampling on 20% of the data to manage processing efficiency.

### Part 2: NLP Pre-processing
- **Tokenization:**  
  Divide the text into tokens to facilitate further analysis.
- **Stop Word Removal:**  
  Eliminate common stop words that do not contribute meaningful information.
- **Stemming and Lemmatization:**  
  Reduce words to their base or root forms to enhance the accuracy of sentiment analysis.

### Part 3: Sentiment Analysis
- **Methodology:**  
  Use the NLTK sentiment analyzer to evaluate sentiment on multiple text fields:
  - `headline`
  - `description`
  - `keywords`
  - `alternative_headline`
- **Process:**  
  - Analyze each text field separately.
  - Maintain individual sentiment scores.
  - Average the scores to form a unified sentiment metric for each article.

### Part 4: Market Basket Analysis & Visualization
- **Market Basket Analysis:**  
  Investigate if certain article sections consistently exhibit higher-than-average positive sentiment.
- **Timeline Visualization:**  
  Plot sentiment trends over the years to observe changes in the overall tone of CNN articles from 2011 to 2022.

### Part 5: Business Relevance
- **Media Optimization:**  
  Insights from this analysis can help media companies tailor content based on audience sentiment, enhancing engagement.
- **Content Strategy:**  
  Understanding sentiment across topics can inform which tones and topics resonate best with audiences and guide content production.
- **Industry Impact:**  
  As CNN is one of the top news providers in the US, these insights could influence broader media strategies and public perception management.

### Part 6: Challenges
- **Data Cleaning:**  
  - Variability due to web crawling, leading to inconsistencies in the dataset.
  - Handling entries labeled as 'Anonymous' in the `author` column.
  - Managing a small fraction of missing values.
- **Data Sampling:**  
  Implementing undersampling (20% of the data) to reduce computational load without compromising analysis quality.

### Part 7: Appendix
- **Column Descriptions:**
  - **author:** The individual who authored the article.
  - **date_published:** The date the article was published on CNN.
  - **part_of:** The broader categorization of the article as defined by CNN.
  - **article_section:** A more specific sector within the article categorization.
  - **url:** The link to the article (removed during cleaning).
  - **headline:** The main title of the article.
  - **description:** A brief summary of the article.
  - **keywords:** Key terms summarizing the article.
  - **alternative_headline:** The secondary title of the article.

## Usage
To run this project:
1. **Setup:**  
   Install the required libraries using the provided `requirements.txt`.
2. **Notebook Execution:**  
   Open the `CNN_Articles_Sentiment_Analysis.ipynb` notebook in Jupyter Notebook or Jupyter Lab.
3. **Run Cells:**  
   Execute the notebook cells in sequential order to perform data cleaning, NLP preprocessing, sentiment analysis, and visualization.

## Collaborators
- Ashley Mercado
- Leonardo Trucios
- Lyushen Song
- Mauro Wang
