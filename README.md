# Movie-Popularity-Prediction

### Introduction
For this project, we will be looking at the top 10,000 most popular movies from [TMDB](https://www.themoviedb.org/?language=en-AU). Our goal is to build a model that will predict the popularity of a movie based on key attributes including but not limited to budget, genres, & revenue. You can access the Kaggle page for the raw data [here](https://www.kaggle.com/datasets/joebeachcapital/top-10000-most-popular-movies-from-imdb?resource=download). 
### Data Exploration
The raw data comes with, as expected, 10,000 observations. Each observation represents a movie with **14** attributes/columns. The 14 attributes are as follows:
1. ID: Integer
2. Title: String
3. Release Date: String
4. **Genres**: Array
5. Original Language: String
6. Vote Average: Decimal
7. Vote Count: Integer
8. **Popularity**: Decimal
9. Overview: String
10. **Budget**: Integer
11. Production Company: Array
12. **Revenue**: Integer
13. Runtime: Integer
14. Tagline: String
### Data Preprocessing
