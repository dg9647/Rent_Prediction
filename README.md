# MACHINEKNIGHT HACKATHON - KEYBOARD WACKERS
## Prediction of House Rents in regions specified.

This is the github repository created for the End to End Machine Learning project done by: Divyansh Gupta, Tanmay Shukla and Khushi Suri.


The project involves a web application in order to predict the house rents depending on specified parameters.<br>
The following cities are included:<br>
1. Mumbai
2. Delhi
3. Kolkata
4. Bangalore
5. Hyderabad 
6. Chennai
7. Ahemdabad 
8. Pune

This project has the goal to predict house rent prices for various different cities.<br>
This project uses a Machine Learning model in the backend to predict the rent prices in various cities.<br>
This project uses a XGBoost Regressor model {currently best suitable}.<br>
The models were evaluated on the basis of two metrics:<br>
<ol>
<li>R<sup>2</sup>score</li>
<li>Mean Absolute Error</li>
</ol>

The models tried out in this project are:<br>
<ol>
<li>Linear Regression</li>
<li>Decision Tree Regression</li>
<li>Random Forest Regression</li>
<li>Adaboost Regression</li>
<li>Gradient Boost Regression</li>
<li>XGBoost Regression</li>
</ol>

Running the project on local machine: <br>
Step 1 - Clone the project <br>
```
Download the zip file and save it locally.
```
Step 2 - Virtual environment <br>
```
pip install virtualenv
virualenv {YOUR_ENVIRONMENT_NAME}
{YOUR_ENVIRONMENT_NAME}\Scripts\activate

# or for linux/mac 
virtualenv {YOUR_ENVIRONMENT_NAME}
source {YOUR_ENV_NAME}/bin/activate
```

Step 3 - Install all the dependencies <br>
```
pip install -r requirements.txt 
# for linux/mac 
pip3 install -r requirements.txt
```
Step 4 - Execution <br>
```
python main.py
# for linux/mac
python3 main.py
```

Directory structure
```
Home - Objects - Encoders(Contains all the label encoders and ordinal encoders for preprocessing)
               - Models (Contains the best selected model for all cities)
     - Results - Contains the results of all the models to aid in model selection
     - static - All the files needed to render flask app
     - templates - All the templates used in the flask app
     - _All_Cities_Cleaned.csv (data source)
     - .gitignore - Files to be ignored while uploading code on github
     - eda.ipynb - Python notebook used while doing Exploratory data analysis 
     - main.py - Python file containing the code for making the flask app
     - models.ipynb - Python notebook used while creating the models 
     - preprocessing.ipynb - Python notebook used while data preprocessing
     - README.md - Readme file for github repository 
     - requirements.txt - For installing the dependencies 
     - sql_files - The files containing insert queries for SQL (need to run these queries to create initial database)
     - wsgi.py - Entry point for deployment 
     - combine.py - The python script which retrains the model every month 
```

App structure<br>

<br>
Home page

* Contains all the links to navigate through the page at the top
* Contains the information about all cities, where the headings are linked to the page for each city if the user is interested 
* Contains basic overall analysis for the entire data at the bottom 
* Contains contact details in the bottom 
<br>

<br>
Pages for a particular city

* Contains all the links to navigate through the page at the top
* Contains a detailed analysis for the houses in that city to help the user in making an informed decision 
* Contains a predict button at the bottom which takes the user to the predict page 
<br>

<br>
Predict Page

* Takes the input from the user
* Submit button to display the results
<br>

<br>
Results Page

* Displays the result for the particular set of inputs


<br>
Contribute Page 

* The user can provide information and contribute to the database if the user feels that the predictions are inaccurate or the inputs do not exist in the database 


<br>
Thanks Page 

* This page is displayed when the data contributed by the user is inserted in the database

This project is deployed on a production server by using gunicorn and nginx then connected to a domain via namecheap.<br>
The machine learning models on the server are retrained on the first of every month by using the combine.py script<br>
