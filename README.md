# Document RAG QA Service

A learning project for document ingestion, vector retrieval, and source-grounded answers.

> Status: initial scaffold. Retrieval, embeddings, and model integration are not implemented yet.

## Planned scope

- PDF, Markdown, and TXT ingestion
- Configurable token chunking with source metadata
- PostgreSQL and pgvector storage
- Per-user retrieval filtering
- Top-k retrieval, similarity threshold, and source citations
- Evaluation set for retrieval and unsupported-answer handling

## Upstream reference

The RAG workflow is studied from [langgenius/dify](https://github.com/langgenius/dify). No Dify source code has been copied into this scaffold. Check the upstream license before reusing any implementation.

## Run locally

```bash
python -m venv .venv
pip install -e ".[dev]"
uvicorn app.main:app --reload
pytest
```

Open <http://127.0.0.1:8000/docs> after startup.

## Docker

```bash
docker build -t document-rag-qa-service .
docker run --rm -p 8000:8000 document-rag-qa-service
```

## Roadmap

1. Add document upload and parsing.
2. Add chunking and metadata persistence.
3. Add pgvector retrieval.
4. Add answer generation, citations, and evaluation.
