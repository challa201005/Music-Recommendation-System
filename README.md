# 🎵 Spotify Song Recommendation System

This project fetches audio features of tracks from a Spotify playlist and builds a **content-based + hybrid music recommender system** using `Spotipy`, `Pandas`, `Scikit-learn`, and `cosine similarity`.

---

## 📌 Features

- Authenticates via Spotify's **Client Credentials Flow**
- Extracts audio features like danceability, energy, tempo, etc., from a **Spotify playlist**
- Normalizes and processes track data for modeling
- Generates:
  - 🎧 **Content-Based Recommendations** (using cosine similarity of audio features)
  - 🔀 **Hybrid Recommendations** (content + weighted popularity by release date)

---

## 🛠️ Installation

1. **Clone the repository** (if applicable):
   ```bash
   git clone https://github.com/challa201005/Music-Recommendation-System.git
   cd spotify-recommendation-System
   ```

2. **Install required packages**:
   ```bash
   pip install requests spotipy pandas scikit-learn
   ```

---

## 🔐 Spotify API Setup

1. Create an app at [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/)
2. Get your **Client ID** and **Client Secret**
3. Replace the placeholders in the script:
   ```python
   CLIENT_ID = 'Your_id'
   CLIENT_SECRET = 'Your_secret'
   ```

---

## ▶️ Usage

### 1. **Get access token**
```python
# Automatically generates and prints access token using client credentials
```

### 2. **Fetch Playlist Data**
```python
playlist_id = '1r8V9g47ADGZD6dwxtkXun'  # Spotify Top 100
music_df = get_trending_playlist_data(playlist_id, access_token)
```

### 3. **Generate Recommendations**
#### Content-Based:
```python
content_based_recommendations("Track Name")
```
#### Hybrid:
```python
hybrid_recommendations("Track Name", num_recommendations=5)
```

---

## 📊 Sample Output

```text
Hybrid recommended songs for 'Oka Maaru':
     Track Name        Artists       Album Name      Release Date    Popularity
     Nenu Nuvvantu    Naresh Iyer       Orange        2010-10-25         62.0
     Oh Priya Priya   Adnan Sami         Ishq         2012-02-03         54.0
     ...
```

---

## 📂 Project Structure

```
├── data_fetch.py         # Spotify API authentication and playlist fetching
├── recommender.py        # Feature scaling, similarity calculations, and hybrid recommendation logic
├── README.md             # You're here!
```

---

## 📌 Notes

- Recommendations are based on audio features and adjusted using **popularity weighted by release recency**
- Missing or invalid track names will be gracefully handled


