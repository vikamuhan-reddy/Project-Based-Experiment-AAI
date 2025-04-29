<H3>ENTER YOUR NAME : Vikamuhan reddy</H3>
<H3>ENTER YOUR REGISTER NO. 212223240181</H3>
<H3>DATE: 29/04/25</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
Perform sentiment analysis using your Facebook data and count the number of Occurrences of 'Your Name' in the extracted text 


<H3>Program:</H3>
```py
  import pandas as pd
from textblob import TextBlob

# Read data from CSV file
data = pd.read_csv("fb_sentiment.csv")

# Given name to count occurrences
given_name = "Vikamuhan"

# Initialize counters for sentiment analysis
sentiment_counts = {'positive': 0, 'negative': 0, 'neutral': 0}

# Initialize and Count occurrences for the given name
name_occurrences = sum(post.lower().count(given_name.lower()) for post in data['FBPost'])

# Perform sentiment analysis and count occurrences of the given name
for post in data['FBPost']:
    polarity = TextBlob(post).sentiment.polarity
    sentiment_counts['positive'] += polarity > 0
    sentiment_counts['negative'] += polarity < 0
    sentiment_counts['neutral'] += polarity == 0

# Print sentiment analysis results
print("Sentiment Analysis Results:")
for sentiment, count in sentiment_counts.items():
    print(f"{sentiment.capitalize()} sentiment: {count}")

# Print occurrences of the given name
print(f"Occurrences of '{given_name}': {name_occurrences}")

```


<H3>Output:</H3>
<img width="876" alt="Screen Shot 1947-02-09 at 08 53 47" src="https://github.com/user-attachments/assets/70f5ba52-e598-4d8b-8a8d-815f2df8e827" />


<H3>Inference:</H3>
I learned how to read data from a file and check the mood of each post using TextBlob. I also learned how to count how many times a name appears in the posts. This helped me understand how to work with text and do simple analysis in Python.
