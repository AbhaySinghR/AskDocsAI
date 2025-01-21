Data Chat with LangChain

This project demonstrates a retrieval-augmented generation (RAG) workflow using LangChain and a Large Language Model (LLM). The goal is to build a chatbot capable of answering questions from a set of documents by leveraging embeddings and a vector database for efficient retrieval.

🛠️ Architecture Overview

The system is divided into the following stages:

Document Loading
Documents (e.g., PDFs, databases, or URLs) are loaded into the pipeline.
Splitting
The documents are split into smaller, manageable chunks for processing using a text splitter.
Storage
The document chunks are stored in a vector database (vectorstore) after being converted to embeddings.
Retrieval
When a user asks a question, the system retrieves the most relevant document chunks using similarity search.
Output
The retrieved chunks are passed as context to the LLM, which generates a response to the user's query.
🔑 Key Components

LLM
Model: Llama 3.3 70B
Provider: Groq
Purpose: Processes the context and generates answers.
Embeddings
Model: BERT
(sentence-transformers/bert-base-nli-mean-tokens)
Purpose: Encodes document chunks into vector representations for similarity search.
Vectorstore
Purpose: Stores embeddings and retrieves relevant chunks during query time.
✨ Features

Conversational Memory
Maintains chat history using LangChain's ConversationBufferMemory to ensure context is preserved across interactions.
Custom Retrieval Logic
Combines the power of the BERT embedding model with Llama for precise and accurate responses.
🚀 Usage

1. Document Loading
Load documents (e.g., PDFs or database entries) into the pipeline.

2. Splitting
Use a recursive text splitter to divide documents into smaller parts for embedding and storage.

3. Embedding Generation
Convert document chunks into vector embeddings using the BERT model.

4. Question-Answering
Query the chatbot, which retrieves relevant chunks and passes them to the Llama 3.3 70B model for generating answers.

🔍 Example Query

Input Question:
"Is there any mention of MATLAB?"
Processing:
Retrieves relevant document chunks containing contact information.
Generates an answer using the Llama model.
Output:
"Yes, there is a mention of MATLAB. The instructor, Andrew Ng, mentions that the student said it was MATLAB that was so helpful, and he also mentions that they will have a short MATLAB tutorial in one of the discussion sections for those who don't know it. Additionally, he mentions that the programming in the class will be mostly in either MATLAB or Octave."

📥 Installation

Import this Notebook
Download and open the provided notebook in your Python environment (e.g., Jupyter Notebook, Google Colab).
Install Required Dependencies
Run the following command in your environment to install the necessary libraries:
pip install langchain sentence-transformers groq
Import PDF and Add File Path
Update the file path to your PDF document in the command below:
loader = PyPDFLoader("/content/MachineLearning-Lecture01.pdf")
pages = loader.load()
Follow the Flow
Execute the commands below in the same order as outlined in the notebook:
Load Document: Load the PDF or document.
Create Chunks: Use a text splitter to divide the document into manageable parts.
Generate Embeddings: Convert document chunks into vector embeddings.
Save in Vector DB: Store the embeddings in a vector database.
Chat with LLM: Interact with the chatbot using the LLM and retrieval system.
Adjust Accordingly
You can replace the embedding model (e.g., use sentence-transformers/all-MiniLM-L6-v2) or the LLM (e.g., different LLaMA versions), but the workflow remains the same.


