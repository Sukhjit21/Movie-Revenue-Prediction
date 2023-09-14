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
6. **Vote Average**: float64
7. **Vote Count**: int64
8. **Popularity**: float64
9. Overview: object
10. **Budget**: int64
11. Production Company: object
12. **Revenue**: int64
13. **Runtime**: int64
14. Tagline: object (~30% null)

### Data Preprocessing
We have decided that there are multiple attributes that are irrelevant and will be dropped. This list is subject to change as we further curate our data and begin to build our model. These features are Tagline, Overview, Original Language, and Release Date. Title and ID won't be used for building the model or making predictions, but for the purpose of potentially identifying an observation, they will not be removed. The remaining 8 features (Genres, Vote Average, Vote Count, Popularity, Budget, Revenue, and Runtime) will more than likely help fit our model. The data will also need to be standardized as almost all features with a numerical measurement have different units. One hot encoding was used to make it easier to manipulate data, specifically regarding genres and production companies before creating the neural network. This handles the categorical data to make it compatible with the neural network, and to avoid bias as integer labels can mistakenly create a relationship between the numerical values in the dataset.

### One Hot Encoding

### Linear Regression

### Neural Network
In our second model, we used an Artificial Neural Network. This model is more appropriate as a weakness of the linear regression model was how many different variables existed, and the neural network is a remedy to that as one hot encoding helped interpret the different variables.

## Figures
### Heatmap 
![heatmap](https://github.com/Sukhjit21/Movie-Revenue-Prediction/assets/85320290/cd0b3934-53d4-4a4d-9b74-66594eb92bf8)
### Scatterplots
#### Revenue vs Budget
![rev_budget](https://github.com/Sukhjit21/Movie-Revenue-Prediction/assets/85320290/8dae725a-4342-4c64-a092-ad692655013a)
#### Revenue vs Average Vote 
![rev_voteavg](https://github.com/Sukhjit21/Movie-Revenue-Prediction/assets/85320290/a73ed91a-9a86-4656-9f23-c574db752ee9)
#### Revenue vs Vote Count
![rev_votecount](https://github.com/Sukhjit21/Movie-Revenue-Prediction/assets/85320290/00fb46ea-0300-459d-bd25-fea6bf1c013f)
#### Revenue vs Runtime
![rev_runtime](https://github.com/Sukhjit21/Movie-Revenue-Prediction/assets/85320290/9e99e8ed-8686-4ab1-9018-543acba36d8d)
#### Revenue vs Popularity
![rev_pop](https://github.com/Sukhjit21/Movie-Revenue-Prediction/assets/85320290/d8d5ffe7-e195-4f9b-88ad-024b77fbf1f7)

### Model MSE
![model_mse](https://github.com/Sukhjit21/Movie-Revenue-Prediction/assets/85320290/a0d6cfc7-18e0-4aef-a795-0cff8c3a7ad3)

## Discussion
### Model 1
Overall, the first model was extremely inaccurate, especially when dealing with data it had not been presented with before. Our testing MSE was several orders of magnitude higher than our training MSE. Normally, such a large gap between training and testing error would cause us to say our model is overfitted, however, due to the extremely high training error, we can conclude that our model significantly underfits the data and is not complex enough to satisfactorily explain the variance in our data set. This was not entirely unexpected, as our data has a large degree of variance, but we were curious to see how sufficiently a linear regression model would describe our dataset. We plan to further explore modeling the data using neural networks in order to find a more appropriately fitting model.

### Model 2
Our second model was also extremely inaccurate, albeit orders of magnitude less so than when we presented our first model with data it had not seen before. Our accuracy was extremely low (peaking around 0.5%) and our MSE was 977043185467392.00. Similarly to our first model, based on our huge MSE, we can conclude that our model still underfit the data and was not complex enough to satisfactorily explain the variance in our data set. However, we did see that using a neural network was significantly more effective than our initial linear regression model, especially when presented with data it had not seen before, as the testing MSE for the neural network was over 10^26 times smaller than the testing MSE for the linear regression model. 

Despite our poor results, the results of both models are somewhat plausible: it’s almost impossible for a studio to guarantee that a movie will succeed. If a neural network was able to successfully predict the ingredients of a blockbuster, then there would be no need for writers, directors or producers. It’s difficult for any machine learning model to accurately replace human creativity, and perhaps harder still to accurately predict what will resonate with audiences, and we ran up against that roadblock when making our model.

## Results

#### Model 1
For our first model, the training MSE was 675697998806435.38 and the testing MSE was 3768517409013513169214405319052180911554560.00.
#### Model 2
Our second model had a training MSE of 977043185467392.00 and the testing MSE was 6849642834690048.00.

## Conclusion
Overall, the project proved to be tough for all six of us. At times we definitely struggled with building a functional model, but working hands on with no strict limits turned out to be a great learning experience. Our MSE for both models was significantly higher than we hoped, but was not entirely unexpected, given that the data didn’t show many strong correlations: building an enhanced model for our data might have taken more time then we had for this class and was possibly outside of the scope for what we learned. With hindsight, we realized that we should have tried to reduce our loss by using hyperparameter tuning. This would’ve given us the best possible parameters, while saving us time from the hours we all spent building and training different models with different parameters. Additionally, we potentially could have had better results if we had limited how many independent variables we were considering when it came to predicting the success of a movie: eliminating more columns during preprocessing and as a result building more streamlined models could have led to more accurate predictions.

Ultimately we were unable to discover the secret to making a successful movie, but diving into such a huge data set and working together to build multiple models from the ground up — beginning with preprocessing and then on to the models themselves — was a fantastic learning experience that left us more experienced and with an idea of what to do better next time.

## Collaborators
#### Rajveer Grewal
Helped with the direction of the project, first model implementation, scheduled meetings, and helped work on the ReadMe write-up.
#### Garrett Hilyer
Helped distinguish relevant features and possible labels for prediction, data preprocessing, brainstormed 2nd model, and wrote/formatted the ReadMe write-up. 
#### Olive Maunupau
Helped brainstorm possible models to run and implemented our 2nd model to predict revenue using a neural network.
#### Ishan Moundi
Helped with preprocessing, helped with implementation of second model, was involved with direction of the project, helped work on the ReadMe write-up.
#### Siddhartha Sahasrabuddhe
Helped with direction of project, planned out preprocessing, helped with second model implementation, wrote/edited the ReadMe write-up.
#### Sukhjit Singh
Helped implement both the first and second models. Helped with the preprocessing of the second model. Polished the ReadMe write-up.

#### Link to Jupyter Notebook
https://colab.research.google.com/drive/10KS-Uo2jpXwVNH4VSZtWGR0PHUbF888x?usp=sharing
