# Machine Learning Fundamentals - Data Science Retreat 2023 Course
Repository for the July 2023 edition of the Machine Learning Fundamentals course, held quarterly at Berlin's bootcamp, Data Science Retreat.

## Contents
This course introduces basic ML algorithms that are foundational for more advanced applications. The course is developed over three days. Despite having a flexible agenda that depends on the specific class needs, I usually try to cover the following topics:

* Day 1: Basic problems of Machine Learning
  * Introduction to Supervised Learning
  * Evaluating supervised learning model results
  * Bias and Variance Tradeoff
  * Linear Regression
  * Regularization
  * Optimization Methods
  * Metrics for Classification

* Day 2: A focus on the most important ML Algorithms for classification
  * Logistic Regression
  * Decision Tree
  * Random Forest
  * Gradient Boosting

* Day 3: Unsupervised Learning and additional topics
  * Support Vector Machines
  * Elements of Unsupervised Learning
  * Principal Component Analysis
  * Cluster Analysis: K-Means
  * Additional topics depending on the class.

The third day's agenda can vary quite a lot depending on the class. Often, I complete some topics from the previous days and/or answer specific questions from students that we didn't have the time to delve into earlier. 

The course is meant to provide clear intuitions about the most important concepts in ML. For this reason, we won't focus on applications, but more on the underlying ideas. However, I have prepared a few notebooks for experimentation with the ML models, especially to get a better idea of how hyperparameters affect the results. Please note that these notebooks are currently (January 2023) still a work in progress, and I will continue to expand on them during 2023. 

## Teaching Style
We will primarily use a whiteboard (either a physical one, or an iPad) to discuss concepts and sketch notes on the fly. There are no pre-prepared slides for this course. The idea is to stimulate discussion on the course topics and involve every student as much as possible. 

We will present theoretical concepts in an accessible, light-math manner, striving to put everything in a broader context. Practical sessions will occur during the course and students will be invited to complete some code snippets and experiment with the provided code. 

For the practical sessions, we'll utilize MLFlow (https://mlflow.org/), an important and popular tool used for MLOps, which will be handy for checking the experiment results (*experiments tracking*).

## Set-up for Practical Sessions

First, be sure to clone this repository:

`git clone https://github.com/andandandand/DSR_ML_Fundamentals_2023.git`

We highly recommend using [VSCode](https://code.visualstudio.com/download) as the Integrated Development Environment to explore this codebase. The notebooks use files such as `Training.py`, `Preprocessing.py`, and `BinaryClasificationTraining.py` that we can explore easily with this tool. 

Please use [micromamba](https://mamba.readthedocs.io/en/latest/micromamba.html) to set up the virtual environment. Open a terminal and follow the installation instructions [here](https://mamba.readthedocs.io/en/latest/installation.html). 

On MacOS, `brew install micromamba` is an easy way to set it up.  

Move to the folder where the repository has been cloned:

```cd DSR_ML_Fundamentals_2023```

and create a virtual environment with the name `ml_env` using the following command:

```micromamba create -y -p ./ml_env -c conda-forge python=3.8```

Then activate the environment:

```micromamba activate ./ml_env```

We will use the `requirements.txt` file to install the needed dependencies: 

```micromamba install -y -c conda-forge --file requirements.txt``` 

### Downloading the Data

For the applications, we use the NY taxi trip data. Go to https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page and manually download "Green Taxi Trip Records (PARQUET)" under `data/input/data_raw` for the month of January 2022 [(link)](https://d37ci6vzurychx.cloudfront.net/trip-data/green_tripdata_2022-01.parquet). These are quite large datasets, so follow the steps below to reduce the data size:

- `cd data/input/`
- `python get_final_data.py` 

To access the MLFlow UI, run the following command from the repository folder `mlflow ui --backend-store-uri sqlite:///mlflow.db` and open on a web browser the generated IP (e.g., http://127.0.0.1:5000/)

## External Resources
A very good resource that we will refer to during the class is the following repository: https://github.com/dvgodoy/ML_Fundamentals. It contains interactive widgets to explore the properties of ML models. The author is a DSR alumnus and former DSR teacher.
