# Insurance Documents QA Chatbot (RAG & LangChain)

A Question-Answering (QA) Chatbot designed to efficiently answer queries based on a corpus of insurance documents using the Retrieval-Augmented Generation (RAG) framework, powered by the LangChain library.

## 🌟 Overview

This project implements a sophisticated chatbot that can ingest various insurance documents (e.g., policies, terms and conditions) and allow users to ask specific questions about the content. Unlike standard language models, this RAG system ensures that answers are accurate, grounded, and directly traceable back to the source documents, making it ideal for high-stakes domains like insurance.

## ✨ Features

  * **Document Ingestion:** Easily load and process multiple insurance documents (PDFs, TXT, etc.).
  * **Retrieval-Augmented Generation (RAG):** Uses a Vector Store to retrieve the most relevant document chunks to inform the Large Language Model (LLM), preventing hallucinations and ensuring factual accuracy.
  * **Contextual Q\&A:** Provides precise answers to complex policy questions based solely on the loaded insurance knowledge base.
  * **LangChain Integration:** Leverages LangChain's modular components for efficient document loading, splitting, vectorization, and chaining the retrieval and generation steps.

## 🛠️ Technologies & Libraries

  * **Framework:** [LangChain](https://www.langchain.com/)
  * **Language Model (LLM):** (e.g., OpenAI, Hugging Face/Llama, or a local model)
  * **Embedding Model:** (e.g., HuggingFaceEmbeddings, OpenAI Embeddings)
  * **Vector Store:** (e.g., FAISS, ChromaDB, Pinecone)
  * **Programming Language:** Python
  * **Document Loaders:** `PyPDFLoader`, `DirectoryLoader` (or similar)

## 🚀 Getting Started

### Prerequisites

1.  Python 3.8+
2.  A valid API Key for the chosen LLM (if applicable).

### Installation

1.  **Clone the repository:**

    ```
    git clone https://github.com/amaan2398/Insurance_Documents_QA_Chatbot_RAG_LangChain.git
    cd Insurance_Documents_QA_Chatbot_RAG_LangChain
    ```

2.  **Create and activate a virtual environment (recommended):**

    ```
    python -m venv venv
    source venv/bin/activate  # On Linux/Mac
    ```

     ```
    python -m venv venv
    .\venv\Scripts\activate   # On Windows
    ```

3.  **Install dependencies:**
    *(Note: You may need to modify the requirements based on the specific LLM/Vector Store used in the notebook.)*

    ```
    pip install -r requirements.txt
    ```

4.  **Set Environment Variables:**
    Create a file named `.env` in the root directory and add your keys:

    ```
    OPENAI_API_KEY="your_openai_key_here"
    # Or other relevant keys (e.g., HUGGINGFACEHUB_API_TOKEN)
    ```

### Usage

1.  **Place Documents:** Put all your `.pdf` or `.txt` insurance documents into a dedicated directory (e.g., `data/`).

2.  **Run the Notebook:** Execute the steps in the provided Jupyter Notebook to process the documents and initialize the QA chain.

    ```
    jupyter notebook langchain_notebook.ipynb
    ```

3.  **Start Chatting:** Follow the final cells of the notebook to input your questions and receive answers based on the insurance documentation.

## 📓 Jupyter Notebook

The entire workflow, from document loading and processing to setting up the RAG chain and running the QA test cases, is detailed in the following notebook:

  * **My Notebook:** [`langchain_notebook.ipynb`](https://github.com/amaan2398/Insurance_Documents_QA_Chatbot_RAG_LangChain/blob/main/langchain_notebook.ipynb\)
