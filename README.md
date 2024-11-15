
# Scalable Retrieval-Augmented Generation (RAG) System

An interactive web-based system that retrieves relevant information from live documents using FAISS and generates real-time responses with Google T5 Flan. Integrated federated learning using the Flower framework to enable privacy-preserving model training across decentralized clients, leading to improved accuracy and faster response times.

---

## 🛠 Tech Stack

- **Python**: Core language for backend development.
- **FAISS**: For high-dimensional similarity search and distributed retrieval.
- **Elasticsearch**: Datastore for document sections and metadata, supporting efficient retrieval.
- **FastAPI**: API framework for handling user queries and responses.
- **Flower**: Federated learning framework for optimizing retrieval models across distributed nodes.
- **SentenceTransformers**: For embedding generation using pre-trained models.
- **Torch**: For model training and inference in the generative component.
- **Docker**: Containerization for service deployment.

---

## 📦 Installation

### Prerequisites

Ensure the following are installed:
- Python 3.8+
- Docker
- Elasticsearch (running locally or on a specified host)
- FAISS

### Setup Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/nivethamagesh66/Scalable-Retrieval-Augmented-Generation-RAG-System.git
   cd Scalable\ Retrieval-Augmented\ Generation\ \(RAG\)\ System/server
   ```

2. **Python Environment**
   ```bash
   python3 -m venv env
   source env/bin/activate
   pip install -r requirements.txt
   ```

3. **Environment Variables**
   Create a `.env` file with:
   ```
   ELASTICSEARCH_HOST=<elasticsearch_host>
   FAISS_INDEX_PATH=<path_to_faiss_index>
   FLASK_APP=<main_application_file>
   ```

4. **Start Docker Services**
   ```bash
   docker-compose up
   ```

5. **Run the FastAPI Server**
   ```bash
   uvicorn run_client:app --host 0.0.0.0 --port 8001
   ```

---

## 💻 Frontend Setup (React)

1. **Go to Client Directory**
   ```bash
   cd ../client
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Start React Server**
   ```bash
   npm start
   ```

4. **Access the App**
   ```
   http://localhost:3000
   ```

---

## 📡 Usage

### 1. Querying the RAG System

Send a POST request to `/answer`:

```json
{
  "user_query": "Enter your question here",
  "isRAGEnabled": true
}
```

**Example with curl**:
```bash
curl -X POST "http://localhost:8001/answer" -H "Content-Type: application/json" -d '{"user_query": "Does the company offer tuition reimbursement?", "isRAGEnabled": true}'
```

### 2. Federated Learning with Flower

- Ensure each client/node (e.g., FAISS service) is running and connected to participate in federated training.
- Flower handles federated updates securely.

---

## 👤 Author

**Nivetha Magesh**  
GitHub: [@nivethamagesh66](https://github.com/nivethamagesh66)

---
