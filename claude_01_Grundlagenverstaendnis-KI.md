# 1 – Grundlagenverständnis KI

## Was ist Künstliche Intelligenz?

KI bezeichnet Computersysteme, die Aufgaben ausführen, die normalerweise menschliche Intelligenz erfordern: Sprachverstehen, Mustererkennung, Entscheidungsfindung, Lernen aus Daten.

## Die drei Ebenen: KI, ML, Deep Learning

- **KI (AI)** – Oberbegriff für alle Techniken, die intelligentes Verhalten simulieren
- **Machine Learning (ML)** – Systeme lernen aus Daten, ohne explizit programmiert zu werden
- **Deep Learning (DL)** – Neuronale Netze mit vielen Schichten; stark bei Bild, Text, Audio
- **Generative KI** – KI, die neue Inhalte erstellt (Text, Bilder, Code)

## Lernparadigmen

- **Supervised Learning** – Lernen mit beschrifteten Daten (z. B. Spam-Erkennung)
- **Unsupervised Learning** – Muster in unbeschrifteten Daten (z. B. Kundensegmentierung)
- **Reinforcement Learning** – Lernen durch Belohnung/Bestrafung (z. B. Spiele, Roboter)
- **Transfer Learning** – Vortrainierte Modelle auf neue Aufgaben anpassen

## Large Language Models (LLMs)

LLMs sind neuronale Netze, trainiert auf riesigen Textmengen. Basis: **Transformer-Architektur** (Google, 2017).

**Funktionsweise:**
1. Text wird in Tokens (Wortteile) zerlegt
2. Modell berechnet Wahrscheinlichkeiten für das nächste Token
3. Attention-Mechanismen ermöglichen Kontextverständnis

**Wichtige Konzepte:**
- **Parameter** – Gewichte im Netz (GPT-4: ~1 Billion)
- **Halluzination** – Modell erzeugt falsche, aber plausibel klingende Inhalte
- **Context Window** – Wie viel Text das Modell auf einmal verarbeitet (128k–2M Tokens)
- **Temperature** – Steuert Kreativität (0 = deterministisch, >1 = kreativ)

## KI-Typen nach Fähigkeit

- **Narrow AI (ANI)** – Spezialisiert auf eine Aufgabe → heute Standard
- **General AI (AGI)** – Menschenähnliche Intelligenz → noch nicht erreicht
- **Super AI (ASI)** – Übermenschliche Intelligenz → theoretisch/Zukunft

## Wichtige Begriffe

- **Prompt** – Eingabe/Anweisung an ein KI-Modell
- **Token** – Grundeinheit des Textes (ca. 3/4 eines Wortes)
- **Embedding** – Numerische Darstellung von Text im Vektorraum
- **Fine-Tuning** – Nachtraining auf spezifische Daten
- **RLHF** – Reinforcement Learning from Human Feedback
- **Multimodal** – KI versteht mehrere Datentypen (Text, Bild, Audio)
- **API** – Schnittstelle zur programmatischen Nutzung von KI-Modellen

## Die drei Treiber des KI-Booms

1. **Datenverfügbarkeit** – Internet liefert Billionen Trainingsdaten
2. **Rechenleistung** – GPUs/TPUs ermöglichen Training riesiger Modelle
3. **Algorithmenfortschritt** – Transformer, Attention, RLHF als Schlüsselinnovationen

## Was KI (noch) nicht kann

- Echtes Verstehen und Bewusstsein
- Garantiert faktenbasierte Aussagen (Halluzinationen)
- Lernen aus einzelnen Gesprächen ohne Fine-Tuning
- Autonomes Handeln in der physischen Welt
