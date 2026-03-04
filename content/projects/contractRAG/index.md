---
title: ContractRAG
date: 2025-11-01
tags:
  - RAG
  - LLM
  - MCP
  - Information Retrieval
  - Enterprise AI
---

A Retrieval-Augmented Generation system providing intelligent access to a company's entire internal contract repository.

<!--more-->

ContractRAG gives organisations a conversational interface over all their internal contracts. The system is designed around a two-stage sequential retrieval pipeline that prioritises precision and efficiency.

**Metadata extraction** is performed first — combining structural signals from file and folder names with LLM-powered content analysis to enrich each document with relevant metadata at index time.

**Retrieval pipeline:**

1. Incoming user queries are first matched against extracted metadata to narrow down the candidate chunks. This drastically reduces the search space before any vector search is performed.
2. A semantic search is then run over the remaining chunks to surface the most relevant content.

If no matching metadata is found for a query, the system falls back directly to semantic search across the full corpus.

ContractRAG exposes its functionality as an MCP server, allowing it to be plugged into any compatible LLM client — including Langdock, Claude Desktop, and similar tools — without additional integration work.
