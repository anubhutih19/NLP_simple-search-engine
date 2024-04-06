# NLP_simple-search-engine

A search engine that uses text preprocessing, indexing, and query processing to fetch relevant ecommerce product listings. 
The additional functionality of translating product descriptions into another language aims to broaden accessibility and usability.
The engine demonstrates how the information retrieval process works on real world data. 



libraries used:
uuid, Spacy, regex, collections, scikitlearn, deep_translator

Note:
Please keep the corpus_ecomm.txt file in the same folder as the project_final.py file.
Implementation

I used Python libraries such as Spacy for NLP tasks, Scikit-learn for TF-IDF computation, and Deep Translator for real-time translation for this project.

The implementation involved several key steps:

- Creating unique identifiers for documents: Following the wikipedia dataset model, I wanted a unique identifier for each product description in the corpus. This identifier was not present in the original dataset, so they had to be created 
- Data parsing and indexing: Product descriptions were parsed and indexed using a unique ID system. Preprocessing techniques like tokenization and lemmatization were applied to organize the data efficiently.
- Search and retrieval system: A TF-IDF vectorizer was used to transform text data into a suitable format for cosine similarity calculations, facilitating the search functionality based on user queries
- Translation feature: The top search results are translated into Korean using the GoogleTranslator API, demonstrating the application of NLP in real-world ecommerce scenarios. The code can be modified to choose any other language for translation

This approach fundamentally leverages the vector space model to facilitate the retrieval and ranking of documents (product descriptions in my dataset) based on their relevance to user queries, demonstrating a practical application of information retrieval concepts using the vector space model.

Usage of Vector Space Model 
1. TF-IDF Vectorization: This project uses the TfidfVectorizer from Scikit-learn python library to transform text data into a vector space model. This vectorizer converts the text documents (product descriptions) into a matrix of TF-IDF features, which is essential for computing text relevance in a vector space.
The data corpus consists of product descriptions, and the preprocessing function handles tokenization along with other text normalization tasks like lemmatization and stop-word removal.
2. Query processing in vector space: When processing a search query, my code transforms the query into the same vector space as the documents using the previously fitted TF-IDF vectorizer.
3. Cosine similarity calculation: After transforming the query into its vector representation, my code computes the cosine similarities between this query vector and all document vectors in the TF-IDF matrix. This step is crucial as it quantifies the relevance of each document to the given query based on the angle between their vectors in the high-dimensional space.
4. Ranking results: Finally, the documents are ranked according to their similarity scores, and the results are sorted in descending order of relevance.

Results

The search engine was tested with various queries such as "camisole", “slip”, 'USB' ,'corset', 'Memory Card' etc.  and the results were sorted by relevance based on the cosine similarity score. Any search query shows top 10 relevant documents (product descriptions) with their rank and the similarity score. After that, the top results are successfully translated into Korean language, showcasing the engine's capability to handle and present multilingual information. 
