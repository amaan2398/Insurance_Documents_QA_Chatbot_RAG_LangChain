# Semantic Spotter Project Submission

## 1\. Background

This project demonstrates "Build a RAG System" in the insurance domain using LangChain.

## 2\. Problem Statement

The goal of the project is to build a robust generative search system capable of effectively and accurately answering questions from a bunch of policy documents.

## 3\. Document

The policy documents can be found [here](https://github.com/amaan2398/Insurance_Documents_QA_Chatbot_RAG_LangChain/tree/main/Policy%2BDocuments).

## 4\. Approach

LangChain is an ideal framework for this project because it simplifies the development of LLM applications. It offers a suite of tools, components, and interfaces that simplify the construction of LLM-centric applications, enabling developers to build applications that can generate creative and contextually relevant content.

**Why LangChain?**

  * **Versatility and Flexibility:** Enables seamless integration with various data sources, making it a comprehensive solution for creating advanced language model-powered applications.
  * **Modularity:** Its core design principle is composition and modularity. By combining modules and components, one can quickly build complex LLM-based applications.
  * **Abstractions and Integrations:** It provides abstractions for most of the functionalities needed for building an LLM application and also has integrations that can readily read and write data, reducing the development speed of the application.
  * **Model Agnosticism:** The framework allows for building applications that are agnostic to the underlying language model, offering a unique value proposition to build applications and iterate continuously.

**LangChain Framework Components:**

1.  **Components:** Modular abstractions for the components necessary to work with language models (LLMs & Chat Models, Prompts, Output Parsers, etc.).
2.  **Use-Case Specific Chains:** Assembling components in particular ways to accomplish a specific use case, serving as a higher-level, customizable interface.

**LangChain Building Blocks:**

  * **Model I/O:** Interface with language models (LLMs & Chat Models, Prompts, Output Parsers).
  * **Retrieval:** Interface with application-specific data (Document loaders, Document transformers, Text embedding models, Vector stores, Retrievers).
  * **Chains:** Construct sequences/chains of LLM calls.
  * **Memory:** Persist application state between runs of a chain.
  * **Agents:** Let chains choose which tools to use given high-level directives.
  * **Callbacks:** Log and stream intermediate steps of any chain.

## 5\. System Layers

The system design incorporates the following LangChain components:

| Layer | Component | Description |
| :--- | :--- | :--- |
| **Reading & Processing PDF Files** | `PyPDFDirectoryLoader` | Used to read and process the PDF files from a specified directory. |
| **Document Chunking** | `RecursiveCharacterTextSplitter` | The recommended text splitter for generic text. It attempts to keep all paragraphs (and then sentences, then words) together by splitting on a list of characters (default: `["\n\n", "\n", " ", ""]`). |
| **Generating Embeddings** | `OpenAIEmbeddings` | Used to create a vector representation of text, supporting operations like similarity search. |
| **Store Embeddings** | `ChromaDB` | Used as the vector store to persist and query the embeddings, backed by LangChain `CacheBackedEmbeddings`. |
| **Retrievers** | `VectorStoreRetriever` | Provides an interface to return documents given an unstructured query, serving as the backbone for combining documents with the language model. |
| **Re-Ranking** | `HuggingFaceCrossEncoder` | Used with model `BAAI/bge-reranker-base` to re-rank the initial search results, significantly improving the relevance of retrieved documents. |
| **Chains** | RAG Chain | Combines multiple components. We are using the pulling prompt `rlm/rag-promp` from the LangChain hub to use in the RAG chain. |

## 6\. System Architecture

*(This section heading is present in the source, but the details were not included in the provided text snippet.)*

## 7\. Prerequisites

  * Python 3.7+
  * `langchain` 0.3.13
  * Please ensure that you add your OpenAI API key to the empty text file named **"OpenAI\_API\_Key.txt"** in order to access the OpenAI API.

## 8\. Running

To run the project:

1.  **Clone the GitHub repository:**
    ```bash
    $ git clone https://github.com/amaan2398/Insurance_Documents_QA_Chatbot_RAG_LangChain.git
    ```
2.  Open the notebook in Jupyter and run all cells.
