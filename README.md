# Movie Recommendation System

A machine learning-based movie recommendation system that provides personalized movie suggestions based on user preferences, viewing history, and movie characteristics.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Dataset](#dataset)
- [License](#license)

## Project Overview
This Movie Recommendation System aims to solve the problem of finding relevant movies in the vast sea of available content. The system analyzes user preferences and movie characteristics to suggest films that align with user interests, enhancing the movie discovery experience.

## Features
- **Collaborative Filtering:** Recommends movies based on similar users' preferences.
- **Content-Based Filtering:** Suggests movies similar to those a user has enjoyed previously based on movie attributes like genre, cast, and directors.
- **Hybrid Recommendation:** Combines both collaborative and content-based approaches for improved recommendation quality.
- **User-Friendly Interface:** Simple interface for interacting with the recommendation system.

## Technologies Used
- **Python** for core development and data processing.
- **Pandas & NumPy** for data manipulation.
- **Scikit-learn** for implementing machine learning algorithms.

## Installation
```sh
# Clone the repository
git clone https://github.com/vijayrampatel/MovieRecommendationSystem.git

# Change to project directory
cd MovieRecommendationSystem

# Install required dependencies
pip install -r requirements.txt
```

## Usage
Run the main application:
```sh
python main.py
```
Follow the on-screen instructions to:
- Input your movie preferences
- Rate movies you've watched
- Receive personalized recommendations

## Methodology
The recommendation system employs the following approach:
1. Data preprocessing and cleaning
2. Feature extraction from movie metadata
3. Implementation of recommendation algorithms
4. Evaluation of recommendation quality
5. Generation of personalized suggestions based on user input

## Dataset
This project utilizes movie datasets containing information such as:
- Movie titles, genres, and release dates
- User ratings and reviews
- Cast and crew information
- Plot descriptions

## Authors
Vijayram & Nevin

## License
This project is licensed under the MIT License - see the LICENSE file for details.

_Last Updated: March 2025_

