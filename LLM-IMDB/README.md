🎥 IMDb Movie Finder (LLM + LangChain + FastAPI)
Welcome to the IMDb Movie Finder! This application allows you to query movies using natural language, leveraging the power of Large Language Models (LLMs) and semantic search.

✨ Features
Natural Language Queries: Ask for movies using everyday language.

Intelligent Filtering: Supports filtering by year, genre, and actors.

Semantic Search: Powered by LangChain and ChromaDB for highly relevant results.

Conversational Memory: The AI remembers previous interactions for seamless follow-up questions.

🚀 Getting Started
Follow these steps to set up and run the IMDb Movie Finder on your local machine.

1. 🐍 Python Environment Setup (Crucial!)

It's essential to use a compatible Python version (like 3.11) for all the AI/ML libraries.

Deactivate any active Conda environment:

<!-- conda deactivate -->
conda deactivate

Check existing environments:

<!-- conda info --envs -->
conda info --envs

If llm-imdb-py311 exists: Proceed to activate it.

If llm-imdb-py311 does NOT exist: Create it first:

<!-- conda create -n llm-imdb-py311 python=3.11 -y -->
conda create -n llm-imdb-py311 python=3.11 -y

Activate the environment:

<!-- conda activate llm-imdb-py311 -->
conda activate llm-imdb-py311

✅ Verify Python Version:

<!-- python --version -->
python --version

Expected Output: Python 3.11.x

⚠️ Important: If you see anything other than 3.11.x (e.g., 3.13.x), STOP and re-do the environment creation steps. This is the most common source of installation issues for torch and related libraries.

2. ⚙️ Backend Setup (FastAPI)

The backend handles the LLM processing and movie data retrieval.

Navigate to the backend folder:

<!-- cd /Users/surya.prakash1/Downloads/testing 2/LLM-IMDB/backend -->
cd /Users/surya.prakash1/Downloads/testing 2/LLM-IMDB/backend

Install Python dependencies:

<!-- pip install -r requirements.txt -->
pip install -r requirements.txt

Troubleshooting torch installation: If you encounter errors related to torch (e.g., No matching distribution found), try installing it specifically for CPU:

<!-- pip install torch==2.2.2 --index-url https://download.pytorch.org/whl/cpu -->
pip install torch==2.2.2 --index-url https://download.pytorch.org/whl/cpu

Then, you might need to re-run pip install -r requirements.txt or manually install other missing packages (e.g., pip install sentence-transformers chromadb langchain-openai langchain-chroma).

Build the Vector Store (Important!):
This step processes your movie data and creates the searchable database.

<!-- python vector_store.py -->
python vector_store.py

Note: This might take some time depending on the size of your dataset.

🚀 Start the Backend Server:

<!-- uvicorn main:app --reload --port 8000 -->
uvicorn main:app --reload --port 8000

Keep this terminal window open. The server needs to be running for the frontend to work.

3. 🖥️ Frontend Setup (React)

The frontend provides the user interface for interacting with the movie finder.

Open a new terminal tab/window.
(Keep the backend server running in the first terminal.)

Navigate to the frontend folder:

<!-- cd /Users/surya.prakash1/Downloads/testing 2/LLM-IMDB/imdb-frontend -->
cd /Users/surya.prakash1/Downloads/testing 2/LLM-IMDB/imdb-frontend

Install Node.js dependencies:

<!-- npm install -->
npm install

Note: You only need to run this once, or if your package.json changes.

🚀 Start the React App:

<!-- npm start -->
npm start

This will usually open your web browser to http://localhost:3000.

🎬 Test the Application
Once both the backend and frontend servers are running:

Open your web browser and go to: http://localhost:3000

Try out some queries!

Example Queries:

🎭 By Genre:

"Show me some comedy movies"

"Find thriller films"

"List top romantic movies"

👤 By Actor / Star:

"Movies with Leonardo DiCaprio"

"Show films starring Natalie Portman"

🧠 By Plot/Theme:

"Time travel science fiction movies"

"Movies about survival in space"

"Psychological thrillers with a twist ending"

🗓️ By Year:

"Movies released in 2019"

"Films from 1994"

🔁 Combination Filters:

"Romantic dramas with Tom Hanks"

"Best action thrillers with Keanu Reeves"

🛠️ Technologies Used
FastAPI: High-performance web framework for the backend API.

LangChain: Framework for developing applications powered by language models.

OpenAI: Provides the GPT model for natural language understanding and generation.

ChromaDB: An open-source embedding database for storing and querying movie data.

React: A JavaScript library for building the user interface.


Uvicorn: ASGI server to run the FastAPI application.

Node.js / npm: JavaScript runtime and package manager for the frontend.

PyTorch: Underlying deep learning library used by embedding models (e.g., sentence-transformers).

<img width="1420" height="784" alt="recommendation" src="https://github.com/user-attachments/assets/88db25ed-c2ec-421e-912c-89b56b945dcf" />
