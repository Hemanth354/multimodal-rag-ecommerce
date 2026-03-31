# 🛒 Multimodal RAG E-Commerce Product Assistant

An AI-powered shopping assistant that allows users to search and explore e-commerce products using **natural language queries** and **image-based search**.  
The system uses **Retrieval-Augmented Generation (RAG)** to retrieve relevant products and generate intelligent recommendations using an LLM.



---

## 🚀 Features

✅ Text-based semantic product search  
✅ CLIP-based image search (visual similarity retrieval)  
✅ Vector search using **FAISS**  
✅ Hybrid retrieval (**Vector Search + BM25 Keyword Search**)  
✅ Transformer-based **Reranker** for better ranking  
✅ LLM-powered recommendation using **Groq Gemma**  
✅ Conversational AI chat support with memory  
✅ Streamlit interactive UI

---

## 🧠 Tech Stack

- Python
- Streamlit (Frontend UI)
- FAISS (Vector Database)
- CLIP Embeddings (Multimodal Search)
- BM25 (Keyword Retrieval)
- CrossEncoder / BGE Reranker
- Groq API (Gemma LLM)
- Pandas, NumPy

---

## 📂 Dataset

The dataset contains product information with the following columns:

- `product_id`
- `product_name`
- `category`
- `discounted_price`
- `actual_price`
- `discount_percentage`
- `rating`
- `rating_count`
- `about_product`
- `product_link`

The text fields (`product_name`, `category`, `about_product`) are combined to generate embeddings for semantic search.

---

## 🏗️ Project Architecture

```text
User (Text Query / Image Upload)
        │
        ▼
Streamlit Web Application
        │
        ▼
Embedding Generator
(CLIP Text Encoder / CLIP Image Encoder)
        │
        ▼
Hybrid Retrieval
(FAISS Vector Search + BM25 Keyword Search)
        │
        ▼
Reranker Model
(Cross Encoder / BGE Reranker)
        │
        ▼
Top Relevant Products
        │
        ▼
Groq Gemma LLM
        │
        ▼
AI Recommendation + Explanation
        │
        ▼
Conversational Memory (Session State)

---

## Project Structure


multimodal-rag-ecommerce/
│
├── data/
│   └── products.csv
│
├── embeddings/
│   └── build_embeddings.py
│
├── models/
│   └── clip_model.py
│
├── rag_pipeline/
│   ├── retriever.py
│   ├── hybrid_search.py
│   └── reranker.py
│
├── llm/
│   └── llm_interface.py
│
├── ui/
│   └── streamlit_app.py
│
├── product_index.faiss
├── requirements.txt
└── README.md


---

## Installation

Clone the repository

```
git clone https://github.com/yourusername/multimodal-rag-ecommerce.git
cd multimodal-rag-ecommerce
```

Install dependencies

```
pip install -r requirements.txt
```

---

## Build Vector Index

Generate embeddings and build the FAISS index:

```
python embeddings/build_embeddings.py
```

---

## Run the Application

Start the Streamlit app:

```
streamlit run ui/streamlit_app.py
```

Open the browser at:

```
http://localhost:8501
```

---

## Example Query

Users can ask queries such as:

* "fast charging cable for iPhone"
* "best laptop under budget"
* "high rated charger"
* "durable USB cable"

The system retrieves relevant products and generates an AI-powered recommendation.

---

## Future Improvements

* Product comparison with LLM reasoning
* Personalized recommendations
* Deployment using Docker or cloud platforms

---
