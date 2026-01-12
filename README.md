# Cross-Lingual Sentence Alignment for Indic Languages

This project evaluates the cross-lingual alignment quality of multilingual
sentence embedding models on Indic languages using the FLORES-200 benchmark.

We compare:
- **MiniLM (multilingual)**
- **LaBSE**

across English–Indic language pairs.

---

## Motivation

Multilingual NLP systems often exhibit uneven performance across languages,
especially for low-resource and Global South languages. Sentence embeddings
are a core component of modern NLP pipelines, yet their cross-lingual
alignment quality varies significantly across models.

This project empirically studies how well multilingual sentence embedding
models preserve semantic similarity between English and Indic languages.

---

## Languages Evaluated

- English ↔ Hindi
- English ↔ Gujarati
- English ↔ Urdu
- English ↔ Marathi

---

## Dataset

We use aligned sentence pairs from the **FLORES-200** benchmark.

Dataset source:
- `haoranxu/FLORES-200` (HuggingFace)

Each language pair contains 1,012 professionally translated sentences.
We evaluate on a subset of 200 sentence pairs.

---

## Models

### MiniLM
A lightweight multilingual sentence embedding model trained via knowledge
distillation from larger transformer models.

### LaBSE
A multilingual BERT-based model trained explicitly for cross-lingual
sentence alignment using parallel corpora.

---

## Methodology

For each language pair:
1. Encode English and target-language sentences using a shared embedding model
2. Compute cosine similarity for aligned sentence pairs
3. Report mean cosine similarity as a measure of cross-lingual alignment

---

## Results

LaBSE consistently outperforms MiniLM across all evaluated Indic languages,
with especially large gains for lower-resource languages.

---

## Key Takeaways

- Cross-lingual alignment quality varies significantly across models
- Lightweight models trade off alignment quality for efficiency
- Models explicitly trained on parallel data (LaBSE) perform better on Indic languages

---

## Reproducibility

Install dependencies:
```bash
pip install -r requirements.txt
