# Solid-Spoon:Recipe Price Per Serving

Prepared and presented by: Crissy Bruce


## Business Problem

Spoonacular has hired me to build a model to use for customers who want to estimate the price per serving based on ingredients.  There is a demand for this estimate as users often have a budget and need a way to gauge the cost of a meal.  The system asks users to input the ingredients they have on hand or plan to use and returns an estimated price per serving.   

***
Questions to consider:
* What are the business's pain points related to this project?
* How did you pick the data analysis question(s) that you did?
* Why are these questions important from a business perspective?
***

## Data

* The recipe data was sourced from https://spoonacular.com/food-api via an API call.
* Dataset included recipe name, ingredients, pricePerServing and more for 1000 different recipes.
* pricePerServing is in cents and range for all recipes is 13.23($0.13)-2149.55($21.50)
* Feature of the dataset are a list of ingredients for all of the recipes
* The mean price per serving is 293.59977 cents($2.94), and the standard deviation is 204.26($2.04) 

![graph1]https://github.com/crissymae/solid-spoon/blob/template-mvp/Images/PredErrorHist.png


## Methods

* Since my x values were text data, I processed the text using both vectorization and TFIDF.

* Linear Regression was used as a baseline
    *TFIDF Baseline Test RMSE: 1.10783E+15
     
* Final model was Support Vector Regression
    *Final TFIDF Test RMSE:  209.97
    
![graph2](PredErrorHist)

## Results

The final model is not a perfect fit based on the RMSE (209.97), but is very close to the standard deviation of the original dataset (204.26 cents).


Here is an example of how to embed images from your sub-folder:

### Visual 1
![graph1](PricePerServingHist)

## Future Steps and Limitations

* Obtain more recipes as there are some outliers within the original data that could skew the modeling work or remove outliers.
* Create more models using Neural Networks as it contains set of adaptive weights as well as the ability to group the ingredients into different classes  

## For More Information

Please review our full analysis in [our Jupyter Notebook](./dsc-phase1-project-template.ipynb) or our [presentation](./DS_Project_Presentation.pdf).

For any additional questions, please contact **name & email, name & email**

## Repository Structure

Describe the structure of your repository and its contents, for example:

```
├── README.md                           <- The top-level README for reviewers of this project
├── dsc-phase1-project-template.ipynb   <- Narrative documentation of analysis in Jupyter notebook
├── DS_Project_Presentation.pdf         <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```
