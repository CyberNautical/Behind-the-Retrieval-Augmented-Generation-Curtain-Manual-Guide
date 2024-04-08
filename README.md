# Manual Demo for Retrieval Augmented Generation
This repository will introduce you to Retrieval Augmented Generation (RAG) with
easy to use examples that you can build upon. The examples use Python with
Jupyter Notebooks and CSV files. The vector database uses the Qdrant database
which can run in-memory.

## RAG Cycle

RAG is a pattern which uses your data with an LLM to generate answers specific to your data. When a user asks a question, the data store is searched based on user input. The user question is then combined with the matching results and sent to the LLM using a prompt (explicit instructions to an AI or machine learning model) to generate the desired answer. This can be illustrated as follows.

![image](https://github.com/armansalimi-microsoft/RAG_Manual_DEMO/assets/150470041/2ae2d1b4-66ed-42fa-813b-9f8226056a44)

RAG uses your data to generate answers to the user question. For RAG to work well, we need to find a way to search and send your data in an easy and cost efficient manner to the LLMs. This is achieved by using an Index. An Index is a data store which allows you to search data efficiently. This is very useful in RAG. An Index can be optimized for LLMs by creating Vectors (text/data converted to number sequences using an embedding model). A good Index usually has efficient search capabilities like keyword searches, semantic searches, vector searches or a combination of these. This optimized RAG pattern can be illustrated as follows.

![image](https://github.com/armansalimi-microsoft/RAG_Manual_DEMO/assets/150470041/7df60656-f4d9-4dc3-9a42-12b04d3c51f4)


## Key Terms
•	Retrieval augmented generation (RAG): A technique in AI where a large language model accesses new or recent data outside its training set to provide better answers and improved results.

•	Vector database: A search engine or database that stores vectorized documents, enabling more accurate information retrieval for AI models.

•	Embeddings: Representations of text data as vectors in a high-dimensional space, allowing similarity comparisons between different pieces of text.

•	Azure AI Search: Microsoft's cloud-based search service (formerly Azure Cognitive Services Search) that offers retrieval augmentation capabilities for large language models.

•	Comma separated value (CSV): A common data format where values are separated by commas, used in this transcript to demonstrate RAG implementation with a vector database.

•	Pandas library: A Python library used for data manipulation and analysis, particularly useful when working with CSV files.

•	Qdrant: Software used for creating an in-memory vector database search, enabling efficient text retrieval and embedding storage.

•	Sentence transformers: A tool to encode sentences into numerical representations (embeddings) that can be compared using cosine similarity or other distance metrics.

•	Cosine distance: A measure of similarity between two non-zero vectors in a multi-dimensional space, often used in text analysis and information retrieval.


## Setup your environment

This example can run in Codespaces but you can use the following if you are
cloniing this repository:

**Install the dependencies**

Create the virtual environment and install the dependencies:

```
python3 -m venv .venv
source .venv/bin/activate
.venv/bin/pip install -r requirements.txt
```

Here is a summary of what this repository will use:

1. [Qdrant](https://github.com/qdrant/qdrant) for the vector database. We will use an in-memory database for the examples
2. [Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/overview) for the LLM - OpenAI API compatible key and endpoint 
3. [OpenAI's Python API](https://pypi.org/project/openai/) to connect to the LLM after retrieving the vectors response from Qdrant
4. Sentence Transformers to create the embeddings with minimal effort


## Step 1: Import your data

The data will be used to create the embeddings for the vector database later and you will need to format it as a list of dictionaries.

Dataset: [Kaggle Myntra Fashion Products - Top 150 results](https://www.kaggle.com/datasets/nirokey/myntra-fashion-products)

## SAtep 2: Create embeddings

Use Sentence Transformers to create the embeddings for your data. This will be used to store the vectors in the Qdrant database. You will verify that the embeddings are created and stored in the database and that a search works correctly

## Step 3: Create a RAG with LLM and Qdrant using your own data

Use OpenAI API endpoint to create a RAG with your own data. 

## Step 4: Test

