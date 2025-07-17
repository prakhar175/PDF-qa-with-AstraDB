# AI PDF QA with AstraDB(Cassandra)

This project demonstrates how to build a simple Question Answering (QA) system over the contents of a PDF file using modern open-source AI tools, vector databases, and local language models. The solution extracts, embeds, stores, and queries PDF text using LangChain, HuggingFace embeddings, Groq LLMs, and an AstraDB vector store powered by Cassandra.

## Features

- **PDF Parsing:** Extracts text from a given PDF file.
- **Text Chunking:** Splits PDF text into manageable chunks for embedding.
- **Vector Storage:** Stores vector embeddings in a Cassandra-powered AstraDB instance.
- **Semantic Search \& QA:** Runs similarity search and retrieves answers using local LLMs.
- **Interactive QA Console:** Enables user to ask questions about the PDF content.


## Getting Started

### Prerequisites

- Python 3.10+
- An [AstraDB](https://astra.datastax.com/) account and API credentials
- [Groq API keys](https://console.groq.com/) for LLM access
- [HuggingFace Transformers](https://huggingface.co/transformers/) and embeddings
- Required Python libraries (see below)


### Installation

1. **Clone the Repository**

```bash
git clone https://github.com/prakhar175/PDF-qa-with-AstraDB.git
cd PDF-qa-with-AstraDB
```

2. **Install Dependencies**

```bash
pip install -r requirements.txt
```

3. **Environment Variables**

Create a `.env` file in the root directory with:
-Get your own keys
```
ASTRA_DB_APPLICATION_TOKEN=your_astra_db_app_token
ASTRA_DB_ID=your_astra_db_id
GROQ_API=your_groq_api_key
```


## Usage

1. **Prepare Your PDF**
    - Place the PDF you want to query (e.g., `Artificial_intelligence.pdf`) in the working directory.
2. **Run the Notebook**
    - Open and execute the Jupyter notebook (`code.ipynb`).
    - The notebook will:
        - Extract text from your PDF.
        - Split and embed the text chunks.
        - Store them in AstraDB.
        - Let you query the content interactively.
3. **Interactive QA**

When prompted, type your question about the PDF. The system will return relevant answers

Type `exit` to end the QA session.

## Code Structure

| Section | Description |
| :-- | :-- |
| Imports \& Setup | Loads all dependencies and API keys from `.env` file |
| PDF Reading \& Text Extraction | Uses `PyPDF2` to extract raw text from the PDF |
| Text Splitting | Chunks the extracted text for efficient embedding |
| Embedding \& Vector Storage | Embeds chunks with HuggingFace, stores in AstraDB vector table |
| LLM \& Query Engine | Configures the Groq model, wraps the store, allows semantic QA |
| Interactive Console | Prompts user for questions, returns answers along with relevant context |



