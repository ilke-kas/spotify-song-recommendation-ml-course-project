# 🎵 Spotify Song Recommendation System

This repository contains a basic machine learning-based music recommendation system developed as a course project for the **Machine Learning Course at Bilkent University**. It uses Spotify audio features to generate personalized recommendations using KNN, PCA, and Autoencoder-based models.

---

### 📌 Overview

Given the audio features of a Spotify track, the system recommends similar songs using:

- K-Nearest Neighbors (KNN)
- PCA + KNN (for dimensionality reduction)
- Neural Network + KNN (using Autoencoders)

A Flask-based REST API serves as the backend for easy integration.

---

### 🧠 Functionalities

#### 🎧 Feature Extraction

Each track is represented using the following 9 Spotify audio features:

- acousticness  
- danceability  
- energy  
- instrumentalness  
- liveness  
- loudness  
- speechiness  
- tempo  
- valence  

#### ✅ KNN Recommendation (`knn.py`)

- Uses Euclidean distance
- Finds the k-nearest songs in the dataset
- Can return only track IDs or full feature vectors

#### ✅ PCA + KNN (`pca_knn.py`)

- Reduces dimensionality via Principal Component Analysis (PCA)
- Applies KNN in the reduced space
- Configurable number of principal components (`n`)

#### ✅ Neural Network + KNN (`NN.py`)

- Trains an Autoencoder to learn compressed embeddings
- Uses the encoder's output for similarity search via KNN
- Pretrained model (`model.pth`) and encoded data (`foo.csv`) are reused for inference

#### ⚖️ Evaluation (`evaluations.py`)

- Compares recommendations with Spotify's official API
- Metrics used:
  - Mean Absolute Error (MAE)
  - Root Mean Square Error (RMSE)
  - Cosine Similarity
- Evaluates for multiple values of `k` (1–10)

#### 🌐 REST API (`server.py`)

- `PUT /knn` — standard KNN recommendation
- `PUT /pcaknn` — PCA-enhanced KNN
- `PUT /nn` — Neural Network encoded KNN
- `POST /eval` — evaluates model performance against Spotify's recommendations

---

### 🧪 Technologies Used

- Python
- PyTorch
- scikit-learn
- Flask
- Spotify Web API
- NumPy & Pandas

---

### 👨‍🎓 Course Info

This project was developed as part of the **Machine Learning Course** at **Bilkent University**.

