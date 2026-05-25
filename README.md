# Database Systems: Query Optimization & NLIDB

This repository contains MSc coursework labs in Database Systems, focusing on PostgreSQL query optimization, execution plan analysis, and LLM-based Natural Language Interfaces to Databases (NLIDBs).

The work demonstrates practical skills in relational databases, SQL query formulation, execution plan interpretation, join-order optimization, and the use of language models for database interaction tasks such as Text-to-SQL, SQL-to-Text, and Data-to-Text.

## Project Overview

The repository includes two main labs:

### Lab 1: PostgreSQL Query Optimization and Execution Plan Analysis

This lab focuses on SQL query analysis and optimization using PostgreSQL execution plans.

The work includes:

- Reconstruction of an SQL query from a given query execution plan
- Interpretation of PostgreSQL physical query plans
- Analysis of joins, filters, indexes, scans, and aggregation operators
- Manual join-order optimization
- Use of `join_collapse_limit` to force PostgreSQL to respect written join order
- Comparison of execution plans before and after optimization
- Performance evaluation using execution time and buffer statistics

The optimized query starts from the most selective predicate and delays joins that multiply intermediate rows. This substantially reduces execution time and shared buffer usage while preserving the same query result.

### Lab 2: Natural Language Interfaces to Databases

This lab focuses on Natural Language Interfaces to Databases using large language models.

The work includes:

- Text-to-SQL prompting
- SQL-to-Text generation
- Data-to-Text generation
- End-to-end natural-language database querying workflow
- Prompt design for database interaction
- Use of structured database schemas and query examples
- Evaluation of generated SQL and natural-language explanations

This lab connects database systems with modern AI-based interfaces, showing how language models can help users interact with structured data through natural language.

## Repository Structure

```text
.
├── query_optimization/
│   └── Database_Query_Optimization_Report.pdf
│
├── nlidb_llm_text_to_sql/
│   └── NLIDB_Text_to_SQL_Lab.ipynb
│
├── README.md
└── .gitignore
```

## Included Files

- `Database_Query_Optimization_Report.pdf`: Report documenting SQL reconstruction from an execution plan, PostgreSQL query optimization, join-order analysis, and before/after execution plans.
- `NLIDB_Text_to_SQL_Lab.ipynb`: Jupyter notebook implementing Natural Language Interface to Database tasks, including Text-to-SQL, SQL-to-Text, and Data-to-Text workflows.

## Tools and Technologies

- PostgreSQL
- SQL
- Query execution plans
- Join-order optimization
- Index scans
- Sequential scans
- Hash joins
- Nested-loop joins
- Aggregation
- JSON execution plans
- Jupyter Notebook
- Python
- Large Language Models
- Text-to-SQL
- SQL-to-Text
- Data-to-Text
- Natural Language Interfaces to Databases

## Relevance

This repository demonstrates practical database systems skills relevant to:

- Data engineering
- AI-ready data infrastructure
- Scientific databases
- Query optimization
- Database performance analysis
- Natural-language data access
- LLM-assisted database querying
- Structured data systems for industrial and scientific applications

The combination of classical database optimization and AI-based natural language querying is relevant to modern data-intensive environments where users need efficient, interpretable, and accessible access to structured information.

## Notes

Sensitive information such as API keys, tokens, credentials, local database passwords, and environment files are intentionally excluded from this repository.

Large databases, local database dumps, temporary files, cache folders, and system-generated files are not included.

To run the notebook, users should configure their own environment variables locally, for example:

```python
import os

OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
```

Do not hard-code API keys or credentials directly into notebooks or source files.
