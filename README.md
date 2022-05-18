# recsys-paper
notes and resources for all things recsys.

## Recommendatoin System Literature Review
- [x] [A Survey of Recommendation Systems: Recommendation Models, Techniques, and Application Fields](file:///Users/alexleu/Desktop/electronics-11-00141-v2.pdf)
    - trend analysis/surevy for recommendatoin systems
    - content based/collaobrative based/hybrid based
    - hybrid has 7 types 
        - weighted
        - switching
        - cascade
        - mixed
        - feature combinaton
        - feature augmentation
        - meta level
    - simpliest way to evaluate recommendation is through RMSE.

## Conversational Recommendation System
- [x] [Conversational Contextual Bandit: Algorithm and Application](https://arxiv.org/pdf/1906.01219.pdf)
    - contextual bandit usually get counts based on count of clicks.
    - using conversation preference to feed into the mondel for the contextual bandit.
        - this helps improves the learning speed.
    - new recommendation, each news is an arm, and the contextual vector would be the reward the user get to maximize the reward
    - conversation is added as part of the contextual vector
    - select the arm that maximzies the reward that is the combination of the contextual vector and the conversational vector.


## Contextual Recommendation System
- [x] [Context-Aware Recommender Systems](https://www.researchgate.net/publication/220605653_Context-Aware_Recommender_Systems)
    - traditonal recommendation system formed the problem as ITEM X CUSTOMER -> Ratings
    - Contextual hopes to form it as ITEM X CUSTOMER X CONTEXT -> Ratings
    - in the form of movie recommendations, context can be in the form of 1) companion, 2) time, and 3) theater
    - household identity can be inferred based on the observed tv program watched.
    - pre-filtering/post-filtering/contextual filtering techniques.
    

## Collaborative Filtering
- [x] [Collaborative Filtering for Implicit Feedback Datasets](http://yifanhu.net/PUB/cf.pdf)
- [x] [Scaling Collaborative Filtering with PySpark](https://engineeringblog.yelp.com/2018/05/scaling-collaborative-filtering-with-pyspark.html)

## Hybrid Recommendation System
- [x] [Beyond Matrix Factorization: Using hybrid features for user-business recommendations](https://engineeringblog.yelp.com/2022/04/beyond-matrix-factorization-using-hybrid-features-for-user-business-recommendations.html)
    - justifications that matrix factorization does not work well for users with few interactions
    - tricky to add new content on the fly.
    - combined both collaborative filtering and content based filtering.
    - textual similarity between user and the business through universal sentence encoder.

## Session Based Recommendation System
- [x] [SESSION-BASED RECOMMENDATIONS WITH RECURRENT NEURAL NETWORKS](https://arxiv.org/pdf/1511.06939.pdf)
- [x] [Contextual Sequence Modeling for Recommendation withRecurrent Neural Networks](https://arxiv.org/pdf/1706.07684.pdf)

## Sequence Based Recommendation System
- [ ] [Sequential Recommender Systems: Challenges, Progress and Prospects](https://www.ijcai.org/proceedings/2019/0883.pdf)
- [x] [Deep Learning for Recommender Systems: Next basket prediction and sequential product recommendation](https://medium.com/recombee-blog/deep-learning-for-recommender-systems-next-basket-prediction-and-sequential-product-recommendation-796228b34dee)
    - uses long term dynamics + short term dynamics to make prediciton
    - mostly summarizes sequential product recommendation examples

## Graphical Neural Network Recommendation System
- [x] [Graph Neural Networks for Recommender Systems: Challenges, Methods, and Directions](https://arxiv.org/pdf/2109.12843.pdf)
- [x] [Improving Conversational Recommender Systems via Knowledge Graph based Semantic Fusion](https://arxiv.org/pdf/2007.04032.pdf)

## User Embedding Recommendation
- [x] [PinnerSage: Multi-Modal User Embedding Framework for Recommendations at Pinterest](https://arxiv.org/pdf/2007.03634.pdf)
  - 4 single embedding approach for user embedding
    - last pin is user's embedding
    - time decay average age as user's embedding
    - predict the next embedding
    - k means oracle.
  - compute a medoid based on 90 days of user's activity.
- [x] [User Embedding for Scholarly Microblog Recommendation](https://aclanthology.org/P16-2073.pdf)
  - average text vectors as user vector.
  - cosine similarity is used to recommend the article to the user.
- [x] [Contextual and Sequential User Embeddings for Large-Scale Music Recommendation](https://labtomarket.files.wordpress.com/2020/08/recsys2020.pdf)
  - define session as an average of the track embeddings.
    - embedding for skipped track and embeddings for played track.
  - loss function is defined by the predicted embedding vs. observed embeddings via cosine similarity.
  - LSTM architecture where session embedding + contextual feature + dense features are combined, hidden state is passed to the next sesion.
  - Contextual feature includes day of week, time of the day, and device.
  - RELU is applied to contextual features and session embeddings. 
  - output and hidden states were computed with LSTM with both the played embedding and the skipped embedding.
  - output from LSTM are combined together, and then applied fully connected neural network. this is the user embedding.
  - final user embedding is computed by long term user contextual information with current session embedding.
- [x] [Personalized Embedding-based e-Commerce Recommendations at eBay]()
    - softmax probability with temperature
    - gated recurrent neural work to pass along user's history.
    - dot product between user embedding and item embedding 
    - in batch negative sampling

## Bandit
- [x] [A Contextual-Bandit Approach to Personalized News Article Recommendation](https://arxiv.org/pdf/1003.0146.pdf)
    - disjoin linear model (arms weights are not shared among differnet arms)
    - ridge regression is applied on training data to give estimates
    - hybrid linear model has features shared between arms.
- [x] [Deep neural network marketplace recommenders in online experiments](https://arxiv.org/pdf/1809.02130.pdf)
    - hybrid item representation model
        - used ALS with click and conversion signal with more weight on conversion
        - textual feature is a variant of CNN using word2vec
        - image features are text prediction based on the image
    
## Two Tower
- [x] [Model-based candidate generation for account recommendations](https://blog.twitter.com/engineering/en_us/topics/insights/2022/model-based-candidate-generation-for-account-recommendations)
    - allows to add in graph based features.
    - 1 tower focuses on getting consumption behavior
    - 1 tower focuses on production behavior