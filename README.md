# CMPE256_Individual_Project
Book Recommendation System

Name:  Mahesh Reddy Konatham
SJSU ID: 013823095

# Abstract:
This project aims at recommending books for users from amazon by their past purchase history using graph theory (network analysis). Searching for a book becomes tedious at times when we have to go through hundreds of books through many pages. This problem can be solved if we have a very good book recommendation system which considers user’s purchase history i.e. the books consumers purchased collectively or together in past. Concept of graph theory is used to make books as vertices and edges are formed between those books which were purchased together, and weighting is given based on the similarity.

# Data collection:

The data for the Book Recommendation system was crawled from Amazon products website for books. This data has fields which includes Id: product id, ASIN (amazon standard identification number) is a ten-digit unique number for every amazon product. Title: Name of the product, sales-rank: overall sales rank of the product, Group: The division of the product like Electronic/book ..etc., similar: ASINs of the products which are purchased together, categories: location of hierarchy in which these product is located and product review information.

 


# Data Pre-processing:

Data pre-processing has to be done in order to clean the data before using for recommendation. Some of the fields remain same as id, ASIN, Title but others like group is filtered to only book, categories are stemmed, lemmatized and stop words are removed, purchased_Together is made from similar ASINs but those which are similar to the product. Total reviews and average rating remain same.

Also, the purchased_Together data in amazon books file is used to make a Purchased_Together Graph structure which has books (ASIN) as Nodes, an Edge exists if the books are purchased together in past and also the weight will be determined by similarity. After the Purchased_Together Graph structure is made Degree- centrality and Clustering co-efficient are also calculated for each Node in the Graph.


 # Methodology:



Calculating Edge weight:

Edge weight for the edges between nodes of purchased_Toogether graph is calculated through two ways 


a)	Based on content of categories:
Similarity between two books in purchased together data is calculated by taking the number of words common in both categories and dividing it with the total number of words in both categories combined.
 

b)	Based on content of Titles:
Similarity between two books in purchased together data is calculated by taking the number of words common in both Titles and dividing it with the total number of words in both Titles combined.
 


# Recommendations:

The python function takes the ASIN of the purchased book by user and the
threshold to which user want the similarity between the purchased and the recommendations as input and then first locates the direct neighbors of the purchased book and then filters based on Average customer ratings and total number of ratings. Finally, after sorting the results recommendations are made based on threshold values and method of similarity calculation.

 

 









