# GraphX-and-Pipelines-Big-Data-Analytics
 GraphX:
 We worked with the Apache GraphX library. The dataset for this project was a graph
 that shows connections between various airports. This data was downloaded for January 2025 from Bureau of Transportation
 website (https://transtats.bts.gov/). We selected following fields for this project:
 • Origin (Origin Airport Code)
 • OriginCityName 
 • Dst (Destination Airport Code)
 • DstCityName 
 The following questions were answered:
 a. Find the top 5 nodes with the highest outdegree and find the count of the number of outgoing
 edges in each.
 b. Find the top 5 nodes with the highest indegree and find the count of the number of incoming edges
 in each.
 c. Calculate PageRank for each of the nodes and output the top 5 nodes with the highest PageRank
 values. You are free to define any suitable parameters.
 d. Run the strongly connected components algorithm on it and find the top 5 components with the
 largest number of nodes. If you can’t run this on the entire dataset, you can choose a smaller sample.
 e. Run the triangle counts algorithm on each of the vertices and output the top 5 vertices with the
 largest triangle count. In case of ties, you can randomly select the top 5 vertices.


 Tweet processing and Classification using Pipelines:
 In this part, we worked with a set of Tweets about US airlines and examined their sentiment polarity.
 More details about the dataset is available at:
 https://www.kaggle.com/crowdflower/twitter-airline-sentiment. It is part of the Kaggle
 competition on Twitter US Airline Sentiment. Our aim is to learn to classify Tweets as either “pos
itive”, “neutral”, or “negative” by using logistic regression classifier and pipelines for pre-processing
 and model building.
We created a pipeline with the following steps.
 1. Loading: First step is to load the text file from the path specified in argument 1. After that we will need to remove rows where the text field is null.
 2. Pre-Processing: We start by creating a pre-processing step with the following stages:
 • Stop Word Remover: Remove stop-words from the text column using the org.apache.spark.ml.feature.StopWordsRemover class.
 • Tokenizer: Transform the text column into words by breaking down the sentence into words using import org.apache.spark.ml.feature.Tokenizer class.
 • Term Hashing: Convert words to term-frequency vectors using import org.apache.spark.ml.feature.HashingTF class.
 • Label Conversion: The label is a string e.g. “Positive”, which we converted to numeric format using import org.apache.spark.ml.feature.StringIndexer class.
 3. Model Creation: We created a logistic regression classification model by creating a ParameterGridBuilder for parameter tuning and then used the CrossValidator
object for finding the best model parameters. 
 4. Model Testing & Cross Validation: Next, we did training and testing of our model on the given dataset and output classification evaluation metrics, such as accuracy, etc. 
 
 
