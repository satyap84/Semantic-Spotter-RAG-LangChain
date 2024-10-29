# Retrieval-Augmented Generation(RAG) Based Chatbot implemented using Langchain to search information in Life Insurance Document.
## Overview
This project builds a Retrieval-Augmented Generation (RAG) chatbot using LangChain to effectively answer user queries baseThis project builds a Retrieval-Augmented Generation (RAG) chatbot using LangChain to automate the process of extracting and answering questions based on life insurance policies. The system combines document processing, vector-based retrieval, caching, and generative AI to efficiently generate concise answers. LangChain simplifies the integration of these components by providing a modular framework to connect document loaders, vector databases, language models, and custom chains.

The chatbot extracts information from policy documents, stores it in ChromaDB (a vector store), and uses OpenAI’s GPT-3.5-turbo to generate answers. With LangChain’s retrieval and caching mechanisms, the system can optimize responses for both complex queries and repeated questions.

## Problem Statement
Insurance documents are long, complex, and challenging to navigate. Customers or employees seeking specific policy details (such as benefits or claims procedures) often struggle to find the relevant sections quickly. Searching through large PDFs manually is time-consuming and prone to errors, leading to frustration for both internal staff and customers.

The goal of this project is to automate the retrieval and question-answering process using RAG-based techniques. The system needs to:

- Extract relevant sections from insurance documents.
- Provide accurate and concise answers to user queries.
- Optimize response time by leveraging a caching mechanism for repeated queries.
- Use generative AI (GPT-3.5) to answer complex, context-dependent questions.
- Ensure that answers are well-cited, linking back to specific sections or pages from the source documents.

## Architecture
The following is the design of the system:

1. PDF Processing and Document Chunking:
  - Use LangChain’s PyPDFLoader to extract text from insurance policy PDFs.
  - Chunk large documents into manageable pieces to ensure relevant information is indexed correctly.
2. Embedding and Vector Store Setup:
  - Generate text embeddings using OpenAI’s text-embedding-ada-002 model.
  - Store these embeddings in a persistent Chroma vector database for efficient retrieval.
3. Retrieval and Caching:
  - Implement a retriever that searches for relevant sections based on user queries using similarity search.
  - Incorporate a cache mechanism to store frequent queries and minimize redundant computation.
4. Prompt Engineering and Response Generation:
  - Use LLMChain to connect the retrieved information with a structured prompt for GPT-3.5-turbo.
  - Ensure the generated responses are concise, informative, and cited, including references to specific policy names and pages.
5. User-Friendly Query Handling:
  - Provide clear and actionable answers to user questions (e.g., "What are the policy benefits for accidental death?").
  - Support both first-time queries and cached queries to enhance the user experience.
