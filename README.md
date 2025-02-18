# LangChain RAG

## Basic RAG Steps
* create folder for PDFs in project root 'pdfs'
* Copy .pdf files to the 'pdfs' dir
* .env.example -> .env
* Set OpenAI API Key
* (Optional) Enable LangSmith Tracing
* (Optional) Set LangSmith API Key
* Create python venv (if there is no python env)
* Run through the Jupyter Notebook - simple_faiss_rag.ipynb

## Using Chains

In the simple_faiss_rag, we represented the user input, 
retrieved context, and generated answer as separate keys in the state. 
Conversational experiences can be naturally represented using a sequence of messages. 
In addition to messages from the user and assistant, retrieved documents and other artifacts can be incorporated 
into a message sequence via tool messages. This motivates us to represent the state of our RAG application using 
a sequence of messages. 

Specifically, we will have

1. User input as a HumanMessage;
2. Vector store query as an AIMessage with tool calls;
3. Retrieved documents as a ToolMessage;
4. Final response as a AIMessage.

Detailed Documentation: https://python.langchain.com/docs/tutorials/qa_chat_history/

## Using Agents

Agents leverage the reasoning capabilities of LLMs to make decisions during execution. 
Using agents allows you to offload additional discretion over the retrieval process. 
Although their behavior is less predictable than the above "chain", 
they are able to execute multiple retrieval steps in service of a query, or iterate on a single search.

Detailed Documentation: https://python.langchain.com/docs/tutorials/qa_chat_history/#agents
