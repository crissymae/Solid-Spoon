# Solid-Spoon:Recipe Price Per Serving Estimator

Prepared and presented by: Crissy Bruce


## Business Problem

Spoonacular has hired me to build a model to use for customers who want to estimate the price per serving based on ingredients.  There is a demand for this estimate as users often have a budget and need a way to gauge the cost of a recipe for meal planning purposes.  The system asks users to input the ingredients they have in mind and returns an estimated price per serving.   


## Data

* The recipe data was sourced from https://spoonacular.com/food-api via an API call, which was highly involved process including the  
  following steps:
    * Requested API key from Spoonacular website
    * Learned about all the requests that are available from the website and trying several before finally learning about the endpoint that
      will return everything needed
    * Viewed the data via json file to confirm data points
    * Created a function that would pull down multiple requests at a time 
    * Converted the data to a dataframe 
    * Converted the dataframe to a .csv
* Dataset included recipe name, ingredients, price per serving and more for 1000 different recipes.
* pricePerServing is in cents and range of price per serving for all recipes is 13.23($0.13)-2149.55($21.50)
* Feature set is a list of ingredients for all of the recipes
* The mean price per serving is 293.59977 cents($2.94), and the standard deviation is 204.26($2.04) 

![graph1](https://github.com/crissymae/solid-spoon/blob/template-mvp/PricePerServingHist.png)


## Methods

* Since my x values were text data, I wanted to understand how the text data was distributed for the ingredients/

![graph2](https://github.com/crissymae/solid-spoon/blob/template-mvp/Word%20Cloud.png)

![graph3](https://github.com/crissymae/solid-spoon/blob/template-mvp/DistributionFrequencyBarGraph.png)

    I was not surprised to see what was in the top 20 as these are very common ingredients.

* I then processed the text using both vectorization and TFIDF. 

* Linear Regression was used as a baseline model
    *TFIDF Baseline Test RMSE: 1.10783E+15
     
* Final model was Support Vector Regression using best parameters from Grid Search
    *Final TFIDF Test RMSE:  209.97
    
![graph4](https://github.com/crissymae/solid-spoon/blob/template-mvp/PredErrorHist.png)

## Results

The final model is not a perfect fit based on the Test MAE (126.33), but is lower than standard deviation of the original dataset (204.26 cents).


## Future Steps

* Obtain more recipes.
* Remove outliers within the original data that could skew the modeling work.
* Try other models, such as Neural Networks as it contains set of adaptive weights as well as the ability to group the ingredients into 
  different classes.
* Check for other features that may be beneficial at predicting price per serving.

## For More Information

Please review the full analysis in https://github.com/crissymae/solid-spoon or our [presentation](https://github.com/crissymae/solid-spoon/blob/template-mvp/Presentation_Final.pdf).

For any additional questions, please contact Crissy Bruce at crissybruce@gmail.com.


