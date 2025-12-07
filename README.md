# CSC361 Project: Spam Filtering

## 📊 Dataset used
["Spam Mails Dataset" by Venkatesh Garnepudi](https://www.kaggle.com/datasets/venky73/spam-mails-dataset/data) on [Kaggle](https://www.kaggle.com)

---

## 📚 Libraries Used

- **string** — Punctuation definition
- **pandas** — CSV parsing
- **nltk** — Stopwords + Porter Stemmer
- **scikit-learn (sklearn)**:
  - CountVectorizer
  - Train/Test Split
  - RandomForestClassifier

---

## Workflow

### 1. **Import Libraries**

### 2. **Download NLTK Stopwords**
Stopwords are common words (e.g., *the, is, at, which*) that typically add noise in NLP tasks.
The NLTK corpus is downloaded to supply these terms.

### 3. **Load Dataset with Pandas**
Parse the CSV dataset into a DataFrame for easier manipulation and exploration.

### 4. **Text Preprocessing**
- Initialize **Porter Stemmer**
 (Reduces words to their root forms)
- Create an empty corpus
- Define the stopword set
- For each document:
 - Remove punctuation
 - Tokenize
 - Remove stopwords
 - Apply stemming
 - Append cleaned/stemmed text to the corpus

### 5. **Vectorization + Train/Test Split**
- Use **CountVectorizer** to convert text into numerical feature vectors
- Split features and labels into 80/20 train/test groups

### 6. **Model Definition & Training**
- Initialize a **RandomForestClassifier**
 - Uses multiple decision trees (ensemble)
 - Good at reducing overfitting
 - Configured to use all CPU cores (`n_jobs=-1`)
- Fit the model on the training data

### 7. **Evaluate Model**
- Test accuracy is approximately **~97%**

### 8. **Inference on a Sample**
1. Choose a sample text instance
2. Apply the same preprocessing steps
3. Add processed sample to a one-item corpus
4. Vectorize using the **same trained vectorizer**
5. Run inference with the classifier
6. Output the predicted label
7. Display the sample’s **actual class** for comparison
