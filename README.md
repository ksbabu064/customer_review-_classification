# customer_review-_classification
A browser-based customer review sentiment classification application built with React and Vite. It uses TF-IDF text vectorization and a custom JavaScript Logistic Regression model to classify reviews as Positive or Negative, with dataset exploration, real-time predictions, performance metrics, and visualization.
Customer Review Classification

A browser-based machine learning application that classifies customer reviews as Positive or Negative using TF-IDF text vectorization and Logistic Regression.

The complete machine learning pipeline is implemented in JavaScript and runs directly in the browser without requiring a backend or external machine learning library.

Overview

Customer Review Classification is a React-based web application designed to demonstrate text classification using traditional machine learning techniques.

The application loads a labeled review dataset, preprocesses the text, converts reviews into TF-IDF feature vectors, trains a Logistic Regression model, evaluates the model on a test dataset, and allows users to classify new reviews interactively.

Features
Dashboard with dataset statistics
Positive and negative sentiment distribution
Average review length visualization
Dataset browser with sentiment filtering
Pagination for dataset records
Real-time review classification
Positive probability calculation
Logistic Regression model implemented from scratch
TF-IDF text feature extraction
Train/test dataset splitting
Accuracy calculation
Precision, recall, and F1-score
Confusion matrix
Classification report
Client-side machine learning with no backend
Netlify deployment configuration
Machine Learning Workflow

The application follows this workflow:

Load the review dataset from CSV.
Parse the CSV using Papa Parse.
Convert review text to lowercase.
Remove punctuation and non-alphanumeric characters.
Tokenize the review text.
Remove common stopwords.
Calculate document frequency for each term.
Build a TF-IDF vocabulary.
Convert reviews into normalized TF-IDF vectors.
Split the dataset into training and testing sets.
Train a binary Logistic Regression model.
Generate predictions for the test dataset.
Calculate classification metrics.
Use the trained model to classify new reviews entered by the user.
Dataset

The application contains 1,200 labeled reviews.

Sentiment	Number of Reviews
Positive	572
Negative	628
Total	1,200

The dataset is stored in:

src/data/reviews.csv

Each record contains:

review_text,sentiment

where the sentiment is either Positive or Negative.

Machine Learning Model
TF-IDF

The application uses Term Frequency-Inverse Document Frequency to convert text into numerical feature vectors.

The implementation includes:

Tokenization
Stopword removal
Document frequency calculation
IDF calculation
Term frequency calculation
L2 normalization
Maximum vocabulary size of 2,000 features
Minimum document frequency of 2
Logistic Regression

The classifier is implemented directly in JavaScript without using an external machine learning library.

The model uses:

Binary classification
Sigmoid activation
Gradient descent
Learning rate: 0.5
Epochs: 60
L2 regularization: 0.001
Dataset Split

The dataset is divided into:

80% training data
20% testing data

A fixed random seed of 42 is used to make the train/test split reproducible.

Application Pages
Dashboard

Displays an overview of the dataset, including:

Total reviews
Positive reviews
Negative reviews
Test accuracy
Sentiment distribution
Average review length
Dataset

Allows users to browse the review dataset and filter reviews by:

All
Positive
Negative

The page displays 10 reviews per page.

Review Classification

Users can enter a new review and classify it using the trained model.

The application returns:

Positive or Negative prediction
Positive probability

Sample positive and negative reviews are also provided for testing.

Performance

Displays the model evaluation results, including:

Accuracy
Positive precision
Positive recall
Positive F1-score
Confusion matrix
Classification report
Macro average
Weighted average
Project Structure
review-classification-app/
|
├── public/
│   ├── icons.svg
│   └── favicon.svg
|
├── src/
│   ├── assets/
│   │   ├── hero.png
│   │   └── vite.svg
│   │
│   ├── components/
│   │   ├── Layout.jsx
│   │   ├── Loading.jsx
│   │   └── StatCard.jsx
│   │
│   ├── data/
│   │   └── reviews.csv
│   │
│   ├── ml/
│   │   ├── logisticRegression.js
│   │   ├── preprocess.js
│   │   └── useModel.jsx
│   │
│   ├── pages/
│   │   ├── Dashboard.jsx
│   │   ├── Dataset.jsx
│   │   ├── Performance.jsx
│   │   └── ReviewClassification.jsx
│   │
│   ├── App.jsx
│   ├── index.css
│   └── main.jsx
│
├── .gitignore
├── .oxlintrc.json
├── index.html
├── netlify.toml
├── package.json
├── package-lock.json
├── postcss.config.js
├── tailwind.config.js
├── vite.config.js
└── README.md
Technologies Used
React
Vite
JavaScript
Tailwind CSS
React Router
Recharts
Papa Parse
Logistic Regression
TF-IDF
Netlify
Installation

Clone the repository:

git clone https://github.com/your-username/review-classification-app.git

Move into the project directory:

cd review-classification-app

Install dependencies:

npm install
Run the Application

Start the development server:

npm run dev

The application will be available at the local development URL provided by Vite.

Production Build

Create a production build:

npm run build

Preview the production build:

npm run preview
Linting

Run Oxlint:

npm run lint
Deployment

The project includes a netlify.toml configuration file.

Build command:

npm run build

Publish directory:

dist

The Netlify configuration also includes a redirect rule so that the React application works correctly with client-side routing.

Advantages
No backend server required
Machine learning runs completely in the browser
Easy to understand ML implementation
Interactive prediction interface
Built-in model evaluation
Dataset visualization
Lightweight architecture
Easy to deploy as a static web application
Limitations
The model is trained every time the application starts.
Logistic Regression is implemented specifically for binary classification.
The dataset is relatively small for a production sentiment analysis system.
The model uses simple tokenization and stopword removal.
The application does not use advanced language models or contextual embeddings.
Predictions depend on vocabulary learned from the training dataset.
Future Improvements

Possible improvements include:

Add stemming or lemmatization
Support n-gram features
Add Naive Bayes and other classifiers
Compare multiple machine learning models
Add ROC-AUC and precision-recall curves
Allow users to upload their own CSV dataset
Add model configuration controls
Store trained models for faster startup
Add multilingual sentiment classification
Add transformer-based sentiment analysis
Improve preprocessing for contractions and negation
Add automated unit and integration tests
License

This project is intended for educational and demonstration purposes.

Author

Developed as a machine learning and web application project demonstrating text classification with React and JavaScript.
