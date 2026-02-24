# 🎬 Movie Recommender (Neo4j + Groq)

![Python](https://img.shields.io/badge/python-3.9%2B-green)
![Neo4j](https://img.shields.io/badge/database-Neo4j-brightgreen)
![Streamlit](https://img.shields.io/badge/UI-Streamlit-ff4b4b)
![LLM](https://img.shields.io/badge/LLM-Groq-orange)

> A smart movie recommendation system powered by Neo4j graph database and Groq LLM for natural language understanding.

---

## 📌 Table of Contents

- [✨ Motivation](#-motivation)
- [🔥 Key Features](#-key-features)
- [🏗 Architecture](#-architecture)
- [🎥 Demo](#-demo)
- [🛠 Prerequisites](#-prerequisites)
- [⚙️ Installation](#-installation)
- [🚀 Usage](#-usage)
- [🔧 Configuration](#-configuration)
- [🗺 Roadmap](#-roadmap)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)
- [👤 Author](#-author)
- [🙏 Acknowledgements](#-acknowledgements)

---

## ✨ Motivation

Traditional recommendation systems rely heavily on vector similarity or static filters.

This project explores a **Graph + LLM hybrid approach**, where:

- 🧠 Groq LLM extracts user intent from natural language
- 🕸 Neo4j graph database models relationships between Movies, Genres, Actors
- ⚡ Streamlit provides a clean interactive UI

The goal is to demonstrate how **LLMs + Graph Databases** can work together in real-world applications.

---

## 🔥 Key Features

- ✅ Natural language queries ("recommend movies like Inception")
- ✅ Graph-based similarity using Neo4j relationships
- ✅ Recommendations by:
  - Similar movie
  - Genre
  - Actor
  - Top-rated
- ✅ Intent extraction via Groq LLaMA model
- ✅ Interactive Streamlit interface
- ✅ Clean modular architecture (LLM layer + DB layer + UI layer)

---

## 🏗 Architecture

```
User Query (Streamlit UI)
        ↓
Groq LLM (Intent Extraction)
        ↓
Intent JSON
        ↓
Neo4j Graph Query
        ↓
Recommendations
        ↓
Displayed in UI
```

### Graph Schema

- (:Movie)
- (:Genre)
- (:Actor)

Relationships:

- (:Movie)-[:BELONGS_TO]->(:Genre)
- (:Movie)-[:ACTED_IN]<-(:Actor)

---

## 🎥 Demo

Example queries:

```
recommend movies like inception
top rated movies
action movies
movies by leonardo dicaprio
```

Example output:

```
Interstellar
Tenet
The Matrix
Shutter Island
```

---

## 🛠 Prerequisites

Make sure you have:

- Python 3.9+
- Neo4j Desktop or Neo4j Aura
- Groq API Key
- Git

Python libraries:

- streamlit
- neo4j
- groq
- python-dotenv (optional)

---

## ⚙️ Installation

### 1️⃣ Clone the Repository

```
git clone https://github.com/your-username/movie-recommender-graph.git
cd movie-recommender-graph
```

---

### 2️⃣ Create Virtual Environment

```
python -m venv venv
source venv/bin/activate      # Mac/Linux
venv\Scripts\activate         # Windows
```

---

### 3️⃣ Install Dependencies

```
pip install -r requirements.txt
```

---

### 4️⃣ Configure Environment Variables

Create a `.env` file:

```
GROQ_API_KEY=your_groq_api_key
NEO4J_URI=bolt://localhost:7687
NEO4J_USER=neo4j
NEO4J_PASSWORD=your_password
```

---

### 5️⃣ Load Movie Data into Neo4j

```
python load_data.py
```

---

### 6️⃣ Run the Application

```
streamlit run app.py
```

Open:

```
http://localhost:8501
```

---

## 🚀 Usage

Type natural language queries like:

```
recommend movies like inception
```

```
top rated movies
```

```
romantic movies
```

```
movies by tom hanks
```

The system automatically:

1. Extracts structured intent via Groq
2. Runs graph queries in Neo4j
3. Returns recommended movies

---

## 🔧 Configuration

Environment Variables:

| Variable | Description |
|----------|------------|
| GROQ_API_KEY | Your Groq API key |
| NEO4J_URI | Neo4j database URI |
| NEO4J_USER | Neo4j username |
| NEO4J_PASSWORD | Neo4j password |

Optional:
- Modify `llm.py` to change LLM model
- Modify `db.py` to customize Cypher queries

---

## 🗺 Roadmap

- [ ] Add movie posters (TMDB API integration)
- [ ] Add rating display in UI
- [ ] Add collaborative filtering
- [ ] Add user authentication
- [ ] Deploy to Streamlit Cloud
- [ ] Dockerize project

---

## 🤝 Contributing

Contributions are welcome!
## ⭐ If You Like This Project

Give it a ⭐ on GitHub!
