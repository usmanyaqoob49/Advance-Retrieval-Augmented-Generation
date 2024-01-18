# Advance-Retrieval Augmented Generation
-- Techniques to Enhance the RAG, to get more accurate and on point informatino from the documents.


RAG Techniques are used to get the documents that are related to query but it is hard to get the close to actual answer, for getting the closely related things we can apply several advance RAG Techniuqes:

	1. Expand the Query:
	   Rewrite the user's query to multiple queries.
Now as we have long tailed documents that are retrieved as relavent documents. We will use Cross Encoder from Sentence Encoder to rank each document according to query:

What is Cross Encoder and How it performs this Ranking thing ?
So Basically Sentence Encoder have two types of encoders:
        
        1: Bi-Encoder:
           This type of Encoder takes the two Queries seprately and pass them from seprate encoder and then perfoms cosine similarity to give the relevancy among both.
           
        2: Cross Encoder:
           This type of encoder process inputs (we are considering 2) together as single unit. This allows the model to directly compare and contrast the inputs and understand their relation in better way, also in the end it returns the score from 0 to 1 that shows the similarity among both :)
           
         
-Now in short we use Cross Encoder as Ranking thing by giving it Query and Retrived Documents one by one and in the end we will get score of each document representing how much query is related to that specified document.




Using Combination of Query Expansion and Re-ranking:
Lastly why not to combine the Query Expansion technique in which we were generating extra queries using LLM that were related to our main query, and Re-ranking to optimize a bit more. But in this scenario we will get 10 documents for each query and then we remove duplicated documents (that were retrieved by every query) and then we can apply re-ranking to get the most relevant documents(may be top 5 or so). 
