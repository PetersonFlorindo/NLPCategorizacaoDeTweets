# Tweet Relevance Classifier for NLP

This repository contains a text classification model developed to filter relevant texts from web scraping outputs.

The project was created as part of my MBA thesis in Data Science and Analytics, with the goal of identifying which collected tweets were actually useful for sentiment analysis, market studies and other NLP tasks related to movie audience reactions.

## Objective

Train a text classification model capable of labeling scraped texts as either **relevant** or **not relevant**, reducing noise in datasets collected from social media and improving the quality of downstream NLP analysis.

## Context

In the original research, tweets were collected from social media during the pre-release window of movies. Since web scraping can return noisy, duplicated or contextually irrelevant content, this classifier was created to help filter the dataset before applying sentiment analysis and other text-based methods.

Although designed for movie-related tweets, the model can be adapted to other domains involving scraped text, such as brands, products, events or public opinion monitoring.

## Model

The notebook trains a text classification model using **spaCy TextCat**.

The classification labels are:

```text
RELEVANTE
NAO_RELEVANTE
```

## Features

* Loads labeled text data from Excel
* Cleans and preprocesses tweet text
* Splits the dataset into training and test sets
* Trains a spaCy text classification model
* Evaluates performance with a classification report
* Plots training loss by epoch
* Saves the trained model locally
* Classifies new CSV or Excel files
* Exports classified texts to CSV

## Input File

The training file should contain at least the following columns:

```text
TWEET
RELEVANTE
```

Where:

* `TWEET` contains the text to be classified
* `RELEVANTE` indicates whether the text is relevant, using `1` for relevant and `0` for not relevant

## Requirements

Install the main dependencies:

```bash
pip install spacy pandas scikit-learn matplotlib openpyxl
```

## Usage

Open the notebook:

```bash
jupyter notebook treino_textcat.ipynb
```

Run the cells in order to:

1. Load the labeled dataset
2. Preprocess the texts
3. Train the spaCy TextCat model
4. Evaluate the classifier
5. Save the trained model
6. Classify new scraped text files

## Output

After training, the model is saved locally as:

```text
modelo_textcat
```

When classifying a new file, the script generates a CSV output with an additional column:

```text
CLASSIFICACAO
```

Where:

* `1` means relevant
* `0` means not relevant

## Applications

* Filtering scraped tweets
* Reducing noise in NLP datasets
* Preparing data for sentiment analysis
* Market research
* Public opinion analysis
* Social media monitoring
* Academic research involving textual data

## Authorship

This project was developed by Peterson Oliveira Florindo.

The use, study, adaptation and sharing of this code are allowed, as long as proper credit is given to the author. This project is made available for educational, academic and research purposes.
