# Online Twitter Sentiment Analysis by Spark Streaming

Sentiment Analysis (SA) relates to the use of: Natural Language Processing (NLP), analysis and computational linguistics text to extract and identify subjective information in the source material. 
A fundamental task of SA is to "classify" the polarity of a given document text, phrases or levels of functionality/appearance - whether the opinion expressed in a document or in a sentence is positive, negative or neutral.
Usually, this analysis is performed "offline" using Machine Learning (ML) techniques. In this project two online tweet classification methods have been proposed, which exploits the well known framework "Apache Spark" for processing the data and the tool "Apache Zeppelin" for data visualization.


# Prerequisites

  - Python 2.7 or greater <br>
  - Pyspark
  - Kafka
  - ZooKeeper
  - Nltk
  
  # Usage
  
  1. Since Kafka uses ZooKeeper, you need to first start a ZooKeeper server if you don't already have one. You can use the convenience script packaged with kafka to get a quick-and-dirty single-node ZooKeeper instance, by running the following command:
  
  `bin/zookeeper-server-start.sh config/zookeeper.properties`
  
  2. Start the Kafka server:
  
  `bin/kafka-server-start.sh config/server.properties`
  
  Once the servers have been started, you can use one of the two models:
  
  2.1 `StreamingNaiveBayesClassification.py`:
  
  `spark-submit
  --jars ~/workspace_spark/spark-1.6.2-bin-hadoop2.6/external/spark-streaming-kafka-assembly_2.10-1.6.2.jar
  --py-files modules/TweetPreProcessing.py,modules/Emoticons.py,modules/Acronyms.py ~/PycharmProjects/TwitterSentimentAnalysis/twitter-kakfa-consumer/src/main/python/StreamingNaiveBayesClassification.py`

  2.2 `StreamingKmeansClassification.py`:
  
  `spark-submit
  --jars ~/workspace_spark/spark-1.6.2-bin-hadoop2.6/external/spark-streaming-kafka-assembly_2.10-1.6.2.jar
  --py-files modules/TweetPreProcessing.py,modules/Emoticons.py,modules/Acronyms.py ~/PycharmProjects/TwitterSentimentAnalysis/twitter-kakfa-consumer/src/main/python/StreamingKmeansClassification.py`
  
  
  
