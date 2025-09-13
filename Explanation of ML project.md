What your project does



Your project is about the Iris Flower Dataset.

There are three types of iris flowers: Setosa, Versicolor, Virginica.



The model predicts which flower it is by looking at:



Sepal length



Sepal width



Petal length



Petal width



So basically → you give numbers about the flower → the model tells you the species (type of flower).



📂 Files in your project

1\. constants.py



Just a file with settings (like shortcuts).



Example:



Where the dataset is saved (iris.csv).



Where the trained model is saved (iris\_model.joblib).



How much data should be used for testing (33%).



What is the column we want to predict (species).



👉 Think of this as a note paper where all important values are written in one place.



2\. inference.py



This is the main file that makes predictions.



It has 2 main functions:



🔹 load\_model()



Opens the saved ML model (iris\_model.joblib) and loads it.



Uses Streamlit caching → means don’t load the model again and again, just keep it ready in memory.



Uses logging (explained below).



👉 Think of this like switching on your calculator once and then reusing it.



🔹 get\_preds\_and\_probs()



Takes 4 inputs (the flower measurements).



Puts them inside a table (DataFrame) so the model understands.



Asks the model:



predict() → gives the species name.



predict\_proba() → gives the percentage chances for each species.



Returns both answers: (prediction, probabilities).



👉 Example: If you enter (5.9, 3.0, 4.2, 1.5), the model might say:



Prediction: Versicolor



Probabilities: Setosa 0.01, Versicolor 0.85, Virginica 0.14



3\. pyproject.toml



This is like a grocery list 📋.

It lists what tools and libraries your project needs:



scikit-learn → the machine learning library



pandas → handles tables/data



numpy → handles numbers



joblib → saving/loading models



loguru → logging system



streamlit → makes a web app



👉 When someone else runs your project, this file helps them install everything needed.



4\. .gitignore



This file tells GitHub which files to ignore (like trash files, cache, or temporary files).



📝 What are Logs? (very simple)



When a program runs, it can write messages about what is happening.

Example messages:



“Model loaded successfully”



“Prediction done: Setosa”



“Error: file not found”



These messages are called logs.

They are very helpful for debugging (finding mistakes) and tracking (knowing what happened).



👉 Without logs, if your program crashes, you won’t know why. Logs act like a diary of your program’s actions.



🔹 What is Loguru?



Normally, Python logging is a bit complicated.

Loguru is a special library that makes logging easy and pretty.



Instead of just printing things with print(), you can write:



from loguru import logger



logger.info("Model loaded successfully")

logger.error("Something went wrong")





logger.info → normal message



logger.error → error message



Loguru automatically shows:



time (when it happened)



level (info, warning, error)



message (what happened)



👉 Think of Loguru as a smart notebook that writes everything clearly while your program runs.



🪄 In short



You have a program that can guess flower type from 4 numbers.



It uses machine learning model (trained once, then saved).



constants.py = important notes (paths \& settings).



inference.py = actual code for making predictions.



logs = messages about what the program is doing.



loguru = the tool that writes those messages nicely.



###### pyproject.toml = shopping list of required libraries.

