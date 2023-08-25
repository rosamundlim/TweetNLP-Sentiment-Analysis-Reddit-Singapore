# TweetNLP-Sentiment-Analysis-Reddit-Singapore
Sentiment Analysis using TweetNLP on r/singapore opinion of SG presidential candidate Mr. Tan Kin Lian in 2023. 

## Background
On Sep 1 2023, Singaporeans will exercise their voting rights to choose the country's ninth president.
Among the eligible candidates, Mr. Tan Kin Lian, was noted by several pundits as a controversial candidate.
This is in part due to his various social media postings, one of which has resulted in AWARE, a women advocacy group to
[raise their concerns](https://www.channelnewsasia.com/singapore/aware-tan-kin-lian-pretty-girls-presidential-election-3712586) on his candidacy. 

This is a sentiment analysis on top r/singapore threads regarding Mr. Tan Kin Lian's candidacy (r/singapore is likely to have a younger demographic) 
using the [TweetNLP library](https://github.com/cardiffnlp/tweetnlp) that is based on the roberta model by cardiffnlp. 

This is *NOT* intended to be an opinion piece on Mr. Tan's candidacy, and it only seeks to understand the sentiments of r/singapore users towards Mr. Tan. 

## Notable Tools utilized
1. asyncpraw
2. regex
3. tweetNLP
4. matplotlib/seaborn
5. pandas

## Scraping Reddit
Using the [asyncpraw library](https://asyncpraw.readthedocs.io/en/stable/), I extracted comments on 10 highly commented Reddit threads regarding Mr. Tan Kin Lian's 
candidacy *as of 26 August 2022*.

## Preprocessing and using the pre-trained model via TweetNLP
Preprocessing focused on converting everything to lowercase, removing hyperlinks in comments, punctuations etc. 
Note that the TweetNLP module takes in a string. 
TweetNLP would be a relevant library to use as it is trained on social media, and how you communicate on Reddit is not very different from Twitter.
Main issue is the idiosyncracy of Singlish on r/singapore that may be a challenge to a pre-trained model. 

## Results 
After tagging each comment and classifying it into the emotion label, prepare the dataframe and relevant tabulations. 

Overall sentiment: ![overall_sentiments](https://github.com/rosamundlim/TweetNLP-Sentiment-Analysis-Reddit-Singapore/assets/42547859/739b9aec-414f-48db-8202-e37ffd43abc0)
r/singapore mostly react negatively, you can observe the emotion labels that are being tagged by Tweetnlp model. 

Sentiment group by reddit thread: ![article_sentiments](https://github.com/rosamundlim/TweetNLP-Sentiment-Analysis-Reddit-Singapore/assets/42547859/02ac3877-46ac-4ac4-a97b-eee2d691956a) 
Now, group it according to the corresponding reddit thread in r/singapore and normalize each emotion within a group by the total count in each group to get a percentage value. 

Most negative reactions: 
1. [Tan Kin Lian's 'pretty girls' posts ignite debate about objectifying women, assessment of presidential candidates](https://www.reddit.com/r/singapore/comments/15yt7fq/tan_kin_lians_pretty_girls_posts_ignite_debate/)
2. [Presidential hopeful Tan Kin Lian accuses various parties of smear campaign](https://www.reddit.com/r/singapore/comments/15xqltm/presidential_hopeful_tan_kin_lian_accuses_various/)
3. [Tan Kin Lian rejects AWARE's concerns he 'objectifies' women, his daughter defends him](https://www.reddit.com/r/singapore/comments/15xrbiy/tan_kin_lian_rejects_awares_concerns_he/) 

Most polarized (similar proportions of negative and positive emotions):
1. [Tan Kin Lian says he will channel public feedback if elected President](https://www.reddit.com/r/singapore/comments/15v6iil/tan_kin_lian_says_he_will_channel_public_feedback/)
   







