# Amazon Product Rating Predictor 🌟

This repository contains a Deep Learning project that predicts customer ratings (1 to 5 stars) based on Amazon product reviews. It uses Natural Language Processing (NLP) techniques and a Bidirectional LSTM (BiLSTM) neural network to understand the sentiment and context of customer feedback.

## 📖 Project Overview

An e-commerce company wants to predict customer ratings using product information and customer reviews. This project solves that problem by treating it as a **Multi-Class Classification** task. The model reads raw review text, processes it, and accurately classifies the sentiment into a 1-5 star rating.

### Key Features
* **Data Preprocessing:** Cleans raw text by removing HTML tags and punctuation, and converts decimal ratings (e.g., 4.2) into integer classes.
* **Text Tokenization & Padding:** Converts English text into numerical sequences suitable for deep learning.
* **Deep Learning Model:** Utilizes a **BiLSTM** architecture built with TensorFlow/Keras to capture forward and backward context in sentences.
* **Real-world Testing:** Includes a pipeline to pass completely unseen, raw string reviews into the trained model to get instant rating predictions.

## 💾 Dataset

The project uses the **Amazon Sales Dataset** (~1,465 records) from Kaggle.
* **Dataset Link:** [Amazon Sales Dataset on Kaggle](https://www.kaggle.com/api/v1/datasets/download/karkavelrajaj/amazon-sales-dataset)

## 🛠️ Tech Stack

* **Language:** Python 3.x
* **Deep Learning Framework:** TensorFlow / Keras
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning Tools:** Scikit-learn (Train/Test Split)

## 🧠 Model Architecture

The neural network is built with the following layers:
1. **Embedding Layer:** Learns 64-dimensional vector representations for up to 10,000 words.
2. **Bidirectional LSTM:** A 64-unit BiLSTM layer that reads the text forwards and backwards to understand deeper contextual meaning.
3. **GlobalAveragePooling1D:** Condenses the sequential data into a fixed-length vector.
4. **Dense & Dropout Layers:** Fully connected layers with ReLU activation and 30% dropout to prevent overfitting.
5. **Output Layer:** A Dense layer with 5 nodes and `softmax` activation to output probabilities for 1, 2, 3, 4, or 5 stars.

## 📊 Example Output on Unseen Data

```text
Review: 'Absolutely amazing product! The quality is fantastic and it works exactly as described. Worth every penny.'
Predicted Rating: 5 Stars

Review: 'Terrible experience. The item broke after two days and the customer service was awful.'
Predicted Rating: 1 Stars

Review: 'It is okay. Not the best quality, but it gets the job done for the price.'
Predicted Rating: 3 Stars
