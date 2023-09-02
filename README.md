# Movie-Popularity-Prediction

### Introduction
For this project, we will be looking at the top 10,000 most popular movies from [TMDB](https://www.themoviedb.org/?language=en-AU). Our goal is to build a model that will predict the revenue of a movie based on key attributes including but not limited to budget, genres, & production company. You can access the Kaggle page for the raw data [here](https://www.kaggle.com/datasets/joebeachcapital/top-10000-most-popular-movies-from-imdb?resource=download). 

### Data Exploration
The raw data comes with, as expected, 10,000 observations. Each observation represents a movie with **14** attributes/columns. The 14 attributes are as follows:
1. ID: int64
2. Title: object
3. Release Date: object
4. **Genres**: object
5. Original Language: object
6. Vote Average: float64
7. Vote Count: int64
8. **Popularity**: float64
9. Overview: object
10. **Budget**: int64
11. Production Company: object
12. **Revenue**: int64
13. Runtime: int64
14. Tagline: object (~30% null)

### Data Preprocessing
As of right now, we have decided that there are multiple attributes that are irrelevant and will be dropped. This list is subject to change as we further curate our data and begin to build our model. These features are Tagline, Overview, Original Language, and Release Date. Title and ID won't be used for building the model or making predictions, but for the purpose of potentially identifying an observation, they will not be removed. The remaining 8 features (Genres, Vote Average, Vote Count, Popularity, Budget, Revenue, and Runtime) will more than likely help fit our model. The data will also need to be standardized as almost all features with a numerical measurement have different units. 

### First Model
