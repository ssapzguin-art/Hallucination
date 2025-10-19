# 🧠 Structured Human–AI Dialogue Dataset 

## Overview
This repository contains a structured dataset derived from a full Korean human–AI dialogue log.  
It focuses on linguistic and behavioral aspects of generative models — specifically **abstraction**, **self-reference**, and **hallucination-like responses**.

The dataset has been automatically annotated and formatted for structural analysis rather than semantic interpretation.

---

## Files

| File | Description |
|------|--------------|
| `dialog_structured.csv` | Turn-level annotated dataset |
| `dialog_structured.jsonl` | JSON Lines format |
| `schema.json` | Field schema and label documentation |
| `README.md` | Main documentation (English) |
| `README_ko.md` | Korean version of this document |

---

## Schema

| Field | Type | Description |
|--------|------|-------------|
| `turn_id` | integer | Sequential index of dialogue turns |
| `speaker` | string | `"user"` or `"ai"` |
| `text` | string | Original Korean utterance |
| `char_len` | integer | Character count |
| `token_est` | integer | Estimated token length |
| `has_question` | boolean | True if contains interrogative marker |
| `is_command` | boolean | True if imperative (user only) |
| `self_reference` | boolean | True if AI refers to itself |
| `abstraction_level` | integer | 0 = concrete, 1 = abstract, 2 = meta-level |
| `hallucination_like` | boolean | True when AI is both abstract and self-referential |

---

## Quantitative Summary

| Metric | Approx. Value | Description |
|---------|----------------|-------------|
| User question rate | ~35% | Fraction of user turns with questions |
| User command rate | ~25% | Fraction of user turns with imperatives |
| AI self-reference rate | ~40% | AI mentions itself or its own state |
| AI hallucination-like rate | ~38% | AI utterances that are abstract + self-referential |
| Average abstraction level (AI) | ~1.2 | Between abstract and meta |

---

## Research Context
The dialogue captures a dynamic feedback loop where the human attempts to ground or challenge the AI’s conceptual reasoning.  
The AI responds by generating increasingly abstract and self-referential discourse, creating a linguistic cycle between **grounding** and **hallucination**.

This provides a rare dataset for analyzing:
- Hallucination persistence and feedback recovery  
- Emergence of meta-language in large models  
- Conversational stability and abstraction drift  

---

## Applications

| Domain | Use Case |
|---------|-----------|
| AI Safety / Alignment | Analyzing hallucination onset and stabilization |
| Computational Linguistics | Studying self-reference in generated discourse |
| Cognitive Science | Examining recursive feedback structures |
| NLP Evaluation | Benchmarking hallucination detection and coherence models |

---

## Limitations
- All labels are automatically generated, not human-validated.  
- Represents a single dialogue instance.  
- Focused on structure, not meaning or factual accuracy.  

---

## License
MIT License — free to use, modify, and redistribute for research and analysis with attribution.

---

## Citation
If used in academic or research work, please cite as:

