# Movie-Revenue-Prediction

### Introduction
In this project, an in-depth analysis is conducted on a comprehensive dataset comprising the top 10,000 movies from [TMDB](https://www.themoviedb.org/?language=en-AU), focusing on exploring the correlations between Genre and Budget and using those to predict Popularity. You can access the Kaggle page for the raw data [here](https://www.kaggle.com/datasets/joebeachcapital/top-10000-most-popular-movies-from-imdb?resource=download). By dissecting the intricate interplay between these factors, this study seeks to uncover patterns that contribute to a film's success. Through this analysis, valuable insights could be gained into the dynamics of the film industry, aiding filmmakers and producers in making informed decisions to maximize both artistic and commercial achievements. This study's findings have the potential to reshape the film industry landscape by providing guidance to filmmakers, producers, and investors. The shocking results will unveil a plot twist unlike any other: the secret to making a popular movie!

## Methods

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
We have decided that there are multiple attributes that are irrelevant and will be dropped. This list is subject to change as we further curate our data and begin to build our model. These features are Tagline, Overview, Original Language, and Release Date. Title and ID won't be used for building the model or making predictions, but for the purpose of potentially identifying an observation, they will not be removed. The remaining 8 features (Genres, Vote Average, Vote Count, Popularity, Budget, Revenue, and Runtime) will more than likely help fit our model. The data will also need to be standardized as almost all features with a numerical measurement have different units. One hot encoding was used to make it easier to manipulate data, specifically regarding genres and production companies before creating the neural network. This handles the categorical data to make it compatible with the neural network, and to avoid bias as integer labels can mistakenly create a relationship between the numerical values in the dataset.

### One Hot Encoding

### Linear Regression

### Neural Network
In our second model, we used an Artificial Neural Network. This model is more appropriate as a weakness of the linear regression model was how many different variables existed, and the neural network is a remedy to that as one hot encoding helped interpret the different variables.

## Figures

## Discussion

### Model 1
Overall, the first model was extremely inaccurate, especially when dealing with data it had not been presented with before. Our testing MSE was several orders of magnitude higher than our training MSE. Normally, such a large gap between training and testing error would cause us to say our model is overfitted, however, due to the extremely high training error, we can conclude that our model significantly underfits the data and is not complex enough to satisfactorily explain the variance in our data set. This was not entirely unexpected, as our data has a large degree of variance, but we were curious to see how sufficiently a linear regression model would describe our dataset. We plan to further explore modeling the data using neural networks in order to find a more appropriately fitting model.

### Model 2
Our second model was also extremely inaccurate, albeit orders of magnitude less so than when we presented our first model with data it had not seen before. Our accuracy was extremely low (peaking around 0.5%) and our MSE was MSE HERE. Similarly to our first model, based on our huge MSE, we can conclude that our model still underfit the data and was not complex enough to satisfactorily explain the variance in our data set. However, we did see that using a neural network was significantly more effective than our initial linear regression model, with the MSE being X times smaller than our linear regression model’s. 

Despite our poor results, the results of both models are somewhat plausible: it’s almost impossible for a studio to guarantee that a movie will succeed. If a neural network was able to successfully predict the ingredients of a blockbuster, then there would be no need for writers, directors or producers. It’s difficult for any machine learning model to accurately replace human creativity, and perhaps harder still to accurately predict what will resonate with audiences, and we ran up against that roadblock when making our model.

## Results

#### Model 1
For our first model, the training MSE was 675697998806435.38 and the testing MSE was 3768517409013513169214405319052180911554560.00.
#### Model 2
Our second model had a training MSE of 28342867143426048.00 and the testing MSE

## Conclusion

#### Link to Jupyter Notebook
https://colab.research.google.com/drive/10KS-Uo2jpXwVNH4VSZtWGR0PHUbF888x?usp=sharing
