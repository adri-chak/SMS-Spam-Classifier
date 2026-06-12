# 📱 SMS Spam Classifier 

A machine learning web application that classifies SMS messages as **Spam** or **Ham (Not Spam)** using the Multinomial Naive Bayes algorithm — deployed live with Flask on Render.

🔗 **Live Demo:** [https://sms-spam-classifier-wwn7.onrender.com](https://sms-spam-classifier-wwn7.onrender.com)

---

## 📌 Project Overview

This project builds a text classification model trained on a real-world SMS dataset. The model learns patterns from thousands of labeled messages and predicts whether a new message is spam or legitimate. The trained model is then served through a minimal Flask web app with a clean dark-themed UI.

---

## 🗂️ Dataset

- **Source:** SMS Spam Collection Dataset (UCI Machine Learning Repository / Kaggle)
- **Size:** 5,574 SMS messages
- **Labels:** `ham` (legitimate) and `spam`
- **Format:** Tab-separated — label and message text

---

## 🧠 ML Pipeline

### 1. Data Loading & Exploration
- Loaded the dataset using **Pandas**
- Explored class distribution (majority ham, minority spam)
- Checked for null values and duplicates

### 2. Data Preprocessing
- Removed duplicate rows
- Encoded labels: `ham → 0`, `spam → 1`
- Cleaned text (lowercasing, punctuation removal)

### 3. Feature Extraction
- Used **TF-IDF Vectorizer** (`TfidfVectorizer` from scikit-learn)
- Converts raw text messages into numerical feature vectors

### 4. Train/Test Split
- Split data: **80% training / 20% testing**
- Used `train_test_split` from scikit-learn

### 5. Model Training
- Algorithm: **Multinomial Naive Bayes** (`MultinomialNB`)
- Chosen for its effectiveness with text/count-based data
- Compared against other Naive Bayes algorithms (Gaussian and Bernoulli)
- Multinomial NB selected as the best performer

### 6. Model Evaluation
- **Accuracy:** -97.1%
- Metrics used: Accuracy Score, Confusion Matrix
- Evaluated on unseen test data

### 7. Model Saving
- Saved trained model and vectorizer using **Pickle** (`model.pkl`, `vectorizer.pkl`)
- Loaded in the Flask app for real-time predictions

---

## 🌐 Web Application

Built with **Flask** and deployed on **Render (free tier)**.

### How it works
1. User pastes a message into the text box
2. Clicks **PREDICT**
3. The message is vectorized using the saved TF-IDF vectorizer
4. The Naive Bayes model predicts spam or ham
5. Result is displayed instantly on the page

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3 |
| ML Library | scikit-learn |
| Data Handling | Pandas, NumPy |
| Text Features | TF-IDF Vectorizer |
| Algorithm | Multinomial Naive Bayes |
| Web Framework | Flask |
| Frontend | HTML, CSS |
| Deployment | Render (free) |
| Version Control | GitHub |

---

## 📁 Project Structure

```
SMS-Spam-Classifier/
├── app.py                 # Flask application
├── model.pkl               # Trained Naive Bayes model
├── vectorizer.pkl          # Fitted TF-IDF vectorizer
├── requirements.txt        # Python dependencies
├── Procfile                # Render start command
└── templates/
    └── index.html          # Frontend UI
```

---

## ⚙️ Run Locally

```bash
# Clone the repo
git clone https://github.com/adri-chak/SMS-Spam-Classifier.git
cd SMS-Spam-Classifier

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
```

Then open `http://localhost:5000` in your browser.

---

## 📦 Requirements

```
flask
scikit-learn
numpy
```

---

## 🚀 Deployment

Deployed for free on [Render](https://render.com):
- Auto-deploys on every GitHub push
- Free tier spins down after 15 min of inactivity (first load may take ~30 sec)

---

## 📊 Results

- ✅ Model Accuracy: **~97.1%**
- ✅ Successfully classifies unseen spam messages
- ✅ Live and accessible via public URL

---

## 🙋 Author

**Adrija Chakraborty**
GitHub: [@adri-chak](https://github.com/adri-chak)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
