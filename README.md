# Movie Recommendation System
<hr>

Authors: Nevin Selby, Vijayram Patel

  <hr>

## Overview
This project implements a content-based movie recommendation system that suggests similar movies based on various movie attributes including cast, crew, keywords, genres, overview, and spoken languages. The system uses natural language processing techniques and cosine similarity to find movies that share similar characteristics.

## How It Works

### Data Processing Pipeline
1. **Data Loading and Merging**:
   - Loads two datasets: `movies.csv` (containing movie details) and `credits.csv` (containing cast and crew information)
   - Merges these datasets on the movie title

2. **Feature Selection**:
   - Selects relevant columns: title, movie_id, cast, crew, vote_average, spoken_languages, popularity, keywords, genres, and overview

3. **Data Cleaning**:
   - Removes rows with missing values
   - Converts JSON strings in columns like genres, keywords, cast, and crew into Python lists

4. **Feature Extraction**:
   - Extracts movie genres from the genres column
   - Extracts keywords from the keywords column
   - Extracts top 3 cast members from the cast column
   - Extracts director information from the crew column
   - Extracts spoken languages
   - Splits the overview text into words

5. **Text Processing**:
   - Removes spaces between multi-word features (e.g., "Science Fiction" becomes "ScienceFiction")
   - Converts all text to lowercase
   - Combines all features into a single "tags" column
   - Applies stemming to reduce words to their root form (e.g., "loving" becomes "love")

6. **Vector Representation**:
   - Uses CountVectorizer to convert the tags into a numerical representation
   - Limits to 5000 most frequent words and removes common English stop words

7. **Similarity Calculation**:
   - Computes cosine similarity between all movie vectors
   - Creates a similarity matrix for all movies in the dataset

### Recommendation Function
The `recommend(movie)` function:
1. Finds the index of the input movie
2. Retrieves the similarity scores from the similarity matrix for that movie
3. Sorts all movies by their similarity score (in descending order)
4. Returns the top 5 most similar movies (excluding the input movie itself)

## Technical Implementation Details
- **Libraries Used**: 
  - pandas: For data manipulation
  - numpy: For numerical operations
  - sklearn: For feature extraction and similarity calculation
  - ast: For parsing string representations of Python literals
  - nltk: For natural language processing

- **Key Techniques**:
  - **Content-Based Filtering**: Recommendations based on movie attributes rather than user ratings
  - **Bag of Words**: Converting text to numerical vectors using word counts
  - **Stemming**: Reducing words to their base form to improve matching
  - **Cosine Similarity**: Measuring similarity between movie vectors regardless of their magnitude

## How to Use

1. Make sure you have the required dependencies installed:
   ```
   pip install pandas numpy scikit-learn nltk
   ```

2. Place the `movies.csv` and `credits.csv` files in the same directory as the notebook

3. Run the Jupyter notebook sequentially

4. To get recommendations for a specific movie, use:
   ```python
   recommend('Movie Title')
   ```
   Replace 'Movie Title' with the exact title of a movie in the dataset.

## Example Recommendations

For "Avatar":
```python
recommend('Avatar')
```

For "Iron Man":
```python
recommend('Iron Man')
```

## Dataset Structure

The system requires two CSV files:

1. **movies.csv** - Contains movie details including:
   - title
   - movie_id
   - vote_average
   - spoken_languages (JSON format)
   - popularity
   - keywords (JSON format)
   - genres (JSON format)
   - overview

2. **credits.csv** - Contains:
   - title
   - cast (JSON format)
   - crew (JSON format)

## Limitations and Future Improvements

- The system only recommends movies based on content similarity, not user preferences
- The current implementation doesn't account for the popularity or rating of movies
- Adding a user interface would make the system more accessible
- Implementing collaborative filtering alongside content-based filtering could improve recommendations
- Considering the recency of movies could provide more relevant recommendations
