# Predictive Analysis
# File functions
## Modeling 
### combined_workflow.ipynb
This is the combined workflow for web scraping, performing sentiment analysis, and saving this all to a .csv file and the MongoDB database. When collecting data, we ran this file every day. This has not been automated.
### logistic_regression.ipynb
This performs and evaluates logistic regression on the stock data based on the sentiment analysis values obtained from web-scraped current news articles. 
### lstm.ipynb
This performs long short-term memory modeling with neural networks to predict stock market changes—increase or decrease—based on historical financial data and sentiment analysis on current news articles.
### autoregressive_model.ipynb
This performs simple autoregressive prediction on the stock data based on the sentiment analysis data and prediction values from the previous two days. It is important to note that the model performance was significantly affected by data sparsity, as it is highly dependent on past data to make future predictions.

## Supplementals to modeling pipeline
### Converting_dates.ipynb
For modeling and data manipulation, sometimes it is better to use the datetime object for efficiency instead of the date as a string. This file allows for these conversions, if necessary.
### Plots.ipynb
This file produces plots of the distribution of stocks across the sectors. It also allows us to make plots of sentiment vs. price of stock for a chosen stock

## Data collection
### yahoo_finance_news_scraper.ipynb
This file builds a web scraper that—given an article title and URL from the Yahoo Finance API—accesses, scrapes, and stores the corresponding article text as a list of strings
### yahoo_finance_news_updating.ipynb
Based on the web scraper implemented in yahoo_finance_news_scraper.ipynb, this file stores the scraped article text in a pandas dataframe and uploads the data into our MongoDB database for storage and future reference.
### Stock_data.csv
This is a local copy of the stock data used to train models, so we don’t have to pull from the database every time.

## Getting Started

Follow these steps to set up the project on your local machine.

### Prerequisites

Before you begin, ensure that you have the following installed:

- **Python**: Download and install the latest version of Python from [python.org](https://www.python.org/downloads/).
- **pip**: Python's package installer, which typically comes pre-installed with Python. You can verify by running `pip --version`.

### Installation

#### 1. Clone the repository

First, clone the repository to your local machine using the following command:

```
$ git clone https://github.com/cc459/Predictive-Analysis.git
```

#### 2. Navigate into the project directory
```
$ cd Predictive-Analysis
```

#### 3. Create a virtual environment
For Mac/Linux:
```
$ python3 -m venv venv
```

For Windows:
```
$ python -m venv venv
```

#### 4. Activate the virtual environment
For Mac/Linux:
```
$ source venv/bin/activate
```

For Windows:
```
$ venv\Scripts\activate
```

If the activation is successful, you should see `(venv)` at the start of your terminal prompt.

#### 5. Install the required packages
With the virtual environment active, install all necessary dependencies:
```
$ pip install -r requirements.txt
```

#### Notes
Once you're done working, you can deactivate the virtual environment by running
```
$ deactivate
```

If you add new packages during development, please update the `requirements.txt` file:
```
$ pip freeze > requirements.txt
```
This ensures that anyone else working on the project will have access to the updated dependencies.

*If you are facing issues running the code, specifically ModuleNotFoundErrors, simply download the module indicated that isn't installed using the command "pip install <module_name>" in terminal. 

