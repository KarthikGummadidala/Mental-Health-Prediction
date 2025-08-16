# Mental Health Prediction Project

This project uses Instagram feed data to predict mental health conditions such as loneliness, anxiety, depression, happiness, and sadness.

# Data

The dataset is the collection of multiple datasets of total 70,000+ rows.
  
cleaned_text — text after lowercasing, URL/mention/hashtag/punctuation removal.

sentiment_score — TextBlob polarity score in [-1, 1] computed from cleaned_text.

specific_label — mapped emotion label derived from sentiment_score using your function:

>= 0.5 → happiness

(0, 0.5) → Loneliness

[−0.5, 0) → Depression

[−0.75, −0.5) → Anxiety

otherwise → Suicidal thoughts

# Environment & Requirements

Python 3.9+ (recommended)

tensorflow (Keras API)

pandas, numpy

scikit-learn

gensim

textblob

# Data Preparation

Load the dataset and inspect its structure.

Clean text by lowercasing, removing links, mentions, hashtags, and punctuation.

Optionally remove stopwords to reduce noise.

Generate sentiment scores and map them into emotion categories (happiness, depression, anxiety, etc.).

# Text Representation

Convert text into sequences of integers using tokenization.

Pad sequences to ensure uniform input length.

Encode categorical labels into one-hot vectors for classification.

# Model Building

Define a BiLSTM network that captures context in both forward and backward directions.

Add a custom Attention layer to focus on important words in a sentence.

Use dropout layers for regularization and compile the model with appropriate loss and optimizer.

# Training & Evaluation

Split the dataset into training and testing sets.

Train the model with early stopping to prevent overfitting.

Evaluate model performance using precision, recall, and F1-score.

# Deployment & Prediction

Save the trained model and reload it with the custom Attention layer.

Create a helper function to preprocess new text and predict its mental health category.

Use the model for real-world text inputs while being mindful of ethical considerations.

