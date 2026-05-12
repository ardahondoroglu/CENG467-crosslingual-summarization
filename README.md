# CENG467-crosslingual-summarization
# Cross-Lingual Abstractive Summarization (EN → TR)
**CENG 467 — Natural Language Understanding and Generation**  
**Group Members:** Arda Hondoroğlu, Sinan İnce

## Task
Given an English article, generate a fluent Turkish summary.

## Dataset
WikiLingua (English subset) — wikiHow articles with EN summaries.  
Since no aligned EN-TR pairs exist, EN summaries are translated to Turkish via MarianMT as evaluation references.

## Baselines

| Baseline | Approach | ROUGE-L |
|----------|----------|---------|
| Baseline 1 | EN article → mT5 (EN summary) → MarianMT (TR) | 10.01 |
| Baseline 2 | EN article → MarianMT (TR text) → mT5 (TR summary) | 13.15 |

## Repository Structure

├── notebooks/

│   └── CENG467_CrossLingual_Summarization.ipynb

├── results/

│   └── results.json

├── README.md

└── requirements.txt

## Models Used
- `csebuetnlp/mT5_multilingual_XLSum` — multilingual summarization
- `Helsinki-NLP/opus-mt-tc-big-en-tr` — English to Turkish translation

## Evaluation
- Metric: ROUGE-1, ROUGE-2, ROUGE-L
- Test set: 20 examples from WikiLingua EN
- References: EN summaries translated to TR via MarianMT
