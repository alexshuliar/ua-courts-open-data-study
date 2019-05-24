# UA courts open data analysis

## Intro

This repo contains jupyter notebooks for data analysis project on Ukrainian courts open data. It has grown up from pieces of code I wrote to practice my python data analysis skills (along with some bash scripting and SQL) and get fluency in working with some "dirty" real world data instead of nice and clean datasets that usually can be found in tutorials, at relevant courses or kaggle. Original data can be found at [Ukrainian open data portal](https://data.gov.ua) or at [official website of Ukrainian courts](https://court.gov.ua/opendata). The open data includes .CSV files for each year from 2006 containing an information about court documents for that period including links for original text. Also, to extract information about companies that are parties of a particular court trial I've used open data on UA legal entities registry (stored in .XML format).

The jupyter notebooks in the repo have a code for data extraction, data analysis and applying some basic machine learning to predict outcomes of court judgements.

Before running a code provided in the notebooks, make sure you download open data for particular years from the links above. Move them into a directory you'll going to work in and provide subdirectories for each year of datasets you've downloaded. Some scripts take a while to run and results in high CPU memory usage. For this reason you may consider to use [Google Colab environment](https://colab.research.google.com). In particluar, it has been used by me in part 5 notebook. 

## Overview of notebooks:

### Part 1. Getting the data

* loading original dataset from open data portal
* filtering out relevant categories of court cases
* first look into our data
* bash and python scripts to download documents text data and some aggregated information using web API of Court on the palm web service


### Part 2. Merging the data and regex matching

* using regular expressions to extract parties (companies) from texts
* cleaning extracted parties from redundant information
* iteratively merging extracted data with the legal entities open data to match companies that are subject to court trials
* accessing time information and extracting durations for trials

### Part 3. Joining all the data

* merging data extracted from different sources into single dataset
* getting features for our future model
* quick analysis with new features

### Part 4. ML and data analysis

* loading all our datasets and building baseline model to predict outcomes of court trials
* exploring our dataset through basic EDA while trying out different features
* computing new aggregated features for our model
* computing feature importances
* extra data analysis to catch some patterns outside the scope of model training objective

### Part 5. NLP and Neural Networks

In this section I'm using Google Colab environment to prepare text of court documents and fit a convolutional neural network with embedding layer at the top.

### EXTRAS

* code to extract parties (companies) from documents using EDRPOU code and apply the same model to predict outcomes of trials
* scripts to (1) extract judges declarations using web API at https://declarations.com.ua and (2) convert json data to nice and clean pandas dataframe (part 1 & part 2 respectively)
* scripts to extract civil cases documents using same procedure described in previous notebooks
* data analysis on civil cases
* comparison of private entrepreneurs (FOP) and companies winning rates in courts using frequenist and bayseian statistical approaches and also methods from so-called "hacker statistics" (permutations and bootstraping)

