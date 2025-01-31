# 🔗 Hyperlink Analysis & Content-Based Recommendation System  

## 📜 Overview  
This project is divided into two main components:  
1. **Hyperlink Analysis** using **PageRank and HITS algorithms**.  
2. **Content-Based Recommendation System** using **K-Nearest Neighbors (KNN)** for song recommendations based on Spotify metadata.  

📌 **Datasets Used**:  
- **Hyperlink Analysis**: Simulated Web graph structure.  
- **Content-Based Recommendation**:  
  - `Spotify_Metadata.csv` – Song metadata.  
  - `Spotify_Numeric.csv` – Song features (numeric vectors).  
  - `Spotify_Users.txt` – User playlists.  

📌 **Programming Language**: `Python 3`  
📌 **Libraries Used**: `NumPy`, `pandas`, `networkx`, `scikit-learn`, `math`, `csv`  

## 🔗 1️⃣ Hyperlink Analysis  
### **1.1 PageRank Algorithm**  
- **Input**: Web graph structure: A → {B, C} B → {C} C → {A}
- **Computation**:  
- **Damping Factor (α) = 0.15**  
- **Three Iterations**  
- PageRank scores computed **before & after normalization** at each step.  

### **1.2 HITS Algorithm (Hubs & Authorities)**  
- **Input**: Web graph structure (including Page D).  
- **Computation**
- **Three Iterations**  
- Hub & Authority scores computed **before & after normalization** at each step.  

📌 **Output**:  
- PageRank & HITS scores printed at each iteration.  

## 🎵 2️⃣ Content-Based Recommendation System  
### **2.1 K-Nearest Neighbors (KNN) for Song Similarity**  
- Function: `knn(item, Data, K)`  
- **Input**:  
  - `item` – Feature vector of a song.  
  - `Data` – Song feature matrix (`Spotify_Numeric.csv`).  
  - `K` – Number of nearest neighbors.  
- **Computation**:  
  - Compute **Cosine Similarity** between `item` and all songs in `Data`.  
  - Return **K most similar songs** with metadata (`Spotify_Metadata.csv`).  

📌 **Demonstration**:  
- Run `knn()` for the given song vector: item = [0.8, 0.1, 0.7, 0.0, 0.5, 0.1, 0.5, 0.2, 0.0, 1.0, 0.1, 0.2, 0.7]
- Print **top 10 similar songs**.  

### **2.2 User-Based Song Recommendations**  
- Function: `recommend(userID, Data, K)`  
- **Input**:  
  - `userID` – User index (0-based).  
  - `Data` – Song feature matrix.  
  - `K` – Number of recommendations.  
- **Computation**:  
  - Compute **user profile** as the **centroid vector** of liked songs.  
  - Call `knn()` to get **top K song recommendations**.  
  - **Exclude previously listened songs** from final recommendations.  

📌 **Demonstration**:  
- Run `recommend()` for:  
- **User 3** (4th row in `Spotify_Users.txt`)  
- **User 19** (20th row in `Spotify_Users.txt`)  
- Print **top 20 recommendations** for each user.  
