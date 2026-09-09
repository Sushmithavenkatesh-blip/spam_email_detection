#  Spam Email Detection using Machine Learning

A web-based **Spam Email Detection** application built with **React and Vite**. The project uses Natural Language Processing (NLP) and Machine Learning techniques to classify email messages as **Spam** or **Ham (Legitimate)**.

The application trains and evaluates two machine learning models directly in the browser:

* **Naive Bayes**
* **Logistic Regression**

It also provides dataset analysis, model performance metrics, vocabulary insights, email statistics, and downloadable reports.

---

##  Features

*  Detect whether an email is **Spam or Ham**
*  Supports **Naive Bayes** and **Logistic Regression**
*  Text preprocessing and tokenization
*  TF-IDF feature extraction
*  Model performance and evaluation metrics
*  Email text analysis
*  Vocabulary and important-term analysis
*  Confusion matrix visualization
*  Email dataset statistics
*  Generate and download a PDF report
*  Runs machine learning directly in the browser
*  Responsive React-based interface

---

##  Machine Learning Workflow

The project follows a complete machine learning pipeline:

```text
Email Dataset
     ↓
Text Preprocessing
     ↓
Tokenization
     ↓
Train/Test Split
     ↓
Vocabulary Creation
     ↓
TF-IDF Feature Extraction
     ↓
Model Training
     ↓
Prediction
     ↓
Model Evaluation
```

### 1. Text Preprocessing

The input email is cleaned before being used for prediction.

The preprocessing includes:

* Removing HTML tags
* Removing URLs
* Converting text to lowercase
* Removing punctuation and special characters
* Normalizing whitespace
* Tokenizing words

### 2. Train/Test Split

The dataset is divided into:

* **80% Training Data**
* **20% Testing Data**

A deterministic shuffle with a fixed seed is used so that the split is reproducible.

### 3. TF-IDF

The application converts email text into numerical features using **TF-IDF (Term Frequency-Inverse Document Frequency)**.

The vocabulary is built only from the training data to avoid test-data leakage.

### 4. Naive Bayes

The project implements a **Multinomial Naive Bayes** classifier with Laplace smoothing.

The model calculates the probability that an email belongs to:

* Ham
* Spam

### 5. Logistic Regression

The project also implements **Logistic Regression from scratch** using:

* Gradient descent
* L2 regularization
* Sigmoid activation

The model produces a spam probability between 0 and 1.

---

## Model Evaluation

Both models are evaluated using the same held-out test dataset.

The application provides metrics such as:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

This makes it possible to compare the performance of Naive Bayes and Logistic Regression.

---

##  Application Pages

### Dashboard

Provides an overview of the email dataset and machine learning results.

### Spam Detector

Enter an email message and select a model to classify it as:

```text
SPAM
```

or

```text
HAM
```

The result also includes the predicted spam probability and text statistics.

### Email Analysis

Provides detailed analysis of the emails in the dataset, including text-related statistics and vocabulary information.

### Model Performance

Displays the performance of the machine learning models and allows comparison between Naive Bayes and Logistic Regression.

---

##  Project Structure

```text
spam-email-detection/
│
├── public/
│   └── data/
│       └── spam_emails.csv
│
├── src/
│   ├── components/
│   │   ├── ChartCard.jsx
│   │   ├── ConfusionMatrix.jsx
│   │   ├── EmailDetails.jsx
│   │   ├── EmailInput.jsx
│   │   ├── EmailTable.jsx
│   │   ├── Header.jsx
│   │   ├── ModelMetrics.jsx
│   │   ├── PredictionResult.jsx
│   │   ├── ReportButton.jsx
│   │   ├── Sidebar.jsx
│   │   ├── StatCard.jsx
│   │   └── VocabularyChart.jsx
│   │
│   ├── ml/
│   │   ├── logisticRegression.js
│   │   ├── modelTraining.js
│   │   ├── naiveBayes.js
│   │   ├── preprocessing.js
│   │   └── tfidf.js
│   │
│   ├── pages/
│   │   ├── Dashboard.jsx
│   │   ├── EmailAnalysis.jsx
│   │   ├── ModelPerformance.jsx
│   │   └── SpamDetector.jsx
│   │
│   ├── services/
│   │   └── dataset.js
│   │
│   ├── utils/
│   │   ├── insights.js
│   │   ├── metrics.js
│   │   ├── reportGenerator.js
│   │   ├── textAnalysis.js
│   │   └── vocabulary.js
│   │
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
│
├── index.html
├── package.json
├── postcss.config.js
├── tailwind.config.js
├── vite.config.js
└── README.md
```

---

## Technologies Used

### Frontend

* React
* Vite
* Tailwind CSS
* JavaScript

### Machine Learning

* Naive Bayes
* Logistic Regression
* TF-IDF
* NLP/Text preprocessing
* Gradient Descent

### Data & Visualization

* CSV dataset
* Charts and statistical analysis
* Confusion Matrix

### Reporting

* jsPDF
* html2canvas

---

##  Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/spam-email-detection.git
```

### 2. Navigate to the project

```bash
cd spam-email-detection
```

### 3. Install dependencies

```bash
npm install
```

### 4. Start the development server

```bash
npm run dev
```

The application will be available at the local URL displayed by Vite, usually:

```text
http://localhost:5173
```

---

##  Using the Spam Detector

1. Start the application.
2. Open the **Spam Detector** page.
3. Select a machine learning model.
4. Enter or paste an email message.
5. Click **Detect Spam**.
6. View the prediction and spam probability.
7. Analyze the email statistics and matched vocabulary terms.
8. Generate a PDF report if required.

---

##  Dataset

The project uses:

```text
public/data/spam_emails.csv
```

The expected columns are:

```text
label
message
```

Example:

```csv
label,message
ham,Hey are we meeting today?
spam,Congratulations! You have won a prize!
```

Supported labels are normalized internally, including:

```text
spam / 1 / true
ham / legitimate / 0 / false
```

---

##  Privacy

The machine learning pipeline runs in the browser. Email text entered into the detector is processed locally by the application and is not required to be sent to an external machine-learning API.

---

##  PDF Reports

The application can generate a downloadable report containing information such as:

* Dataset summary
* Model metrics
* Confusion matrix
* Current prediction
* Text statistics
* Spam probability
* Model insights
* Visualization

The report does not need to include the raw email message.

---

##  Project Objectives

The main objectives of this project are:

1. To build a practical spam email classification system.
2. To demonstrate NLP-based text preprocessing.
3. To convert text into numerical features using TF-IDF.
4. To implement and compare Naive Bayes and Logistic Regression.
5. To evaluate machine learning models using classification metrics.
6. To provide an interactive user-friendly web interface.
7. To demonstrate how machine learning can be integrated into a frontend application.

---

##  Real-World Applications

Spam detection systems are commonly useful for:

* Email services
* Business communication platforms
* Customer-support systems
* Messaging applications
* Marketing platforms
* Cybersecurity systems

For example, an email containing suspicious promotional language, unusual links, or patterns frequently found in spam messages can be analyzed by the trained model and classified as spam.

---

##  Future Improvements

Possible improvements include:

* Add more machine learning algorithms
* Use larger and more diverse datasets
* Add deep-learning models
* Improve feature engineering
* Add multilingual spam detection
* Add real-time email service integration
* Improve model tuning and cross-validation
* Add user authentication
* Deploy the application online
* Add an API/backend for centralized model training

---

##  Project Type

**Machine Learning + NLP + React Web Application**

This project is suitable for:

* Academic projects
* Machine Learning demonstrations
* NLP projects
* Final-year/student projects
* Portfolio projects
* GitHub ML showcases

---

##  Conclusion

The **Spam Email Detection** project demonstrates how Natural Language Processing and Machine Learning can be combined with a modern React interface to create an interactive email classification system.

By using **TF-IDF, Naive Bayes, and Logistic Regression**, the application transforms email text into meaningful numerical features and predicts whether the message is likely to be **Spam or Ham**.
# spam_email_detection
#  Spam Email Detection using Machine Learning  A web-based **Spam Email Detection** application built with **React and Vite**. The project uses Natural Language Processing (NLP) and Machine Learning techniques to classify email messages as **Spam** or **Ham (Legitimate)**.  
