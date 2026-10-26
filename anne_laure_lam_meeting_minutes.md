# LAM RAG Project — Meeting Minutes

**Date:** 26 October 2026  
**Project:** LAM AI-Powered Search Assistant  
**Objective:** Build an initial RAG demonstrator using scientific documentation and project information from LAM.

---

## 1. Initial Technical Approach
* **Vector Database:** Start with ChromaDB for vector storage and retrieval. Consider Qdrant at a later stage.
* **Scope:** Develop a simple, working demonstrator first rather than implementing complex access control or authentication.
* **Workflow:** Follow the existing Jupyter notebook workflow, particularly Notebook 01, and reuse the approaches demonstrated in the course materials.
* **Interface:** Build a command-line RAG pipeline initially, followed by a Streamlit or Dash interface.
* **Reference:** Use the Centrale GitHub repository as the reference implementation.

---

## 2. PDF Ingestion and Summarization
* **Document Target:** Begin with two or three MMX-related PDF documents.
* **Chunking Strategy:** Split each PDF page by page, treating each page as an individual initial chunk.
* **Summarization Target:** Generate a concise summary of each page, approximately 5–6 sentences long.
* **LLM Selection & Prompting:** Develop and refine the summarization prompt for an appropriate language model (such as Gemma 4 31B?) to preserve the original meaning and important technical details.
* **Metadata Retention:** Each summary should retain important keywords, entities, technical terminology, and contextual information.
* **Data Storage:** 
  * Store the processed PDF content in a structured JSON file, including page number, document title, source location, original text, and summary.
  * Maintain a separate JSON file for Redmine content.

---

## 3. Website and Redmine Ingestion
* **Public Content:** Investigate extracting content from the LAM website and relevant wiki pages, including GLNEMO documentation using Python HTML-parsing and web-scraping libraries.
* **Redmine Ingestion:** Investigate extracting one Redmine project as an initial test, then expand to a second project if successful.
* **Extraction Methods:** Compare browser-based scraping with Redmine's API as a potential alternative.
* **Context Preservation:** Preserve project names, titles, source URLs, and relevant contextual information in the extracted records.

---

## 4. Models and Embeddings
* **Embeddings:** Evaluate alternative embedding models, including Qwen embeddings and models available through Ollama.
* **Summarization Model:** Investigate using a stronger language model for page summarization, with particular attention to prompt quality and factual preservation.
* **Architecture:** Keep summarization, embedding, retrieval, and answer generation as separate stages of the pipeline.

---

## 5. Infrastructure and Access
* **Access Status:** Access to the computing machine and SSH is still pending because the public-services/access upgrade has not been completed.
* **Support:** The team is awaiting support from the data centre to restore the required access.
* **Hardware:** GPU resources, including an A100, are expected to be made available.
* **Interim Plan:** In the meantime, develop and test the ingestion and preprocessing pipeline locally where feasible.

---

## 6. Demonstration Plan
* **Target:** Prepare a basic ChromaDB-backed RAG pipeline for the Monday demonstration.
* **Dataset Note:** Use MMX PDF documents as the initial dataset. *(Note: Did not receive on time, so moved to other LAM-related PDFs).*
* **Interface Progress:**
  1. Demonstrate retrieval and question answering from the processed documents through the command line.
  2. Subsequently integrate the pipeline with a Streamlit or Dash interface, potentially using the LAM website as a demonstration entry point.

---

## 7. Immediate Action Items
1. **PDF Ingestion:** Process two or three MMX PDFs, extract page-level text, generate summaries, and produce structured JSON.
2. **Summarization:** Refine the prompt and evaluate the quality of the generated summaries.
3. **RAG Prototype:** Integrate the processed documents with ChromaDB and test retrieval.
4. **Web/Redmine Ingestion:** Test extraction of one Redmine project and relevant public wiki content.
5. **Infrastructure:** Follow up with the data centre regarding SSH and GPU access.
6. **Coordination:** Email Thomas Fenouil, copying Christian Surace, to clarify the scraping approach and the MMX documentation to use.

---

> **Expected Initial Deliverable:** A reproducible PDF-to-JSON pipeline that produces page-level text and summaries, ready for embedding and retrieval in the initial ChromaDB demonstrator.