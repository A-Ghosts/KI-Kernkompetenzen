# 3 – Retrieval & Wissenssysteme

## Das Kernproblem

Standard-LLMs haben einen Knowledge Cutoff – sie kennen keine internen Dokumente, keine aktuellen Daten, keine proprietären Informationen. Retrieval-Systeme lösen dieses Problem.

## Retrieval-Augmented Generation (RAG)

RAG ist die wichtigste Methode, um LLMs mit aktuellem und eigenem Wissen zu erweitern.

**Ablauf:**

1. INDEXIERUNG (einmalig): Dokumente → Chunks → Embeddings → Vektordatenbank
2. ABFRAGE (jede Anfrage): User-Frage → Embedding → Ähnlichkeitssuche → Top-K Chunks
3. GENERIERUNG: LLM + relevante Chunks + User-Frage → Antwort mit Quellenangabe

**Vorteile:** Aktuelles Wissen ohne Neu-Training, Quellenangaben möglich, kostengünstiger als Fine-Tuning, einfach aktualisierbar.

**Nachteile:** Qualität hängt von Chunking-Strategie ab, höhere Latenz, komplexere Architektur.

## Embeddings & Vektordatenbanken

Embeddings sind numerische Vektoren, die den semantischen Inhalt von Text repräsentieren. Ähnliche Texte liegen im Vektorraum nah beieinander.

**Wichtige Vektordatenbanken:**
- **Pinecone** – Managed Service, sehr skalierbar (Enterprise)
- **Weaviate** – Open Source, multimodal (Flexibel)
- **Chroma** – Einfach, Python-nativ (Prototyping)
- **Qdrant** – Open Source, performant (Self-hosted)
- **pgvector** – PostgreSQL-Erweiterung (Bestehende DB)

## Chunking-Strategien

Wie Dokumente zerlegt werden, bestimmt die RAG-Qualität.

- **Fixed Size** – Feste Zeichenanzahl mit Overlap → einfacher Einstieg
- **Sentence Splitting** – An Satzgrenzen → strukturierte Texte
- **Semantic Chunking** – Nach inhaltlicher Kohärenz → beste Qualität
- **Document Structure** – Header-basiert (Markdown, HTML) → Dokumentationen

Faustregel: 256–512 Tokens pro Chunk, 50–100 Tokens Overlap.

## Fortgeschrittene RAG-Techniken

- **Hybrid Search** – Semantische Suche + Keyword-Suche kombiniert
- **Re-Ranking** – Ergebnisse durch separates Ranking-Modell neu sortieren
- **HyDE** – LLM generiert hypothetische Antwort für bessere Suche
- **Multi-Query Retrieval** – Frage in mehrere Varianten umformulieren
- **Parent Document Retrieval** – Kleine Chunks suchen, große als Kontext nutzen

## RAG vs. Fine-Tuning

| Kriterium | RAG | Fine-Tuning |
|---|---|---|
| Wissensaktualität | Immer aktuell | Statisch |
| Kosten | Günstig | Teuer |
| Quellenangaben | Möglich | Schwierig |
| Verhalten/Tonalität | Begrenzt | Sehr gut |
| Implementierung | Mittel | Hoch |

Empfehlung: Zuerst RAG versuchen. Fine-Tuning nur wenn Verhalten/Stil angepasst werden muss.

## Evaluation von RAG-Systemen

- **Retrieval Precision** – Wie relevant sind die gefundenen Chunks?
- **Answer Faithfulness** – Ist die Antwort durch die Quellen gedeckt?
- **Answer Relevance** – Beantwortet die Antwort die Frage?
- **Context Recall** – Wurden alle relevanten Infos gefunden?

Tools: RAGAS, TruLens, LangSmith
