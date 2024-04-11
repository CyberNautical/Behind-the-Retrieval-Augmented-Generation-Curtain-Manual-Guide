# Behind the Retrieval Augmented Generation Curtain- Manual Guide

## Introduction
This document introduces Retrieval Augmented Generation (RAG) with step-by-step, easy-to-follow examples using Python in Jupyter Notebooks, CSV files, and the Qdrant vector database, which can operate in-memory.

## RAG Cycle
RAG is a methodology that combines your dataset with a large language model (LLM) to generate answers specific to your queries. When a user poses a question, the system searches the dataset for relevant data based on the input. 

![image](https://github.com/armansalimi-microsoft/RAG_Manual_DEMO/assets/150470041/2ae2d1b4-66ed-42fa-813b-9f8226056a44)

The results are then combined with the user's query and sent to the LLM as a prompt to generate the desired answer. RAG's efficacy relies on the efficiency of the search mechanism, facilitated by an Index—a data store optimized for quick searches and integrating with LLMs. A robust Index supports various search types, such as keyword, semantic, and vector searches, essential for the optimized RAG pattern.

![image](https://github.com/armansalimi-microsoft/RAG_Manual_DEMO/assets/150470041/7df60656-f4d9-4dc3-9a42-12b04d3c51f4)


## Key Terms
•	**Retrieval augmented generation (RAG)**: A technique where a large language model enhances its responses by accessing external data.
•	**Vector database**: A database that stores information as vectors, which are numerical representations enabling precise retrieval.
•	**Embeddings**: High-dimensional vector representations of text, facilitating similarity assessments between texts.
•	**Comma separated value (CSV)**: A file format that uses commas to separate individual data items.
•	**Pandas library**: A Python library for data manipulation and analysis, commonly used with CSV files.
•	**Qdrant**: A software tool for creating in-memory vector databases, which are essential for efficient text retrieval.
•	**Sentence transformers**: Tools that convert sentences into embeddings, allowing comparison through metrics like cosine similarity.
•	**Cosine distance**: A metric used to measure the similarity between two vectors within a multi-dimensional space.


## Setup your environment
Before beginning the steps outlined in this manual, please ensure you have access to the necessary files and scripts. You can do this by either forking or downloading the repository. This will provide you with all the resources required to follow the interactive Jupyter Notebook and successfully implement your RAG system.

**Install the dependencies**
To set up your development environment using Conda, follow these steps to create a Conda environment and install the necessary libraries:

```
conda create -n rag_env python=3.9
conda activate rag_env
conda install pip
pip install -r requirements.txt
```

Dependencies include:
1. [Qdrant](https://github.com/qdrant/qdrant) for the vector database. We will use an in-memory database for the examples
2. [Azure OpenAI](https://learn.microsoft.com/en-us/azure/ai-services/openai/overview) for the LLM - OpenAI API compatible key and endpoint 
3. [OpenAI's Python API](https://pypi.org/project/openai/) to connect to the LLM after retrieving the vectors response from Qdrant
4. [Sentence Transformers](https://www.sbert.net/) to create the embeddings with minimal effort

## Interactive Guide
To effectively implement the steps outlined in this manual, please use the interactive Jupyter Notebook available [here](https://github.com/armansalimi-microsoft/RAG_Manual_DEMO/blob/main/Manual%20Guide%20Notebook.ipynb). This notebook provides a hands-on approach to each step from importing your data to testing the RAG system with your own dataset. It is designed to be user-friendly, ensuring a practical and educational experience as you build and deploy a Retrieval Augmented Generation system.

#### Step 1: Import your data
The data will be used to create the embeddings for the vector database later and you will need to format it as a list of dictionaries.Prepare your dataset by formatting it as a list of dictionaries, which will later facilitate the creation of embeddings for the vector database. To ensure that the procesess is lightening fast, I have listed the top 150 records of the full dataset.

Full Dataset: [Kaggle Myntra Fashion Products](https://www.kaggle.com/datasets/nirokey/myntra-fashion-products)
Top 150 Dataset: [150 Kaggle Myntra Fashon Products](https://github.com/armansalimi-microsoft/RAG_Manual_DEMO/blob/main/Demo_fashion_products.csv)

#### Step 2: Create embeddings
Generate embeddings using Sentence Transformers, and verify their storage and search functionality within the Qdrant database.

#### Step 3: Implement RAG with LLM and Qdrant
Leverage the OpenAI API to integrate your data with the LLM, creating a dynamic RAG system based on your specific datase

#### Step 4: Test
Ensure the system accurately retrieves data and generates responses by conducting thorough tests.
