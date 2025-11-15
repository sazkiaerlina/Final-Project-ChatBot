# 🧑‍🍳ChefBot-Indonesia
A chatbot designed to help you find recipes based on ingredients, discover Indonesian dishes, and get clear step-by-step cooking guidance.

#  Project Overview
ChefBot Indonesia is an intelligent Indonesian recipe-search chatbot built using Retrieval-Augmented Generation (RAG), web search, and a powerful LLM (Groq LLaMA 3.3-70B Versatile).
Its purpose is to provide accurate, verified, and easy-to-follow cooking answers—whether users want to find dishes based on ingredients, explore authentic Indonesian recipes, or receive step-by-step cooking instruction

ChefBot Indonesia integrates three technologies working together:
1. Local Recipe Knowledge Base (Embedding + FAISS)
   All Indonesian recipes in the dataset are converted into numerical embeddings usingHuggingFace “intfloat/multilingual-e5-base”.
   These embeddings are stored and indexed using FAISS, which serves as the retrieval backbone for accurate, data-grounded answers.
2. Web Search Layer (Serper API)
   When the answer requires recent or external information, ChefBot accesses the internet through Serper Web Search.
   This ensures responses are fresh, verifiable, and not limited to the local dataset.
3. Large Language Model (Groq LLaMA 3.3-70B Versatile)
   The LLM plays a central role in interpreting user queries and generating high-quality responses.

# Design Choice
1. Multilingual Embeddings — intfloat/multilingual-e5-base
   - Works very well for Indonesian language.
   - Excellent for semantic search (ideal for ingredient-based retrieval).
   - Lightweight and fast enough for Google Colab.
   - Strong performance across multilingual datasets.

2. LLM Generation — Groq LLaMA 3.3 70B Versatile
   - Extremely fast inference on Groq hardware.
   - Strong reasoning and multilingual understanding.
   - Produces coherent, detail-rich cooking instructions.

3. Retrieval-Augmented Generation (RAG)
   - Keeps answers grounded in real recipe data.
   - Reduces hallucinations.
   - Enables ingredient-based and semantic recipe search.

4. Web Search (Serper API)
   - Fast, affordable, and simple to use.
   - Retrieves relevant Indonesian cooking info.
   - Complements the dataset when certain recipes are missing.
     
5. CrewAI for Workflow Orchestration

   CrewAI simplifies the workflow:
   query → retrieve → optional web search → generate final answer.

6. Langchain Integration

   LangChain offers consistent abstractions for managing the core components of the system, such as embeddings, vector stores (FAISS), prompts, and retrievers, thus simplifying the integration between the large language model (LLM), the vector database, and web search tools. 
   
7. Google Colab as the Development Platform
   
   Google Colab environment provides a free GPU which is crucial for accelerating recipe data embedding, as well as fast LLM inference and retrieval from FAISS, enabling rapid prototyping. Colab also guarantees ease of running, sharing, and reproducing this project, as it eliminates the need for users to perform complex local setup and ensures all dependencies are available in a uniform cloud environment.

# Dataset
- URL: https://www.kaggle.com/datasets/canggih/indonesian-food-recipes
- This dataset provides 14,000 recipes divided into 7 categories based on the main ingredients (chicken, goat, beef, egg, tofu, fish, and tempe).

# Steps to run
1. Clone the Repository
2. Open the Project in Google Colab
3. Install Requirements
4. Set Up API Keys 
5. Load and Prepare the Recipe Dataset
6. Build or Load FAISS Vector Store
7. LLM & Tools Setup
8. Agent Definition
9. Start the chatbot




