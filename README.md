Project Overview:
This project processes movie metadata from the TMDB 5000 dataset and uses content-based filtering techniques to recommend movies. By combining features like genres, keywords, cast, crew, and overview, it creates a similarity matrix using TF-based vectorization.

Features:

Data preprocessing and merging of TMDB datasets.
Feature extraction from:
Genres,
Keywords,
Cast,
Crew (Director),

Overview:

Text normalization, stemming, and tokenization.
Similarity calculation using cosine similarity.
Movie recommendation based on title input.
Final export of processed data and model with Pickle.

Dataset:

The project uses the TMDB 5000 Movie Dataset, which includes:
tmdb_5000_movies.csv,
tmdb_5000_credits.csv.

Tech Stack:

Python,
Pandas, NumPy,
NLTK for NLP tasks,
Scikit-learn for vectorization and similarity,
Pickle for saving model/data,
Google Colab, PyCharm.

Workflow:

1. Data Loading & Merging-
movies and credits datasets are merged on the title column.
Selected columns: movie_id, title, overview, genres, keywords, cast, and crew.

2. Data Cleaning-
Removed nulls and duplicates.
Converted stringified lists to Python lists using ast.literal_eval.

3. Feature Engineering-
Extracted top 3 actors from cast.
Extracted only the Director from the crew.
Cleaned and joined all textual features into a single tags column.

4. Text Processing-
Lowercased text.
Removed whitespace.
Applied stemming using PorterStemmer.

5. Vectorization-
Used CountVectorizer (Bag-of-Words) with max_features=5000 and stopwords removed.

6. Similarity Calculation-
Used cosine similarity on the vector matrix.
Implemented a recommend() function that:
Finds index of the selected movie,
Retrieves top 5 similar movies based on similarity scores.

7. Model Export-
Saved:
movies.pkl: dataframe with movie IDs and tags.
similarity.pkl: cosine similarity matrix.
movie_dict.pkl: movie info dictionary.

Files Generated:
movies.pkl – Preprocessed dataframe.
similarity.pkl – Cosine similarity matrix.
movie_dict.pkl – Dictionary of movies for web apps.

The project includes a modern frontend using Streamlit that allows users to:

Select a movie title from a dropdown,
Click "Recommend",
View 5 recommended movies with posters.
