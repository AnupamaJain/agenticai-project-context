## RAG / AI System

<!-- Remove this file entirely if your project has no AI/LLM component -->

- Separate ingestion, parsing, chunking, embedding, indexing, retrieval, reranking, context assembly, and answer generation.
- Keep retrieval logic independent from answer generation logic.
- Preserve source metadata for traceability.

### RAG Rules

- Never dump raw full documents into prompts — use chunking strategies.
- Use deterministic chunking strategies unless explicitly experimenting.
- Maintain chunk metadata: source, page, section, title, tenant, timestamps.
- Prefer source attribution/citations in outputs where trust and traceability matter.
- Add configurable retrieval parameters: top_k, filters, score thresholds, reranking.

### Ingestion

- Support clean, repeatable document ingestion pipelines.
- Normalize and sanitize extracted text.
- Preserve source identity and version.
- Re-embed only when necessary — embedding is expensive.

### Answering

- Ground answers in retrieved context.
- Handle no-context and low-confidence cases gracefully — do not hallucinate.
- Return structured outputs where the product requires it.
- Log what context was retrieved and what was used for each answer.

### Do Not

- Mix ingestion code with runtime answer generation in the same module.
- Make retrieval behavior impossible to inspect or tune.
- Hide retrieval failures silently.
- Dump system prompts with PII or secrets into logs.