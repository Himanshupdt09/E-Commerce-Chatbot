# E-Commerce Chatbot using RAG (LangChain + OpenAI + AstraDB)

An intelligent chatbot that answers product-related queries by combining Retrieval-Augmented Generation (RAG) with LangChain, OpenAI Embeddings, and AstraDB vector storage. Built to handle Flipkart-style headset and earbud product data and deployed using Flask on AWS EC2.

![Chat Demo 1](images/image1.png)
![Chat Demo 2](images/image2.png)

---

## Features

- End-to-end product question-answering system powered by LLMs.
- Embedding-based semantic retrieval using OpenAI and LangChain.
- Product metadata stored and queried from AstraDB.
- Flask-based web interface for real-time user interaction.
- Fully deployed on AWS EC2 for accessible hosting.

---

## Tech Stack

| Component     | Description                                         |
|---------------|-----------------------------------------------------|
| OpenAI        | Embedding generation for product descriptions       |
| LangChain     | RAG pipeline for retrieval and response generation |
| AstraDB       | Cloud-based vector database for semantic search     |
| Flask         | Web application (frontend and backend)              |
| AWS EC2       | Hosting and deployment                              |
| Flipkart Data | Sample product dataset (headphones, earbuds)        |

---

## Project Structure

```plaintext
ecomm-chatbot/
├── app.py                       # Flask entry point
├── requirements.txt             # Python dependencies
│
├── data/
│   └── flipkart_products.csv    # Product dataset
│
├── ecombot/
│   ├── __init__.py
│   ├── data_converter.py        # Converts CSV to LangChain documents
│   ├── ingest.py                # Embedding generation and ingestion
│   └── retr_gen.py              # Retrieval and response logic
│
├── templates/
│   └── chat.html                # HTML UI for chatbot
│
├── static/
│   └── style.css                # UI styling
│
├── images/
│   ├── image1.png
│   └── image2.png
│
└── README.md
```

---

## How It Works

1. Product data is parsed and converted into document chunks.
2. OpenAI embeddings are generated for each chunk.
3. Embeddings and metadata are stored in AstraDB.
4. User queries are passed through a LangChain retriever to fetch relevant chunks.
5. Retrieved content is used to generate answers via a language model.
6. Final response is rendered on a web interface using Flask.

---

## Running Locally

1. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. Run the Flask application:

   ```bash
   python app.py
   ```

3. Open your browser and navigate to `http://localhost:5000`.

---

## Deployment

- Hosted on AWS EC2
- Vector database and metadata stored in AstraDB
- LLM-powered responses served through OpenAI API
- Docker-compatible for containerized deployment

---

## Future Improvements

- Integrate voice input via speech-to-text
- Extend support for multiple product categories
- Enable user chat history and session tracking
- Add query filters such as brand, price range, etc.