# Tweet Sentiment Analysis:

This is a sentiment analysis project based on a twitter dataset found on Kaggle here : https://www.kaggle.com/kazanova/sentiment140
Using Word2Vec and Logistic Regression all written in Python to create our models, and Flask to create the web application.

# To Run the project:
- To run the project we recommend you use a virtual environment. We use Pipenv to create the environment and to install the requirements, you can see the documentation here: https://pypi.org/project/pipenv/ <br/>
- To create a shell inside your project directory use:
&ensp;<p><code>pipenv shell</code></p> 
- To install the requirements using the <code>requirements.txt</code> file use:
&ensp;<p><code>pipenv install -r requirements.txt</code></p>

- Then you can simply run:
&ensp;<p><code>python app.py</code></p> 

# Data processing:

In this section we'll tackle what data proccessing is done on the dataset to produce the model used in the application you can find all the details in our <code>Data_processing.ipynb</code> notebook <br/>

- After importing the data we cleaned it by removing abreviations, stop words and ponctuation and we also lemmatized the tweets (using <code>nltk</code>)
- We took all the words present in the dataset and trained our Word2Vec model on them with window size 5 and vector size 300
- To use the model in the application we chose to use the save method on the model, this created three files one <code>.model</code> file and two <code>.npy</code> files
# Creating Logistic Regression model:
After competing our data processing we move on to training our Logistic Regression model and these were the steps taken: <br/>
- We represented each tweet by the sum of the vectors of each word in the tweet and we stored them into a matrix that represented our features.
- We split the dataset into training and testing sets with the training set containg 30% of the data.
- We trained our Logistic Regression Model using <code>scikit-learn</code> library and saved the model as a <code>pkl</code> file using the <code>pickle</code> library.
The results of the model on testing set were as follows: <br/>
![alt text](https://github.com/AbdelGhafour69/tweet_sentiment_analysis/blob/master/model_res.png?raw=true)
- When we wanted to use the model we simply called <code>pickle.load</code> to regain the model and analyze the user's input
