# 🎵 Music Recommendation System using MFCC & Annoy

This project implements a **content-based music recommendation system** using audio signal processing and similarity search techniques.

It extracts audio features from songs, stores them in a database, and uses **Annoy (Approximate Nearest Neighbors)** to recommend similar songs.

---

## 🚀 Project Overview

The system analyzes songs using **MFCC (Mel-Frequency Cepstral Coefficients)** and recommends similar tracks based on audio similarity.

---

## 🛠️ Technologies Used

- Python
- Librosa (Audio Processing)
- NumPy
- MongoDB
- Annoy (Approximate Nearest Neighbors)
- Scikit-learn (Standardization)
- Mutagen (Metadata extraction)

---

## 📂 Project Files

```
│── retrieve_space.py          # Extract MFCC features & store in MongoDB
│── standardizing_mfccs.py     # Normalize MFCC features
│── making_annoy_model.py      # Build Annoy index
│── test_annoy.py              # Retrieve similar songs (recommendation)
│── ids.txt                    # Mapping of Annoy index to MongoDB IDs
│── mfcc_index.ann             # Saved Annoy index
```

---

## ⚙️ How It Works

---

### 🔹 Step 1: Audio Feature Extraction
- Reads `.mp3` files
- Extracts:
  - MFCC features using `librosa`
- Stores:
  - Song title
  - MFCC vector
- Saves data into **MongoDB**

📌 File: `retrieve_space.py`

---

### 🔹 Step 2: Feature Standardization
- Converts MFCCs into NumPy array
- Applies:
  - `StandardScaler`
- Updates standardized values back into MongoDB

📌 File: `standardizing_mfccs.py`

---

### 🔹 Step 3: Build Annoy Index
- Creates vector index using MFCC features
- Uses:
  - Angular distance
- Stores mapping between:
  - Annoy index
  - MongoDB document IDs

📌 File: `making_annoy_model.py`

---

### 🔹 Step 4: Music Recommendation
- Takes last listened songs
- Computes average MFCC
- Finds nearest neighbors using Annoy
- Retrieves similar songs from MongoDB

📌 File: `test_annoy.py`

---

## 🎯 Features

- Audio-based recommendation (no user ratings needed)
- Fast similarity search using Annoy
- Scalable for large music datasets
- Integration with MongoDB

---

## 🔧 How to Run

1. Start MongoDB server

2. Insert songs into database:
   ```bash
   python retrieve_space.py
   ```

3. Standardize features:
   ```bash
   python standardizing_mfccs.py
   ```

4. Build Annoy index:
   ```bash
   python making_annoy_model.py
   ```

5. Get recommendations:
   ```bash
   python test_annoy.py
   ```

---

## 📊 Learning Outcomes

- Audio feature extraction using MFCC
- Working with NoSQL databases (MongoDB)
- Feature scaling techniques
- Approximate nearest neighbor search
- Building recommendation systems
- Handling real-world data pipelines

---

## 📌 Future Improvements

- Add web interface (Flask / React)
- Use deep learning embeddings
- Improve recommendation accuracy
- Add playlist generation
- Deploy as an API

---

## 🙋‍♂️ Author

**Shahid Ullah**  
Data Scientist | Aspiring Data Analyst  

---

⭐ *This project demonstrates practical implementation of a scalable recommendation system using audio data.*
