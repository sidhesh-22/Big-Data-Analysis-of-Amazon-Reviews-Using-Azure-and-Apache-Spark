# Big-Data-Analysis-of-Amazon-Reviews-Using-Azure-and-Apache-Spark

## Table of Contents

- [Project Overview](project-overview)
- [Data Source](data-source)
- [Major steps followed](major-steps-followed)
- [Insights and Findings](insights-and-findings)
- [Conclusion and further scope](conclusion-and-further-scope)


### Project Overview

This is a scalable end-to-end data processing project for conducting sentiment and trend analysis of the Amazon Fine Food Reviews dataset using distributed computing with Apache Spark. The main aim was to examine consumer behavior and inspect patterns at scale by responding to four main research queries: (i) which items get the most and least ratings, (ii) how length of review relates to star ratings, (iii) whether or not users show a tendency towards extreme ratings, and (iv) whether repeat reviewers reflect uniform rating practice.

Below is an overview of an Azure Storage Account

![image](https://github.com/user-attachments/assets/a135b4ef-c71a-458c-b231-3dd4cac95df7)



### Data Source

The dataset used in this project has been taken from Kaggle.


### Major steps followed

1. Fetching the dataset from Kaggle.
2. Initializing Spark Session with all the necessary jar files.
3. Accessing the Azure Blob Storage data using Spark.
4. Performing basic data preprocessing in Jupyter Notebook using Python.
5. Loading the cleaned data into the PostgreSQL database.
6. Exporting the cleaned data from PostgreSQL into a CSV format.
7. Loading the clean and processed data exported from PostgreSQL into a Python dataframe.
8. Creating data visuals to answer the research questions.
9. Creating an automated data pipeline using a batch script and saving it in a .sh format file, which can be directly triggered from the terminal.


The figure below shows an Azure Blob Container with the Uploaded Dataset:


![image](https://github.com/user-attachments/assets/6d2387fa-8e65-45f6-b977-b5823b045bf4)



### Insights and Findings

1. To address the first research question—which products have the highest and lowest ratings—the top 10 most-reviewed products were selected and their average ratings computed.
   

![image](https://github.com/user-attachments/assets/93d08fa3-c42a-40cc-b612-5655f1c2b50f)


This plot indicates minimal variation between leading products, which could suggest product stability or brand faithfulness as the cause of high average ratings.


2. To address the second research question—whether review length affects rating—a scatter plot was created comparing review word count to assigned rating scores. The figure below indicates that the majority of reviews are less than 500 words, with a high concentration of reviews between 1 and 5 stars. There is no obvious linear relationship, although very long reviews appear to group around lower or mid-range ratings.


![image](https://github.com/user-attachments/assets/4353dbc4-1e42-49ee-83ea-f3c42ae34cc8)


This suggests that while review length may not significantly affect ratings, longer reviews may be more critical, indicating the user has more feedback to offer, positive or negative.


3. The third question—is there bias toward the use of extreme ratings—was dealt with by considering the distribution of all review ratings. Figure 6 shows a strong skew for 5-star ratings, the majority of reviews. There is a steep decline in the number of reviews for the ratings 2, 3, or 4, affirming a bimodal distribution skewed to the extremes.

![image](https://github.com/user-attachments/assets/955d0708-8378-4d37-85b6-dbd57849068b)

This corresponds with previous research that indicates that online reviews tend to be emotionally polarized, either extremely dissatisfied or highly satisfied, and few neutral reviews.


4. To respond to the last question—do repeat reviewers exhibit rating consistency—the average rating per individual user was computed. As indicated in Figure 7, nearly all users had an average rating bunched together at 4.5 to 5.0. The distribution is very peaked, which indicates that repeat reviewers are likely to be continually positive in their ratings.


![image](https://github.com/user-attachments/assets/a7704c5a-5843-423e-ac10-5e41ccbb523e)


This finding indicates that most users are positively skewed or mostly contented with their orders, so it's difficult to detect truly neutral writers.


### Conclusion and further scope

- This project was able to successfully deploy a scalable cloud-based data pipeline for trend and sentiment analysis with the Amazon Fine Food Reviews dataset.
- With distributed processing through Apache Spark, data extraction from Azure Blob Storage, and structured persistence with PostgreSQL, the system proved able to efficiently process large-scale review data.
- These results emphasize the significance of taking both textual and behavioral aspects into account while analyzing consumer reviews.
- Sentiment scores from review text were not derived from high-end NLP models, and all analyses only considered descriptive trends and not predictive modeling.
- Future research can build on this base by combining real-time streaming data with Spark Structured Streaming or Kafka, and using sentiment classification models like BERT or RoBERTa for richer text insights.
- Further, clustering user activities or constructing product recommendation systems would add greater utility to the analysis.
