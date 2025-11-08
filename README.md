### Enron Email & Stock Analysis Chatbot (Project "Enrique")

This project is an AI-powered chatbot designed to analyze and provide insights from the Enron email dataset. It specifically focuses on the communications of Kenneth Lay (the CEO and founder of Enron) and analyzes email activity and Enron's stock performance data.

The chatbot, named "Enrique," uses a Large Language Model (LLM) hosted on Amazon Bedrock to understand natural language questions, query a vector database, and provide conversational, context-aware answers.

Key Features

    Natural Language Queries: Ask complex questions in plain English (e.g., "Who was Kenneth Lay friendly with?").

    Email Analysis: Find out who emailed whom, what topics were discussed, and identify relationships and communication patterns.

    Stock Performance Integration: Correlate email dates with Enron's stock performance, asking questions about prices, highs, lows, and trading volume.

    Conversational Memory: The chatbot remembers the context of your conversation for follow-up questions.

    RAG Architecture: Implements a Retrieval-Augmented Generation (RAG) pipeline using ChromaDB to ground the LLM's answers in factual data from the emails and stock CSVs.

Tech Stack

    Python: The core programming language.

    LangChain: The main framework for orchestrating the RAG pipeline, managing prompts, and connecting components.

    Amazon Bedrock: The cloud service used to host and access the foundation model.

    Meta Llama 3.1 70B Instruct: The specific LLM used for its powerful reasoning and instruction-following capabilities.

    ChromaDB: The open-source vector database used to store and retrieve email and stock data embeddings.

    Pandas & NumPy: Used for data loading, cleaning, and preprocessing of the stock data.

    Jupyter Notebook: For development, experimentation, and demonstration.


# Configure AWS Credentials

This project requires AWS credentials to access Amazon Bedrock. The safest way to configure this is using the AWS CLI:

aws configure


This command will prompt you for your:

AWS Access Key ID

AWS Secret Access Key

Default region name (e.g., us-east-1)

Default output format (you can leave this as json)

This securely stores your credentials for the project to use.

# To Prepare and Ingest Data

Download the Data:

Download the Enron Email Dataset (e.g., from Kaggle or the official dataset page).

Download the Enron Stock Price Data (ENRN.csv) (e.g., from Yahoo Finance).

Place the data in a data/ directory within this project.

Run the Ingestion Script:
You must first process the raw data and store it in the ChromaDB vector store.

python ingest_data.py


(Note: This script will need to be created. It should load the emails and stock data, chunk them, create embeddings, and save them to a persistent ChromaDB database.)

Usage

Once setup is complete, you can interact with the chatbot by running the EnronEmailProject.ipynb Jupyter Notebook.

Launch Jupyter:

jupyter notebook


Open the notebook and run the cells. You can ask questions using the ask_question() function defined in the notebook.

Example Questions

Here are a few examples of questions you can ask Enrique:

# Example from the notebook
ask_question("Who did Kenneth Lay email the most?")


# Example from the notebook
ask_question("Who did Kenneth Lee seem friendly with?")


# More examples
ask_question("What was the overall performance of Enron's stock price in November 2000?")
ask_question("Were there any emails that directly or indirectly showed signs of illegal activity?")
ask_question("Who are you?")
