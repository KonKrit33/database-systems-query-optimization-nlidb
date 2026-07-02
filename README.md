# Database Systems Engineering: Query Optimization and LLM-based NLIDB Pipeline

This repository presents a database systems engineering project focused on two complementary areas:

1. relational query optimization and execution plan analysis,
2. large-language-model-based Natural Language Interfaces to Databases (NLIDBs).

The project combines classical database systems concepts with modern AI-assisted database interaction. It demonstrates practical skills in SQL, query execution analysis, join-order optimization, prompt engineering, Text-to-SQL, SQL-to-Text, Query Results-to-Text, and end-to-end natural-language querying over structured databases.

## Project Overview

The repository is organized into two main modules.

## Module 1: PostgreSQL Query Optimization

This module focuses on relational query optimization using PostgreSQL execution plans.

The work includes:

- reconstruction of SQL queries from physical execution plans,
- interpretation of PostgreSQL query plans,
- analysis of joins, filters, scans, indexes, and aggregation operators,
- manual join-order optimization,
- comparison of execution plans before and after optimization,
- performance evaluation using execution time and buffer statistics,
- use of PostgreSQL settings such as `join_collapse_limit` to control join ordering.

The goal is to understand how query structure, predicate selectivity, join order, and physical operators affect database performance.

## Module 2: LLM-based Natural Language Interface to Databases

This module implements an LLM-based NLIDB workflow using the Spider dataset and SQLite databases.

The notebook includes:

- Text-to-SQL prompting,
- few-shot Text-to-SQL prompting,
- SQL-to-Text generation,
- Query Results-to-Text generation,
- execution of generated SQL queries,
- schema-aware prompt construction,
- conversion of query results into natural language,
- an end-to-end NLIDB pipeline.

The final pipeline takes a natural-language question and a database path as input, then performs:

1. Text-to-SQL generation,
2. SQL explanation,
3. SQL execution,
4. natural-language verbalization of the query results,
5. latency measurement for each component.

## Technical Components

The NLIDB pipeline includes the following components:

- database schema extraction from Spider metadata,
- schema formatting for prompt construction,
- SQL generation from natural language,
- SQL cleaning and post-processing,
- SQL-to-Text explanation,
- SQLite query execution,
- tabular result serialization,
- Query Results-to-Text generation,
- end-to-end orchestration,
- latency tracking.

## Tools and Technologies

- PostgreSQL
- SQL
- SQLite
- Spider dataset
- Python
- Pandas
- Jupyter Notebook
- OpenAI API
- vLLM backend option
- Large Language Models
- Text-to-SQL
- SQL-to-Text
- Query Results-to-Text
- Prompt engineering
- Query execution plans
- Join-order optimization
- Database performance analysis

## Repository Structure

```text
.
├── README.md
│
├── query_optimization/
│   └── Database_Query_Optimization_Report.pdf
│
├── nlidb_pipeline/
│   └── NLIDB_Text_to_SQL_SQL_to_Text_Data_to_Text.ipynb
│
├── .env.example
├── requirements.txt
└── .gitignore
