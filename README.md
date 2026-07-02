# LLM-based Natural Language Interface to Databases

This repository presents a prototype Natural Language Interface to Databases (NLIDB) built with large language models.

The project implements an end-to-end workflow that allows users to ask questions about a relational database in natural language. The system generates SQL, explains the generated query, executes it on a SQLite database, and converts the query results into a natural-language answer.

The project focuses on the connection between database systems and AI-assisted data access, combining Text-to-SQL generation, SQL-to-Text explanation, Query Results-to-Text generation, and prompt engineering.

## Project Overview

Relational databases store structured information efficiently, but querying them usually requires knowledge of SQL. Natural Language Interfaces to Databases aim to make structured data accessible through ordinary language.

This project explores how large language models can be used to build a prototype NLIDB pipeline over databases from the Spider Text-to-SQL dataset.

The notebook demonstrates four main components:

1. Text-to-SQL generation
2. SQL-to-Text explanation
3. SQL query execution
4. Query Results-to-Text verbalization

These components are then combined into a complete end-to-end NLIDB pipeline.

## Main Pipeline

The pipeline takes as input:

- a natural-language question,
- a relational database path,
- the corresponding database schema.

It then performs the following steps:

```text
Natural-language question
        ↓
Schema-aware Text-to-SQL generation
        ↓
Generated SQL query
        ↓
SQL-to-Text explanation
        ↓
SQL execution over SQLite database
        ↓
Tabular query results
        ↓
Query Results-to-Text verbalization
        ↓
Final natural-language answer
```

## Technical Components

The notebook includes:

- loading and inspecting the Spider dataset,
- extracting database schemas from Spider metadata,
- formatting database schemas for LLM prompts,
- generating SQL queries from natural-language questions,
- cleaning generated SQL outputs,
- explaining SQL queries in natural language,
- executing SQL queries over SQLite databases,
- converting query results into markdown tables,
- generating natural-language summaries of query results,
- measuring latency across the NLIDB pipeline.

## Example Use Case

For a natural-language question such as:

```text
How many films did each director direct?
```

the system:

1. reads the relevant database schema,
2. generates a SQL query,
3. explains what the SQL query does,
4. executes the SQL query on the SQLite database,
5. converts the result table into a concise natural-language answer.

This creates a complete natural-language interaction layer over a relational database.

## Tools and Technologies

- Python
- Jupyter Notebook
- SQLite
- Pandas
- Spider dataset
- OpenAI API
- optional vLLM backend
- Large Language Models
- Prompt Engineering
- Text-to-SQL
- SQL-to-Text
- Query Results-to-Text
- Natural Language Interfaces to Databases

## Repository Structure

```text
.
├── README.md
├── llm_nlidb_text_to_sql_pipeline.ipynb
├── requirements.txt
├── .env.example
└── .gitignore
```

## Dataset

This project uses the Spider dataset, a benchmark dataset for Text-to-SQL research.

The dataset is not included in this repository because of size and licensing considerations. The notebook contains code for downloading and loading the dataset automatically.

Expected local structure after download:

```text
spider_data/
├── dev.json
├── tables.json
└── database/
```

The dataset folder and zip file should remain excluded from Git version control.

## Environment Variables

API keys and credentials should not be committed to the repository.

The OpenAI API key should be provided as an environment variable:

```python
import os

OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
```

A local `.env` file can be used during development, but it should remain excluded from Git.

Example `.gitignore` entries:

```text
.env
spider_data/
spider_data.zip
__pycache__/
.ipynb_checkpoints/
```

## Notebook Contents

The notebook is organized around the following workflow:

- environment setup,
- LLM backend preparation,
- Spider dataset loading,
- Text-to-SQL prompting,
- few-shot Text-to-SQL prompting,
- SQL-to-Text explanation,
- Data-to-Text generation,
- Query Results-to-Text generation,
- full NLIDB pipeline implementation,
- latency measurements,
- findings and limitations.

## Relevance

This project is relevant to modern AI-assisted data access systems.

It demonstrates how language models can be used to interact with structured data through natural language, while still relying on relational databases and SQL execution underneath.

The project is relevant to:

- AI engineering
- data engineering
- database systems
- LLM-based applications
- natural-language data access
- structured data analytics
- scientific and industrial data systems
- AI-ready data infrastructure

## Limitations

This is a prototype-level NLIDB system, not a production-ready database interface.

Important limitations include:

- generated SQL may be incorrect,
- the system depends strongly on schema quality,
- Text-to-SQL errors propagate to later pipeline stages,
- generated SQL is not fully validated before execution,
- the current implementation is designed for local experimentation,
- latency depends on the selected LLM backend,
- robust SQL safety checks are not yet implemented.

## Future Work

Potential extensions include:

- SQL validation before execution,
- execution-guided SQL correction,
- retrieval-augmented few-shot prompting,
- automatic schema linking,
- benchmark evaluation on Spider,
- PostgreSQL support,
- query-plan-aware SQL optimization,
- integration with database cost feedback,
- safer SQL execution sandboxing,
- comparison between OpenAI and local vLLM models,
- development of a web-based NLIDB demo.

## Attribution

Prepared for public portfolio use by:

Konstantinos Kritsotakis

This repository highlights practical skills in AI engineering, prompt engineering, database systems, and LLM-assisted interaction with structured data.
