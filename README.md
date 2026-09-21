# Architecture

```text
[Unstructured Financial PDFs/Excel] 
       │
       ▼ (Ingestion & Extraction)
[LlamaParse (Agentic OCR / Markdown Layouts)]
       │
       ▼ (Vectorization & Ingestion)
[Qdrant Dual Ingestion Client] ──► Sparse Model (BM25) ──┐
                               ──► Dense Model (BGE)    ──┼─► [Single Qdrant Collection]
                                                          │
       ▼ (Unified API Layer)                              │
[FastAPI Endpoint] ◄──────────────────────────────────────┘
       │
       ▼ (Re-ranking Optimization)
[Cross-Encoder Layer (BGE-Reranker-Large)]
       │
       ▼ (Inference)
[Bilingual LLM Synthesis (Llama-3 / GPT-4o)]
       │
       ▼ (Production & Validation Harness)
[Evaluation & Tracing Engine (Ragas & TruLens Dashboard)]
```
