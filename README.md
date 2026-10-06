# 🌍 Language Translator / Language Detection

A simple Machine Learning project that predicts the **language of a given text** using Natural Language Processing (NLP) techniques.

The project uses **CountVectorizer** to convert text into numerical features and **Multinomial Naive Bayes** to classify the text into its corresponding language.

---

## 📌 Project Overview

Language identification is an important NLP task where the objective is to determine which language a given text belongs to.

In this project:

1. A language dataset is loaded using Pandas.
2. The dataset is analyzed for missing values and language distribution.
3. Text data is converted into numerical features using `CountVectorizer`.
4. The dataset is divided into training and testing sets.
5. A `MultinomialNB` model is trained.
6. The model is evaluated on the test dataset.
7. Users can enter their own text and get the predicted language.

---

## 🧠 Machine Learning Workflow

```text
Dataset
   ↓
Data Analysis
   ↓
Text Extraction
   ↓
CountVectorizer
   ↓
Train-Test Split
   ↓
Multinomial Naive Bayes
   ↓
Model Evaluation
   ↓
User Input
   ↓
Predicted Language
```

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **NLP**
* **CountVectorizer**
* **Multinomial Naive Bayes**
* **Jupyter Notebook**

---

## 📂 Project Structure

```text
Language-Translator/
│
├── Language Translator.ipynb
│
├── Language Translator/
│   └── language.csv
│
└── README.md
```

---

## 📊 Dataset

The project uses a CSV dataset named:

```text
language.csv
```

The dataset contains text samples along with their corresponding language labels.

The main columns used are:

| Column     | Description                     |
| ---------- | ------------------------------- |
| `Text`     | Text sample used for prediction |
| `language` | Language label/class            |

---

## 🔍 Data Analysis

The dataset is inspected using Pandas to check:

### First few records

```python
data.head()
```

### Missing values

```python
data.isnull().sum()
```

### Language distribution

```python
data['language'].value_counts()
```

### Data types

```python
data.dtypes
```

---

## 🔢 Feature Extraction

Machine Learning models cannot directly process raw text.

Therefore, `CountVectorizer` is used to convert the text into numerical features.

```python
from sklearn.feature_extraction.text import CountVectorizer

cv = CountVectorizer()
X = cv.fit_transform(x)
```

This converts the text into a matrix of numerical word-count features.

---

## 🤖 Model Used

### Multinomial Naive Bayes

The project uses the `MultinomialNB` algorithm, which is well suited for text classification problems.

```python
from sklearn.naive_bayes import MultinomialNB

model = MultinomialNB()
model.fit(X_train, y_train)
```

---

## ✂️ Train-Test Split

The dataset is divided into training and testing data using `train_test_split`.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.33,
    random_state=42
)
```

The test size is **33%**, while the remaining **67%** is used for training.

---

## 📈 Model Evaluation

The trained model is evaluated using its `.score()` method:

```python
model.score(X_test, y_test) * 100
```

This gives the classification accuracy on the test dataset.

> The exact accuracy depends on the dataset used when running the notebook.

---

## 💬 Making Predictions

After training, users can enter their own text:

```python
user = input("Enter your Text : ")

Data = cv.transform([user]).toarray()

output = model.predict(Data)

print(output)
```

### Example

```text
Enter your Text : Bonjour, comment allez-vous ?
```

The model will return the predicted language label.

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone <your-repository-url>
```

### 2. Navigate to the Project

```bash
cd Language-Translator
```

### 3. Install Dependencies

```bash
pip install pandas numpy scikit-learn jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

### 5. Open

```text
Language Translator.ipynb
```

### 6. Run the Cells

Run the notebook cells sequentially and provide your own text when prompted.

---

## 📦 Required Libraries

```text
pandas
numpy
scikit-learn
jupyter
```

---

## 🎯 Key Concepts Demonstrated

* Data loading using Pandas
* Exploratory data analysis
* Missing-value checking
* Text classification
* Natural Language Processing
* Feature extraction
* `CountVectorizer`
* Train-test splitting
* Multinomial Naive Bayes
* Model evaluation
* Real-time user prediction

---

## 🔮 Future Improvements

This project can be extended with:

* TF-IDF feature extraction
* Multiple ML model comparison
* Confusion matrix
* Precision, Recall and F1-score
* Better text preprocessing
* Stop-word handling
* Character-level n-grams
* Web interface using Flask
* Streamlit interface
* Support for more languages
* Translation functionality using a translation API

---

## 👨‍💻 Author

**Aryan Dongre**

B.Tech — Artificial Intelligence & Data Science

---

## ⭐ If You Like This Project

If you found this project useful, consider giving the repository a ⭐ on GitHub.
