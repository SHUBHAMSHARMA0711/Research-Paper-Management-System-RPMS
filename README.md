# Research Paper Management System (RPMS)

## Overview
The **Research Paper Management System (RPMS)** is designed to provide users with a comprehensive platform to search, discover, and access research papers across various disciplines. The system indexes papers from multiple sources, such as academic journals, conference proceedings, and institutional repositories. It simplifies the retrieval of relevant literature by integrating diverse data sources into a single, accessible platform.

## Motivation
The exponential growth of academic research has made it challenging for researchers, students, and academics to efficiently find relevant literature. RPMS addresses this issue by enabling federated querying across multiple sources, eliminating the inefficiencies of separate searches on different platforms. This system ensures faster and more accurate retrieval of relevant papers.

## Features

1. **Keyword Search**
   - Users can input keywords, titles, or author names to search for relevant research papers.

2. **Advanced Filtering**
   - Filter search results by criteria such as publication year, author, journal, citation count, and subject area, enabling precise and tailored searches.

3. **Research Metrics Analysis**
   - Evaluate the impact of papers or authors using metrics like citation counts, h-index, and journal impact factors to assess the significance of research contributions.

4. **Semantic Analysis**
   - Uses a Query Analyzer to perform semantic analysis on user queries, identifying key terms, synonyms, and relevant categories to enhance search precision.

## Stakeholders

1. **Researchers and Academics**
   - Primary users who rely on the platform to find relevant literature for research, teaching, and study purposes.

2. **Publishers and Academic Institutions**
   - Benefit from increased visibility and accessibility of their published works, contributing to broader knowledge dissemination.

3. **Students**
   - Use the platform for conducting research for assignments, theses, or dissertations.

4. **Developers**
   - Responsible for maintaining and enhancing the platform to meet user needs and incorporate technological advancements.

## Innovation
The innovative aspect of RPMS lies in its federated querying capabilities. Unlike traditional systems relying on a single source, RPMS distributes queries across multiple sources with different schemas. The system integrates fetched data to provide users with a seamless experience, displaying the most relevant research papers regardless of their storage location. This approach significantly reduces the time and effort required to locate specific academic papers and offers a holistic view of available research.

## Tech Stack

### Backend:
- **Python**: Core language for development.
- **Flask**: Framework for building the API.
- **pymongo**: Library for MongoDB integration.
- **mysql-connector-python**: Library for MySQL operations.
- **Sentence Transformers**: For semantic similarity computations.
- **fuzzywuzzy**: For fuzzy string matching.

### Frontend:
- **HTML** and **Jinja2 Templates**: For rendering the user interface.

### Databases:
- **MongoDB**: Stores data for IEEE and ResearchGate papers.
- **MySQL**: Stores data for CVPR papers.

## Key Functions

### `extract_schema(collection)`
- Extracts the schema dynamically from a MongoDB collection based on sample documents.

### `extract_mysql_schema(cursor, table_name)`
- Extracts the schema dynamically from a MySQL table.

### `compute_similarity(schema_a, schema_b)`
- Computes the semantic similarity between two schema field sets using Sentence Transformers.

### `search_documents(query, db, mapping, fuzzy=False)`
- Searches MongoDB for documents matching the query and applies schema mappings.

### `search_mysql_documents(query, cursor, table_name, mapping)`
- Searches MySQL for documents matching the query and applies schema mappings.

### `entity_matching(user_entity, db_entities)`
- Matches user query attributes with database entities using fuzzy and semantic matching.

### `search2(query)`
- Combines results from MongoDB and MySQL into a consolidated response.

## Dependencies

- Flask
- pymongo
- mysql-connector-python
- pandas
- fuzzywuzzy
- sentence-transformers
- cohere

Install all dependencies via `pip install -r requirements.txt`.
