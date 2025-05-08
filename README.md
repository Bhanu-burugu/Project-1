pip install gensim nltk scikit-learn feedparser networkx matplotlib
import feedparser
import nltk
from nltk.tokenize import word_tokenize
from gensim.models import Word2Vec
from sklearn.metrics.pairwise import cosine_similarity
import networkx as nx
import matplotlib.pyplot as plt
import numpy as np
def fetch_news_data():
    url = "https://news.google.com/rss"
    news_feed = feedparser.parse(url)
    articles = [entry["title"] for entry in news_feed.entries]
    return articles

news_data = fetch_news_data()
print("Sample News Data:", news_data[:5])
