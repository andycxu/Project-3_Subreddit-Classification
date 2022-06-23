Project 3: Web APIs & NLP 
                         by Chenhao Andy Xu
                         
1. Exclusive Summary
Reddict has been one of the largest online platform of communities for people all over the world. On reddit, people from different countries with different languages can talk to each other about various topics. Each topic on Reddit is called a subreddit. Due to high web traffic, Reddit received many advertisement requests and all other kind of business that end with high revenue every year. However, problems exist at the same time. One of the common customer reported issue is that posts sometimes are placed in wrong subreddits. Some of them are posted in wrong subreddits by users and some are placed to wrong subreddits by Reddit administrators. In reddit, we believe that provide easy access of the content and clean reading environment are very important to both our users and our company because the number of users and total web traffic are the most important factors of Reddit. 

In this project, a solution is proposed to auto categorize misplaced posts into correct corresponding subreddit. The techniques used are machine learning based classifiers and Natural Language Processing (NLP). The NLP helps computer to understand human language and vocabulary and classifier tecniques can provide which subreddit the post should be belong to. The project uses subreddit of piano and drum as inital model setup. The goal is to increase the accuracy rate for the prediction of posts without proper subreddits. Classifier methods like Logistic Regression, K Nearest Neighbors (KNN), and Random Forest Classifier (RFC) and NLP methods of Countvectorizer and Tfidfvectorizer are used to analyze the posts' title and selftext. 

With this created model, upto 90% of misplace posts are categorized into correct subreddits. Compare to the baseline accuracy, it is about 40% higher (The baseline accuracy is 52%). This increase in the accuracy of classification will probably reduce the most of our user complaints. The reddit total traffic and revene would also possibly increase due to the ease of content retrieve. User experience would be raised to an elite level. 

The model has been ready for actual applicatin at this moment. It can also apply to other subreddit with minor adjustment on parameters. If Reddit approve the solution that our department proposed, the reddit website will be clean and easy to read in future. At the same time, we will continue optimize the model and continue raise the accuracy score for classification. More detailed information is explained in the following presentation and report book. If you are interested in the project, it's my horner to have you read my approach steps. 

2. Problem Statement
As a member in the Reddit maintain team, it's my job to ensure all post belong to the corresponding subreddits. Recently, reddit users complained more and more about misplaced posts which increased the reading difficultness. In order to maintain users' satisfication and web traffic, our team is required to create a solution to accurately classify posts into correct subreddits. 
In this project, subreddits of piano and drum are selected as initial model setup. Mutiple classification and NLP technqiues are used to train a model that the model is able to classify a post either belongs to piano or drum. The goal is to increase the accuracy rate as higher as possible. 

2. Data Collection and Basic Approach
All data retrieved from reddit website from the most recent to least recent. About 4100 posts come from the subreddit piano and about 3800 post come from the subreddit drum. Features are considered in the analysis are title and selftext. One feature model utlize only the title to predict the catrgory while two feature model utlize both title and selftext for analysis. The one feature model runs through three types of classifier methods (Logistic Regression, KNN, and RFC) and two type of NLPs (Countvectorizer and Tfidfvectorizer), which gives 6 models. for each model, parameters are furhter explored by grid search method, which give 12 models. In addition, the two feature model is processed under only logistic regression, which also contained 4 models. Thus, the approach contains 16 models. 
Logistic regression is selected because it's simple and offen have high accuracy. KNN is selected because KNN have mutiple parameters to explore and digging in grid search step. RFC is selected because it's decision tree based method and it's different from previous two mthods. 

The selftext in dataset had a lot of missing value. Instead of dropping them, empth string is used to replace so that all corresponding titles are saved. The data then split into train and test set. The split ratio is 0.67 and 0.33. There are 5310 rows of training data and 2616 rows of tesing data. Common words are checked. Because the model is not limited in piano-drum classifier, common words like'piano' and 'drum' is removed as well as common 'english' default words. 

3. Data Analysis
3.1. One Feature Model - Logistic Regression
Logistic regression gives a good accuracy score. Under Countvectorizer, the accuracy for test set is 0.877. Under Tfidfvectorizer, it's 0.881. The grid search parameters includes ngram range, min_df and logisticregression C score. Due to the high accuracy, the grid search does not imporve significantly. For Countvectorizer, it's 0.879 and 0.880 for Tfidfvectorizer. 

3.2. One Feature Model - KNN
The results of KNN are 0.728 for Countvectorizer and 0.650 for Tfidfvectorizer. Lower acccuracy usually indicate an increase post grid search. The grid search parameters includes number of neighbors, weight of each neighbor, and the distance metric of neighbors. As the result, the accuracy is 0.778 for Countvectorizer and 0.730 for Tfidfvectorizer. 

3.3. One Feature Model - Random Forest Classifier
The result of RFC stayed between previous two models. the accuracy score if 0.849 for Countvectorizer and 0.856 for Tfidfvectorizer. After grid search with adjustment on n_estimators, max_depth, min_sample_split, it's 0.817 for Countvectorizer and 0.815 for Tfidfvectorizer. 

3.4. Two Feature Model - Logistic Regression
With no surprise, the two feature model improve the accuracy. Both the accuracy scores are about 0.898. After grid search, it's about 0.899. 

4. Conclusion
The proposed model increased accuracy rate from 12.5% o 34.8% from baseline. However, it encountered bottleneck for accuracy score around 90%. In order to improve, three methods can be tried in future:
1). collect more data points
2). optimize model by further digging on parameters
3). try other models. 