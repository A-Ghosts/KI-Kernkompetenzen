# 6 – Infrastruktur & Entwicklung (Deployment)

## Die drei Deployment-Modelle

**Cloud API** – Sofort nutzbar, kein Setup, Pay-per-Use (OpenAI, Anthropic, Google)

**On-Premise / Self-Hosted** – Volle Kontrolle, hohe Investition, feste Kosten

**Hybrid** – Kombination aus beidem, flexibel aber komplex

## Cloud-basiertes Deployment

API-as-a-Service – direkte Nutzung ohne eigene Infrastruktur:
- OpenAI API – Größtes Ökosystem
- Anthropic Claude API – Stark bei Sicherheit
- Google Vertex AI – GCP-Integration
- AWS Bedrock – Multi-Modell, AWS-nativ
- Azure OpenAI Service – Microsoft-Ökosystem, DSGVO-konform
- Mistral La Plateforme – EU-basiert

## On-Premise – wann sinnvoll?

- Strenge Datenschutzanforderungen (Gesundheit, Recht, Finanzen)
- Hochvolumige Anwendungen (ab bestimmtem Scale günstiger)
- Regulatorische Anforderungen (Datensouveränität, AI Act)
- Schutz von Intellectual Property

**Wichtige Hardware:** GPU (NVIDIA H100/A100/RTX 4090), VRAM (24–80 GB+), NVMe SSD (10+ TB)

**Software-Stack:** FastAPI (API-Server), vLLM/TGI/Ollama (Inference), Docker/Kubernetes (Container), Prometheus/Grafana (Monitoring)

**Self-Hosting-Tools:**
- **Ollama** – Einfachstes lokales LLM-Hosting
- **vLLM** – Hochperformante Inferenz, Produktion
- **LM Studio** – GUI für lokale Modelle
- **Jan** – Open-Source ChatGPT-Alternative lokal

## MLOps – KI in Produktion

MLOps = Praktiken für den zuverlässigen Betrieb von KI-Systemen.

Lifecycle: Daten sammeln → Modell wählen/trainieren → Evaluieren → Deployen → Monitoren → Verbessern

**Experiment Tracking:** MLflow, Weights & Biases, Neptune

**Data Versioning:** DVC, LakeFS

**CI/CD für ML:** GitHub Actions, ArgoCD

**Monitoring – was beobachten:**
- Latenz & Throughput (SLA einhalten)
- Token-Kosten (Budget-Kontrolle)
- Halluzinations-Rate (Qualität)
- Data Drift (Modell bleibt relevant)

Monitoring-Tools: LangSmith, Helicone, Langfuse, Arize AI

## Inference-Optimierung

- **Quantisierung** (INT8/INT4) – Modell kleiner, schneller, minimal weniger Qualität
- **Batch Processing** – Mehrere Anfragen gleichzeitig
- **KV-Cache** – Wiederverwendung von Zwischenergebnissen
- **Continuous Batching** – Maximale GPU-Auslastung

## Kostenkalkulation

Cloud API: Kosten = Input-Tokens x Preis/1M + Output-Tokens x Preis/1M
Beispiel Claude Sonnet: ~$3 Input + $15 Output pro 1M Tokens

Self-Hosted TCO: Hardware + Strom + Kühlung + Personal + Wartung
Breakeven: Typisch ab >10M Tokens/Tag rentabler als API

## Sovereign AI – Datensouveränität 2026

Unternehmen und Staaten bauen eigene KI-Infrastrukturen auf:
- EU AI Act Compliance
- DSGVO / Datenschutz
- Geopolitische Risiken

Lösungen: EU-Cloud-Anbieter (Scaleway, Hetzner, OVH), Mistral AI (Paris), On-Premise mit Open Source, Private Clouds nach BSI-Standards
