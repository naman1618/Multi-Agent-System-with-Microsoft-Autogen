# Multi Agent Autogen RAG Architecture

This project implements a Retrieval-Augmented Generation (RAG) architecture using OpenAI's language models and Chroma vector store for document retrieval. It provides a chatbot interface for interacting with the system and also demonstrates the use of the AutoGen library for creating intelligent agents.

## Features

- Downloads and processes PDF documents.
- Extracts text from PDFs and splits it into manageable chunks.
- Generates embeddings using OpenAI embeddings.
- Stores and retrieves documents using Chroma vector store.
- Integrates with AutoGen to create and manage multiple agents.
- Provides conversational retrieval using OpenAI's language models.

## Requirements

- Python 3.7+
- PyPDF2
- Langchain
- Chroma
- OpenAI Embeddings
- AutoGen
- ChromaDB
- JSON

## Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/UA-AICore/aicore-rag-architecture-.git
    cd aicore-rag-architecture-
    ```

2. Install the required packages:

    ```sh
    pip install -r requirements.txt
    ```

3. Set up your environment variables:

    ```sh
    export OPENAI_API_KEY='your-openai-api-key'
    ```

## Usage

1. Ensure you have your configuration JSON file set up correctly.

2. Run the application:

    ```sh
    python app.py
    ```

3. Access the chatbot interface through the provided link.

## Project Structure

- `app.py`: Main application file that sets up the chatbot and integrates various components.
- `requirements.txt`: List of required Python packages.
- `OAI_CONFIG_LIST`: JSON file containing configuration for the OpenAI models.

## Functions

### `config_list_from_json(file_path, filter_dict)`

Loads and filters configuration list from a JSON file.

### `answer_resume_question(question)`

Answers resume-related questions using the ConversationalRetrievalChain.

### `norag_chat()`

Initiates a non-RAG chat session with predefined agents.

### `rag_chat()`

Initiates a RAG chat session with retrieval-augmented agents.

### `function_calling_rag_chat()`

Initiates a RAG chat session with function-calling capability.

## License

This project is licensed under the MIT License.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss changes.

## Acknowledgements

- [OpenAI](https://openai.com/)
- [Langchain](https://langchain.com/)
- [Chroma](https://chroma.com/)
- [AutoGen](https://autogen.com/)
