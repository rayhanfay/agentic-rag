# Agentic RAG System

A Python-based document processing and question-answering system that combines document analysis with Large Language Models (LLMs) using Retrieval-Augmented Generation (RAG).

## Features

- Document processing for PDF, DOCX, and TXT files
- Text extraction with layout preservation
- Image and table extraction from PDFs
- Vector-based document retrieval
- LLM-powered question answering
- Document summarization capabilities

## Prerequisites

- Python 3.12+
- Ollama for local LLM support
- Required Python packages (see Requirements section)

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd agentic-rag
```

2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

3. Install and run Ollama (if not already installed):

```bash
# Follow instructions at https://ollama.ai/download
```

## Project Structure

```
.
├── data/                  # Directory for input documents
├── utils/
│   └── document_processor.py    # Document processing utilities
├── Agentic_RAG.ipynb     # Main Jupyter notebook
└── requirements.txt      # Project dependencies
```

## Core Components

### Document Processor

The `DocumentProcessor` class handles various document formats and provides:

- Text extraction with layout preservation
- Image extraction from PDFs
- Table extraction using Camelot or basic PyPDF2
- Support for multiple file formats (PDF, DOCX, TXT)

### RAG System

The system implements:

- Document chunking and embedding
- Vector-based retrieval using FAISS
- Integration with Ollama LLM
- Multiple agent tools for different query types

## Usage

1. Place your documents in the `data/` directory.

2. Run the Jupyter notebook:

```bash
jupyter notebook Agentic_RAG.ipynb
```

3. The system provides three main tools:
   - `retrieval_qa`: Answer questions based on document content
   - `summarize_document`: Generate summary for a specific document
   - `summarize_all_documents`: Summarize all available documents

## Example Usage

```python
# Initialize the system
docs = DocumentProcessor()
# ... (initialization code from notebook)

# Ask questions about your documents
response = agent.invoke({
    "input": "Summarize all documents about mental health."
})
```

## Requirements

Key dependencies:

- camelot-py==1.0.0
- docx2txt==0.8
- langchain-ollama==0.2.2
- ollama==0.4.7
- pandas==2.2.3
- PyMuPDF==1.25.2
- PyPDF2==3.0.1
- python-dotenv

## Features in Detail

### Document Processing

- PDF processing with layout preservation
- Image extraction with base64 encoding
- Table extraction using Camelot (when available) or basic PyPDF2
- Support for different document formats

### RAG Implementation

- Text chunking with RecursiveCharacterTextSplitter
- Vector embeddings using HuggingFace's sentence-transformers
- FAISS vector store for efficient retrieval
- Integration with Ollama LLM for generation

### Agent Tools

- Question answering with source attribution
- Document summarization (single and batch)
- Context-aware responses using RAG

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
