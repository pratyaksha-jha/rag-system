# Retriever: Explainable RAG with Local Knowledge Graphs

**Team FPS**      
*Pratyaksha Jha | Somita Agarwal | Freya Sheth*      
**IIT Guwahati**

---

## Project Overview
**Retriever** is a browser-native, transparent Retrieval-Augmented Generation (RAG) system. It addresses the "Black Box" nature of traditional AI by providing a modular pipeline where every generated answer is supported by a **Local Knowledge Graph**. This graph visualizes the entities, metrics, and evidence sentences used to derive the final response, ensuring 100% verifiability.



## Key Design Features

- **Privacy-First Architecture:** 100% client-side execution. No user data is sent to external servers; all processing is handled in the browser via `pdf.js` and custom JavaScript logic.
- **Auditable Retrieval:** Uses Term-Frequency scoring with a **Factual Boost** ($+1$ score for numerical data/units), ensuring the retrieval process is deterministic and traceable.
- **Bounded Context Graph:** The Knowledge Graph is constructed strictly from the retrieved chunks, preventing "Global Hallucinations" and ensuring nodes represent only the current context.
- **Extractive Synthesis:** Instead of abstractive text generation, the system ranks and concatenates original source sentences to maintain absolute grounding in the evidence.

## Technical Stack

- **Core Logic:** Vanilla JavaScript (ES6+), Regex-based Extraction.
- **UI/UX:** HTML5, Tailwind CSS.
- **Parsing Libraries:** `pdf.js` (PDF), `mammoth.browser.js` (Word).
- **Deployment:** Static Web App.

---

## How It Works

1. **Document Ingestion:** Upload PDF, DOCX, or JSON. Documents are fragmented into overlapping chunks to preserve local context.
2. **Retrieval Engine:** A keyword-based scoring algorithm identifies the most relevant chunks.
3. **Local Entity Extraction:** The system identifies **METRICS** (numerical data) and **ENTITIES** (Proper nouns) using pattern-based NLP.
4. **Answer Synthesis:** Relevant sentences are selected and ranked to form a factual response.
5. **Explanation Layer:** The UI displays color-coded entity tags and interactive evidence blocks linked to the source files.

---

## Getting Started

### Prerequisites
No installation or API keys required. All logic runs in a modern web browser.

### Running the Prototype
1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/pratyaksha-jha/rag-system.git](https://github.com/pratyaksha-jha/rag-system.git)
   ```
2. **Launch:** Open the index.html file in Chrome, Firefox, or Edge.
3. **Test:** Upload your documents or click "Load Sample Documents" to see the system process climate and economic datasets.

### Technical Report
For a deep dive into our methodology, scoring formulas, and architectural design choices, please refer to our technical report.

### Team FPS      
IIT Guwahati      
- Pratyaksha Jha      
- Somita Agarwal      
- Freya Sheth   
