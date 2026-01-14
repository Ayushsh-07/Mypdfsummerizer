# 📄 PDF Summarizer

## Overview
The PDF Summarizer is a powerful web application designed to help users quickly extract the essence of long documents. By leveraging Large Language Models (LLMs) and vector search, the system generates concise, coherent summaries of any uploaded PDF file.

## Key Features
* **Automated Summarization**: Extracts and summarizes key points in 3-5 sentences.
* **Semantic Search**: Uses FAISS and HuggingFace embeddings to understand the context of the document before summarizing.
* **User-Friendly Interface**: Built with Streamlit for a clean, interactive web experience.

## Technical Architecture
The system follows a modern RAG (Retrieval-Augmented Generation) pipeline:
1.  **Text Extraction**: Parses text from uploaded PDFs using `PyPDF2`.
2.  **Chunking**: Splits text into manageable segments (1000 characters with a 200-character overlap) to preserve context.
3.  **Embedding Generation**: Converts text chunks into vector representations using the `all-MiniLM-L6-v2` model.
4.  **Vector Storage**: Stores embeddings in a local `FAISS` index for efficient similarity searching.
5.  **LLM Processing**: Utilizes OpenAI's `gpt-3.5-turbo-16k` to generate the final summary based on retrieved relevant text.

## Installation & Setup

### 1. Prerequisites
Ensure you have Python installed and a valid OpenAI API key.

### 2. Environment Configuration
Create or edit the `openai.env` file in the root directory and add your API key:
```bash
OPENAI_API_KEY=YOUR_OPENAI_API_KEY
