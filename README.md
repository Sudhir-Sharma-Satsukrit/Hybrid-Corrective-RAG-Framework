# Project Title 🚀
# Hybrid-Corrective-RAG-Framework
Developed a retrieval system that implements a **Corrective RAG (CRAG)** pipeline using **LangGraph**, designed to intelligently evaluate the reliability of local retrieval and automatically fall back to **real web search** when internal knowledge is insufficient. The system goes beyond standard RAG by introducing a **three‑way classification** of retrieved chunks—correct, ambiguous, and incorrect—and refining partially relevant context instead of discarding it.

The pipeline demonstrates a robust pattern for enterprise‑grade retrieval systems:  
**never assume local knowledge is trustworthy, evaluate reliability explicitly, salvage useful context, and correct course with external sources when needed.**




![Demo Screenshot or GIF](./assets/demo.gif)

## 1. Problem Statement 
Meridian Engineering Company's internal assistant relies on a local knowledge base that is incomplete, outdated, and blind to real‑time external information. A standard RAG pipeline retrieves nearby embeddings without judging their reliability, often producing outdated or irrelevant answers and failing to detect when external information is needed.
A smarter system is needed to grade retrieval quality, salvage useful context, and trigger web search when local knowledge fails.

## 2. Architecture 
- **User Query**  
- **Local Vector Store Retrieval**  
- **Chunk Classification (Correct / Ambiguous / Incorrect)**  
- **Ambiguous Chunk Refinement**  
- **Reliability Scoring**  
- **Web‑Search Fallback (if needed)**  
- **Answer Synthesis with Source Attribution**


## 3. Key Features 
- **Three‑Way Chunk Reliability Classification**    
Every retrieved chunk is graded as correct, ambiguous, or incorrect, replacing the simplistic binary relevance check used in             standard RAG. This allows the system to understand how trustworthy each piece of local information is.

- **Ambiguous Chunk Refinement**  
Instead of discarding partially relevant documents, the pipeline extracts only the genuinely useful sentences and removes noise. This salvages valuable context that traditional RAG would ignore.

- **Automatic Web‑Search Fallback**  
When local retrieval is unreliable—no correct chunks or too many incorrect ones—the system automatically triggers real web search to supplement or replace internal knowledge.

- **Transparent Source Attribution**  
Every fact in the final answer is clearly tagged with its origin:
local document, refined chunk, or web search.
This ensures full transparency and auditability.

- **Reliability‑Aware Answer Generation**  
The final response is synthesized using only the most trustworthy information, combining refined local context with external search results when needed.

- **Built on LangGraph for Agentic Control**  
The pipeline uses LangGraph to orchestrate grading, refinement, fallback logic, and answer synthesis in a structured, agent‑driven workflow.




## 4. Tech Stack
- **LangGraph**  
- **Python**  
- **Local Vector Store (FAISS / Chroma / Milvus)**  
- **Web Search API**  
- **LLM for grading, refinement, and synthesis**





