# Twitter Airline Sentiment Analysis Dataset

## Description  
This dataset contains tweets related to major airlines, along with sentiment labels and metadata. It is designed for analyzing customer opinions, sentiment trends, and complaint reasons in the airline industry. Key features include sentiment confidence scores, negative reason categorization, retweet counts, and user/timezone information.

## Dataset Overview  
The data is structured as a tabular file (e.g., CSV) with the following columns:  

| Column Name                     | Description                                                                 |
|---------------------------------|-----------------------------------------------------------------------------|
| `tweet_id`                      | Unique identifier for the tweet.                                            |
| `airline_sentiment`             | Sentiment classification (negative/neutral/positive).                       |
| `airline_sentiment_confidence`  | Confidence score (0-1) for the sentiment label.                             |
| `negativereason`                | Categorized reason for negative sentiment (e.g., "Lost Luggage").           |
| `negativereason_confidence`     | Confidence score for the assigned negative reason.                          |
| `airline`                       | Airline mentioned in the tweet (e.g., "Delta", "United").                   |
| `airline_sentiment_gold`        | Gold-standard sentiment label (if available, for validation).               |
| `name`                          | Twitter username of the poster.                                             |
| `negativereason_gold`           | Gold-standard negative reason (if available).                               |
| `retweet_count`                 | Number of times the tweet was retweeted.                                     |
| `text`                          | Full text of the tweet.                                                     |
| `tweet_coord`                   | GPS coordinates of the tweet's origin (if enabled by user).                 |
| `tweet_created`                 | Timestamp of the tweet.                                                     |
| `tweet_location`                | User-provided location metadata.                                            |
| `user_timezone`                 | Timezone of the user.                                                       |

## Potential Use Cases  
- **Sentiment Analysis**: Train NLP models to classify airline-related sentiment.  
- **Complaint Analysis**: Identify common pain points via `negativereason` categorization.  
- **Retweet Impact**: Study correlations between sentiment and retweet counts.  
- **Geospatial Trends**: Map complaints/sentiment by location (using `tweet_coord`).  
- **Temporal Analysis**: Track sentiment patterns over time.  

## Usage  
### Load Data  
```python
import pandas as pd

df = pd.read_csv("airline_sentiment.csv")
print(df[['text', 'airline_sentiment']].head())
