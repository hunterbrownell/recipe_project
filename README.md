# recipe_project
This is the third project in DSC80

## Introduction and Question Identification
We are using the "Recipes" dataset which contains data on many different recipes. Our analysis aims to answer the 
question, "Do recipes that take more time tend to have higher ratings?" The purpose of this is to help users decide
whether or not it would be worth it for them to spend more time making food, or just make something quick and easy. The
data contains 83,782 rows which each correlate to a single recipe. We will be using the "rating" column which contains
the average rating for each recipe. We will also use the "minutes" and "n_steps" columns which will tell us the time and number of steps each recipe takes.

### Data Cleaning
For our data cleaning process, we started by replacing all the ratings of 0 in the reviews data with np.nan's because a
rating of 0 just meant the recipe was not rated. This helped stop recipes from receiving a lower average rating than 
they should have due to 0's being factored in. Then we created a column with true/false depending on whether an entry 
was a rating or just an entry with a description. Then we grouped by the "recipe_id" column with aggfunc mean so that we
had the average rating for each recipe which we could merge to the recipes data. Then we grouped the recipes data by
"recipe_id" again but with aggfunc sum this time so we could get the total reviews for each recipe.
Finally, we merged the two dataframes into one big dataframe which contained the relevant information to use in our analysis.


>print(recipes_merged.head().to_markdown(index=False))
