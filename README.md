# 🎬 Movie Recommender System

A modern movie recommendation system built with FastAPI backend and Streamlit frontend. The system uses TF-IDF vectorization and genre-based filtering to provide personalized movie recommendations.

## ✨ Features

- **Smart Search**: Autocomplete search with real-time movie suggestions
- **Hybrid Recommendations**: Combines TF-IDF content-based filtering with genre matching
- **Rich Movie Details**: Displays posters, backdrops, release dates, genres, and overviews
- **Modern UI**: Clean, responsive interface with grid-based movie displays
- **TMDB Integration**: Fetches live movie data and images from The Movie Database API

## 🛠️ Tech Stack

- **Backend**: FastAPI, Python
- **Frontend**: Streamlit
- **ML**: TF-IDF Vectorization, Scikit-learn
- **Data**: TMDB API, Pandas, NumPy
- **Deployment**: Heroku-ready with Procfile

## 📦 Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd Movie_Recommended_System
```

2. Create a virtual environment:
```bash
python -m venv .venv
.venv\Scripts\activate  # Windows
# or
source .venv/bin/activate  # Linux/Mac
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create a `.env` file with your TMDB API key:
```
TMDB_API_KEY=your_api_key_here
```

Get your free API key from [The Movie Database](https://www.themoviedb.org/settings/api)

## 🚀 Usage

### Run Backend (FastAPI)
```bash
uvicorn main:app --reload
```
API will be available at `http://127.0.0.1:8000`

### Run Frontend (Streamlit)
```bash
streamlit run app.py
```
App will open at `http://localhost:8501`

## 📁 Project Structure

```
Movie_Recommended_System/
├── app.py                 # Streamlit frontend
├── main.py               # FastAPI backend
├── movies.ipynb          # Data preprocessing notebook
├── requirements.txt      # Python dependencies
├── Procfile             # Heroku deployment configuration
├── data/
│   └── movies_metadata.csv
└── pickled models (generated):
    ├── df.pkl
    ├── indices.pkl
    ├── tfidf_matrix.pkl
    └── tfidf.pkl
```

## 🔧 API Endpoints

- `GET /` - Health check
- `GET /movie/autocomplete?query={query}` - Search autocomplete
- `GET /movie/search?query={query}&tfidf_top_n={n}&genre_limit={n}` - Get recommendations
- `GET /movie/{tmdb_id}` - Get movie details

## 🌐 Deployment

### Heroku Deployment

1. Create a Heroku app:
```bash
heroku create your-app-name
```

2. Set environment variables:
```bash
heroku config:set TMDB_API_KEY=your_api_key_here
```

3. Deploy:
```bash
git push heroku main
```

4. Scale the web dyno:
```bash
heroku ps:scale web=1
```

## 📊 How It Works

1. **Data Processing**: Movie metadata is processed and vectorized using TF-IDF
2. **Search**: User searches for a movie via autocomplete
3. **Recommendations**: System finds similar movies using:
   - Content-based filtering (TF-IDF cosine similarity)
   - Genre-based matching
4. **Display**: Results are fetched from TMDB API with posters and details

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [The Movie Database (TMDB)](https://www.themoviedb.org/) for the API and data
- Dataset from Kaggle/TMDB movies metadata
