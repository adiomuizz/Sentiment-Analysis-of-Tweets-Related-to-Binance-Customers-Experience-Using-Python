# 📊 Binance Twitter Sentiment Analysis

This project performs **sentiment analysis** on tweets related to **Binance's customer experience** using Python and natural language processing (NLP) techniques. The goal is to understand the public’s perception by classifying tweets as **positive**, **negative**, or **neutral**.

🔗 **Read the full article on Medium**:  
[Sentiment Analysis of Tweets Related to Binance Customers Experience Using Python](https://medium.com/@muizzadio/sentiment-analysis-of-tweets-related-to-binance-customers-experience-using-python-517953c5c95)

---

## 📌 Project Objective

To analyze 2,000 tweets containing the keyword **"Binance"**, using sentiment analysis methods that help measure customer satisfaction and public opinion. This analysis can assist Binance or any data-driven business in detecting sentiment trends and improving decision-making.

---

## ⚙️ Tools & Libraries Used

| Library | Purpose |
|--------|--------|
| `tweepy` | Access Twitter API for scraping tweets |
| `textblob` | Perform sentiment polarity analysis |
| `matplotlib.pyplot` | Data visualization (Pie chart, WordCloud) |
| `pandas`, `numpy` | Data manipulation and structuring |
| `re` | Regular expression for text cleaning |
| `PIL` | Image handling (WordCloud rendering) |
| `nltk.sentiment.vader` | Sentiment scoring |
| `sklearn.feature_extraction` | Text vectorization |
| `better_profanity` | Profanity detection & removal |
| `wordcloud` | Visualizing the most common words |

---

## 🧪 Project Workflow

### 1. Twitter API Authentication

Authenticate using Twitter Developer credentials:
```python
auth = tweepy.OAuthHandler(API_key, API_secret)
auth.set_access_token(access_Token, access_TokenSecret)
api = tweepy.API(auth)
````

### 2. Data Collection
Collect tweets by keyword input:
```python
keyword = input("Enter keyword: ")
noOfTweet = int(input("Enter number of tweets: "))
tweets = tweepy.Cursor(api.search_tweets, q=keyword).items(noOfTweet)
```
### 3. Data Cleaning
To ensure the accuracy and reliability of the sentiment analysis, the dataset underwent several cleaning steps:
**Stop Words Removal**  
  Common stop words (e.g., *the*, *is*, *in*) that do not contribute meaningful sentiment were removed using NLTK's predefined stop word list.

- **Removal of URLs, Hashtags, and Mentions**  
  All links, hashtags (e.g., `#Binance`), and mentions (e.g., `@user`) were stripped from the tweets to maintain text clarity.

- **Profanity Filtering**  
  Profane and inappropriate words were filtered out to maintain professionalism and ethical standards.

- **Non-Alphanumeric Characters**  
  All non-alphanumeric characters (punctuation, emojis, special symbols) were removed or normalized to retain only clean text suitable for analysis.


### 4. Sentiment Analysis
Use TextBlob to compute tweet polarity:

```python
TextBlob(tweet).sentiment.polarity
```
- Positive if polarity > 0
- Negative if polarity < 0
- Neutral if polarity == 0

### 5. Data Visualization
- Pie chart to show sentiment distribution.
- WordCloud to highlight the most frequent words

##  📈 Key Results & Interpretation

### 🧾 Sentiment Distribution (from 2,000 tweets):

| Sentiment | % of Tweets | Interpretation                                  |
|-----------|-------------|--------------------------------------------------|
| 👍 Positive | 27.7%       | Many users express satisfaction with Binance.    |
| 👎 Negative | 3.25%       | Very few users express dissatisfaction.          |
| 😐 Neutral  | 69.05%      | Most tweets are informational or market-focused. |

The high proportion of neutral tweets indicates that the Binance conversation on Twitter is largely centered on updates, trading activity, and general information, with a notable positive sentiment reflecting a generally favorable customer experience.

###  🧾 Most Common Words:
Words such as "Binance," "crypto," "regulatory," "bullish," and "exchange" frequently appear. These suggest a mix of trading updates, market news, and platform commentary.

📌 Conclusion
The project highlights how sentiment analysis can help companies like Binance measure public opinion and make data-driven decisions. With a small percentage of negative feedback and a majority neutral stance, Binance enjoys relatively favorable sentiment on Twitter.

By integrating such analysis into business intelligence, organizations can:

- Track user satisfaction
- Identify potential service issues early
- Adapt messaging and services proactively

  🚀 How to Run
1. Clone this repository:
```bash
git clone https://github.com/your-username/binance-twitter-sentiment.git
````
2. Install required libraries:
```bash
pip install tweepy textblob better_profanity wordcloud matplotlib numpy pandas
````
3. Set your Twitter Developer API credentials:
   ```bash
   API_key = "your_api_key"
   API_secret = "your_api_secret"
   access_Token = "your_access_token"
   access_TokenSecret = "your_access_token_secret"
   ````
4. Run the Python script and input a keyword (e.g., "Binance") and number of tweets (e.g., 2000) when prompted.

🔐 Note
Keep your Twitter API credentials private. Never upload them publicly to GitHub or any version control.

👨‍💻 Contact 
- Name: Adio Muizz Adeniyi
- 📧 muizzadio@gmail.com
- 🌍 LinkedIn












