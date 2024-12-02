
# Smart Article Retrieval System with Cohere and Weaviate

## Overview
This project demonstrates a semantic search and retrieval system that leverages Cohere's NLP capabilities and Weaviate's vector database. The system stores unstructured article data, performs semantic searches, and ranks results for relevance.

## Features
- **Semantic Search**: Understands natural language queries to find relevant articles.
- **Vector Database**: Uses Weaviate for efficient storage and retrieval of vectorized content.
- **Hybrid Query**: Combines semantic and lexical relevance for accurate results.
- **Re-ranking**: Uses Cohere to enhance search result rankings.

---

## Prerequisites
- Python 3.8 or higher
- API keys for:
  - [Cohere](https://cohere.ai/)
  - [Weaviate](https://weaviate.io/)
- Dependencies (see below)

---

## Setup and Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Environment Variables**
   - Create a `.env` file in the root directory:
     ```dotenv
     COHERE_API_KEY=your-cohere-api-key
     WEAVIATE_API_KEY=your-weaviate-api-key
     WEAVIATE_API_URL=your-weaviate-url
     ```

4. **Run the Script**
   ```bash
   python main.py
   ```

---

## How It Works

1. **Environment Initialization**:
   - Loads API keys using `dotenv`.
   - Initializes Cohere and Weaviate clients.

2. **Schema Creation**:
   - Defines an `Article` class schema with properties:
     - `title`: The title of the article.
     - `text`: The content of the article.
   - Adds the schema to Weaviate.

3. **Data Ingestion**:
   - Inserts example articles into the Weaviate database.

4. **Querying**:
   - Uses a hybrid search method combining semantic vectors and lexical matching.
   - Re-ranks results with Cohere's NLP model for improved relevance.

5. **Output**:
   - Displays top-ranked articles matching the query.

---

## Example Queries

**Query**: "What is the capital of Canada?"  
**Results**:
1. Title: Ottawa: The Capital of Canada  
   Text: Ottawa is the capital city of Canada, located in the province of Ontario.

2. Title: Canada Geography  
   Text: Canada is the second-largest country in the world by land area.

---

## Dependencies
- [Cohere Python SDK](https://github.com/cohere-ai/cohere-python)
- [Weaviate Python Client](https://github.com/semi-technologies/weaviate-python-client)
- `python-dotenv`

Install dependencies with:
```bash
pip install -r requirements.txt
```

---

## Future Enhancements
- Add additional content classes for multi-domain support.
- Integrate summarization for concise article previews.
- Enable advanced reranking using custom NLP models.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---
