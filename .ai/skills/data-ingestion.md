---
name: data-ingestion
description: Standardized pipeline for parsing, chunking, and indexing data (RAG/DB).
---

# Skill: Data Ingestion Pipeline

## Goal
Process raw documents (PDF, Text, Markdown) into structured, searchable data.

## Steps
1. **Source**: Extract text from the source file.
2. **Cleanup**: Normalize text (remove extra whitespace, sanitize characters).
3. **Chunking**: Break text into semantically meaningful chunks (e.g., 500-1000 tokens).
4. **Metadata**: Attach source info (filename, timestamp, tenant ID) to each chunk.
5. **Indexing**: Insert chunks into the database or vector store.

## RAG Rule
Refer to `.ai/rules/50-rag-system.md` for chunking strategies.
