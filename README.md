# ai-schema-pilot

ai-schema-pilot is a schema-aware natural language to SQL generation system. It uses embedding-based schema selection to identify the most relevant tables and columns from a database schema, improving the accuracy and relevance of SQL queries generated from natural language input.

This system is designed to work seamlessly with large language models such as ChatGPT or Ollama, providing them with focused schema context to reduce hallucinations and improve query precision.

## Overview

1. Accepts a natural language query, for example:  
   "Show me the total sales per product last month."

2. Selects the most relevant tables from a large database schema by embedding the query and schema elements using sentence-transformers and ranking via cosine similarity.

3. Constructs a schema-aware prompt containing only the relevant schema details, reducing noise and improving the quality of generated SQL.

4. Generates the final SQL query by invoking an LLM such as ChatGPT or Ollama.

## Project Structure

```
ai-schema-pilot/
├── schema/
│ ├── schema.sql # Source schema in SQL format
│ └── schema.json # Parsed schema metadata with tables, columns, and types
├── scripts/
│ ├── parse_sql_schema.py # Script to convert .sql schema to structured JSON
│ └── schema_selector.py # Embedding-based schema selector
├── examples/
│ └── queries.txt # Sample natural language queries
├── generate_sql.py # Integration script with Ollama or OpenAI API
├── README.md
├── requirements.txt```
