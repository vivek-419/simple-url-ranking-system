# URL Ranking System – Search Engine Simulation

A medium-complexity URL Ranking System that simulates the core components of a modern search engine, including crawling, indexing, query processing, ranking, caching, analytics, and monitoring.

This project was developed to demonstrate real-world search engine concepts such as TF-IDF ranking, inverted indexing, caching strategies, search analytics, and scalable architecture design.

---

## Project Overview

The objective of this project is to efficiently retrieve and rank URLs based on user search queries.

The system simulates how modern search engines:

- Process user queries
- Search indexed content
- Rank URLs based on relevance
- Cache frequently searched results
- Track user behavior
- Improve ranking quality through analytics

---

## System Architecture

### Search Request Flow

```text
User
 ↓
React Frontend
 ↓
Nginx Reverse Proxy
 ↓
Backend Service
 ↓
Redis Cache

Cache Hit
 └── Return Results

Cache Miss
 ↓
Query Processor
 ↓
Search Index
 ↓
Ranking Engine
 ↓
Database
 ↓
Analytics Update
 ↓
Store in Cache
 ↓
Return Results
```

### Crawling & Indexing Flow

```text
Scheduler
 ↓
Crawler Service
 ↓
Indexer Service
 ↓
Search Index
 ↓
Database
```

---

## Features

### Query Processing

- Tokenization
- Stop-word Removal
- Query Normalization
- Keyword Extraction

### Search Index

- Inverted Index Structure
- Keyword to URL Mapping
- Fast URL Retrieval

### Ranking Engine

Uses multiple ranking factors:

- TF-IDF Score
- Click Score
- Backlink Score
- Freshness Score

Final Ranking Formula:

```text
Score =
0.50 × TF-IDF
+
0.20 × Click Score
+
0.20 × Backlink Score
+
0.10 × Freshness Score
```

### Cache System

- Redis-style Cache Simulation
- Cache Hit / Miss Detection
- TTL (Time-To-Live) Support
- Reduced Query Latency

### Analytics System

Tracks:

- Search Queries
- Click Logs
- Query Frequency
- Popular URLs

### Monitoring Dashboard

Displays:

- URLs Indexed
- Cache Hits
- Cache Misses
- Cache Hit Rate
- Total Queries Processed

---

## Technologies Used

### Programming Language

- Python

### Database

- SQLite

### Data Processing

- Pandas

### Ranking & Search

- Scikit-Learn
- TF-IDF Vectorizer
- Cosine Similarity

### Visualization

- Matplotlib
- Graphviz

### Architecture Components

- React.js
- Nginx
- Redis
- PostgreSQL
- Analytics Service
- Crawler Service
- Indexer Service

---

## Database Schema

### URLs Table

| Column | Description |
|----------|-------------|
| id | URL Identifier |
| url | Website URL |
| title | Page Title |
| keywords | Search Keywords |
| category | Category |
| clicks | User Click Count |
| backlinks | Authority Score |
| freshness | Content Freshness |

### Query Logs Table

| Column | Description |
|----------|-------------|
| id | Query ID |
| query | Search Query |
| timestamp | Search Timestamp |

### Click Logs Table

| Column | Description |
|----------|-------------|
| id | Click ID |
| url | Clicked URL |
| timestamp | Click Timestamp |

### Search Index Table

| Column | Description |
|----------|-------------|
| keyword | Indexed Keyword |
| url_id | URL Reference |

---

## Simulation Components

### 1. Architecture Visualization

Visual representation of the search engine workflow using Graphviz.

### 2. Simulated Crawler

A dataset of 30 URLs across categories:

- Programming
- AI
- Cloud
- DevOps
- Web Development
- Databases
- Education

### 3. Indexer

Extracts keywords and builds the search index.

### 4. TF-IDF Engine

Converts documents into vectors and calculates relevance scores.

### 5. Query Processor

Processes user queries before searching.

### 6. Ranking Engine

Ranks URLs using relevance, popularity, authority, and freshness.

### 7. Analytics Service

Records searches and user interactions.

### 8. Monitoring Dashboard

Provides operational metrics similar to production monitoring systems.

---

## Sample Search Flow

### User Query

```text
Best Python Tutorial For Beginners
```

### Query Processing

```text
python tutorial beginners
```

### Search Index Lookup

```text
python
 ↓
URL1
URL3
URL7
```

### Ranking Engine

Calculates:

- TF-IDF Score
- Click Score
- Backlink Score
- Freshness Score

### Final Output

```text
1. Python Tutorial
2. Real Python Guide
3. Learn Python
...
```

---

## Scalability Considerations

For larger datasets and production deployment:

### Horizontal Scaling

```text
Nginx
 ↓
Backend 1
Backend 2
Backend 3
Backend 4
```

### Improvements

- Redis Clustering
- PostgreSQL Replication
- Distributed Crawlers
- Sharded Search Index
- Microservices Architecture
- Containerization with Docker
- Kubernetes Orchestration

---

## Failure Handling

### Redis Failure

- Bypass cache
- Query Ranking Engine directly
- Increased latency but system remains functional

### Database Failure

- Use replication and failover strategies
- Read replicas for scalability

### Search Index Corruption

- Rebuild index from database records

---

## CAP Theorem Considerations

Search systems typically prioritize:

```text
Availability
+
Partition Tolerance
```

over strict consistency.

Returning slightly stale search results is preferable to failing user requests.

---

## Future Enhancements

- Real-time Web Crawling
- Dynamic URL Discovery
- Search Suggestions
- Autocomplete
- Semantic Search
- NLP-based Query Understanding
- Personalized Search Results
- Distributed Search Infrastructure
- Machine Learning Ranking Models
- Real PostgreSQL Integration
- Real Redis Integration
- Docker Deployment
- Kubernetes Deployment

---

## Project Structure

```text
URL-Ranking-System/
│
├── URL_Ranking_System_V2_Interview_Ready.ipynb
├── README.md
├── architecture/
│   └── architecture-diagram.png
├── screenshots/
│   ├── search-demo.png
│   ├── analytics-dashboard.png
│   ├── monitoring-dashboard.png
│   └── tfidf-ranking.png
└── database/
    └── search_engine.db
```

---

## Learning Outcomes

This project demonstrates practical understanding of:

- Search Engine Architecture
- Information Retrieval
- TF-IDF Ranking
- Query Processing
- Inverted Indexes
- Database Design
- Caching Strategies
- Analytics Systems
- Scalability Concepts
- CAP Theorem
- Fault Tolerance
- System Design Principles

---

## Author

Developed as a Search Engine System Design and Simulation Project for academic and interview preparation purposes.
