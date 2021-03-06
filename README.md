# Stylometry
Sample project for using stylometry to deanonymize Twitter account author.

## Instructions
#### 1. Install the dependencies and run Python:
```bash
    $ pip install tweepy numpy unidecode nltk scipy sklearn
    $ python3
```
In Python, import `nltk` and download Model `punkt`.
​    
```python
    >>> import nltk
    >>> nltk.download()
```

#### 2. Download files:
```bash
    $ git clone https://github.com/ViliamV/stylometry.git
    $ cd stylometry/
```

#### 3. Get Twitter API credentials

- Follow [these](https://themepacific.com/how-to-generate-api-key-consumer-token-access-key-for-twitter-oauth/994/) steps.
- Input credentials into `twitter-API.txt`

#### 4. Download tweets
- Create `accounts.txt` in main directory and put there account's names to download, one in each line. Put the unknown author's account last.
- Create directory `data` in main directory.
- Run `tweet-downloader.py` and wait. Due to Twitter API speed, it might take a while.
- Verify if `data` contains downloaded tweets.

#### 5. Run stylometry
- Edit `classification.py` and change value `UNKNOWN` (line 28) to unknown author's account.
```python
    UNKNOWN="example_account"
```
- Run `classification.py`.

## About classification
This code uses Bag of Words model for extracting features from the text. A great introduction for implementing this model can be found [here](https://www.kaggle.com/c/word2vec-nlp-tutorial/details/part-1-for-beginners-bag-of-words).

The code also uses Czech stopwords and Czech tokenizer, however, it is quite simple to change it.
