# Amazon Reviews Clustering

This project involves applying topic modeling to Amazon product reviews using Latent Dirichlet Allocation (LDA) to discover classes of concerns expressed by customers.


## Data Preparation

I started by selecting four related categories from the metadata and mapped those ASINs to the ASINs in the reviews data to pull these reviews. I removed stopwords from the reviewsText using nltk. I converted the reviews to lowercase and tokenized the reviewsText column and then lemmatized this data. I was still getting some single and double letter strings such as "a","s","it","us" etc., so I removed these strings too. I then created a dictionary and corpus.


## LDA Model Fitting and Evaluation

Next, I fit an LDA model to the corpus and evaluated its performance by inspecting the topics and applying a coherence metric. I experimented with different parameters such as the number of topics, workers, passes, etc., to improve the coherence. I preferred a model where the number of topics was high, approximately 20, and the workers were low with high passes. If I reduced the number of topics to around 5 or kept the number of workers to 4 or kept the number of passes low approx 2, the model ran faster but gave me lower coherence (0.49-0.528). For my preferred model, the coherence was around 0.55.


## Alternative Approach
Based on the initial model, I investigated at least one alternative approach that I expected may yield more coherent topics. I tried using different data preprocessing pipelines, changing LDA hyper-parameters and the choice of clustering algorithm itself. However, none of these approaches improved the coherence beyond my preferred model.
