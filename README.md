<h1 align="center">Movie Recommendation System</h1>

<hr>

# Table of Contents
1. [Business Case](#business-case)
2. [Dataset](#dataset)
3. [Approach](#approach)
4. [R Functions Used](#r-functions-used)
   - [Base R Functions](#base-r-functions)
   - [dplyr Functions](#dplyr-functions)
   - [igraph Functions](#igraph-functions)
5. [What We Learned About Data](#what-we-learned-about-data)


<hr>

# Business Case
Personalized recommendation systems have become essential in enhancing user engagement and satisfaction on digital platforms. In the entertainment industry, such as streaming services and movie platforms, recommending relevant movies helps retain users, increase watch time, and boost subscriptions.

<hr>

# Dataset
- **Dataset Name**: Movie Recommendation System
- **Nodes**: 221,588 (users and movies)
- **Edges**: 25,000,095
- **Type**: Undirected
- **Description**: This project uses the MovieLens dataset, a popular benchmark dataset for recommender systems. It contains user-generated movie ratings along with metadata like movie titles and genres. Each row represents a user, each column a movie, and the values indicate user ratings. This structured data enables personalized movie recommendations based on user preferences and movie similarities.
- **URL**: [Movie Recommendation System](https://www.kaggle.com/datasets/parasharmanas/movie-recommendation-system?select=ratings.csv)


<hr>


# Approach
To enrich the dataset, we joined the ratings.csv and movies.csv files based on the movieId column. This merge provided additional movie-related information, such as titles and genres, which helped in making more informed recommendations.

For this project, we began by loading the dataset and selecting key features like userId, movieId, and rating to focus on the user-movie interactions. We then created an edge list to represent these interactions as a graph, where users are connected to movies, with ratings as the edge weights. This allowed us to better understand the relationships within the data.

To simplify the graph, we selected only the top users and top-rated movies, ensuring the data was manageable and focused on the most active participants. We then created a smaller, simplified graph and removed unnecessary edges and self-loops.

We used various graph metrics like eccentricity, cohesive blocks, and PageRank to gain insights into the structure of the data and identify important nodes. Further, we explored community detection with the Louvain method and visualized the graph using customized layouts, adjusting node and edge attributes to highlight relationships based on ratings. Finally, we employed graph rewiring and centrality measures to explore potential changes and the most influential users and movies in the network.



<hr>

# R Functions Used

## Base R Functions
`read.csv()`, `head()`, `range()`, `paste0()`, `data.frame()`, `print()`, `cat()`, `length()`, `sapply()`, `ifelse()`, `sort()`, `seq()`, `max()`, `min()`

## dplyr Functions
`group_by()`, `summarise()`, `summarize()` (alias of `summarise()`), `arrange()`, `filter()`, `tally()`, `top_n()`

## igraph Functions
`graph_from_data_frame()`, `vcount()`, `ecount()`, `simplify()`, `eccentricity()`, `cohesive_blocks()`, `page_rank()`, `V()`, `E()`, `is_separator()`, `degree()`, `fit_power_law()`, `rewire()`, `each_edge()`, `layout_with_fr()`, `coreness()`, `cocitation()`, `as.directed()`, `max_flow()`, `make_line_graph()`, `betweenness()`, `diameter()`, `get.diameter()`, `maximal.cliques()`, `ego()`, `alpha_centrality()`, `cluster_louvain()`, `membership()`, `plot()` 


<hr>

# What we learned about data
In the movie recommendation system task, we learned that the data provides valuable insights into user preferences and movie characteristics. By analyzing the user ratings, movie genres, and other metadata, we can uncover patterns that help predict a user's interest in a particular movie. The dataset typically includes information such as movie titles, genres, user ratings, and possibly user demographic data. This allows us to explore different recommendation techniques, such as collaborative filtering, content-based filtering, and hybrid approaches. Through this analysis, we acquired a better understanding of how to leverage historical interactions and movie features to generate personalized recommendations for users, improving user engagement and satisfaction. The data reveals how users' tastes vary, and with the right approach, we can provide movie suggestions that closely align with their preferences.
