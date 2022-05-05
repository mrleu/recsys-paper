# recsys-paper

## Collaborative Filtering
- [x] [Collaborative Filtering for Implicit Feedback Datasets](http://yifanhu.net/PUB/cf.pdf)
- [x] [Scaling Collaborative Filtering with PySpark](https://engineeringblog.yelp.com/2018/05/scaling-collaborative-filtering-with-pyspark.html)

## Hybrid Recommendation System
- [x] [Beyond Matrix Factorization: Using hybrid features for user-business recommendations](https://engineeringblog.yelp.com/2022/04/beyond-matrix-factorization-using-hybrid-features-for-user-business-recommendations.html)

## Session Based Recommendation System
- [x] [SESSION-BASED RECOMMENDATIONS WITH RECURRENT NEURAL NETWORKS](https://arxiv.org/pdf/1511.06939.pdf)
- [x] [Contextual Sequence Modeling for Recommendation withRecurrent Neural Networks](https://arxiv.org/pdf/1706.07684.pdf)

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
