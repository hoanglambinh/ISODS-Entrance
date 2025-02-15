# ISODS-Entrance
Vietnamese Legal Document Processing & Retrieval

This repository contains three Python notebooks for processing, embedding, and searching Vietnamese legal documents. The tasks involve web scraping, vector database creation, and semantic search using ChromaDB and LangChain.

1️. Web Scraping & Preprocessing

Description

This notebook scrapes Vietnamese legal documents from the PhapDien website and prepares them for further processing. It downloads full legal texts, extracts meaningful content, and saves them in structured directories.

Key Features

- Fetches and saves legal document pages.

- Organizes data into directories (e.g., vbpl, property, history, related, pdf).

- Ensures filenames are sanitized and properly structured.

Output

- Full document HTML files: full_ItemID.html

- PDF files and metadata

2️. Creating a Vector Database with ChromaDB

Description

This notebook processes and stores the extracted legal texts in a vector database using ChromaDB. It tokenizes and embeds the documents with the Vietnamese Bi-Encoder model, then saves them in ChromaDB for efficient retrieval.

Key Features

- Processes only full_ItemID.html files.

- Chunks text into 2000 tokens per segment with 20-token overlap.

- Generates embeddings using bkai-foundation-models/vietnamese-bi-encoder.

- Stores file paths in metadata for traceability.

- Saves the ChromaDB vector database for future retrieval.

Output

- chroma_db/ directory containing the vector database.

- Processed .pt files for embeddings.

3️. Semantic Search Using ChromaDB & LangChain

Description

This notebook performs semantic search on the stored vector database. Users can input a query, and the system retrieves the top-k most relevant legal documents using similarity search.

Key Features

- Loads ChromaDB and precomputed embeddings.

- Uses LangChain's retriever for querying.

- Returns top-k similar documents with metadata (file paths).

- Displays excerpts from matched documents.

How to Use

- Run the notebook and enter a query when prompted:

- Enter search query: " "

- Results will display the most relevant legal documents.

Observations

- Search accuracy: The relevance of results depends on how well the embeddings capture document meaning.

- Chunking strategy matters: Overlapping tokens ensure better contextual understanding.

- Fast retrieval: ChromaDB efficiently finds similar documents in seconds.

- Metadata is useful: Including file paths helps trace search results back to source files.

Output

Ranked search results with excerpts and metadata.
