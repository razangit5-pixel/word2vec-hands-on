# 🧠 Word2Vec Hands-On — Arabic Word Embeddings

A hands-on implementation of **Word2Vec** for **Arabic text**, featuring both from-scratch training and pre-built embedding models. Built with Gensim and trained using CBOW and Skip-gram architectures on Arabic corpora.

---

## 📁 Repository Structure

```
word2vec-hands-on/
│
├── Word_Embeddings.ipynb           # Main notebook: training Arabic Word2Vec from scratch
├── prebuilt_embrddings_model.ipynb # Notebook: loading and exploring pre-built embeddings
│
├── cbow_arabic.model               # Trained CBOW model (Arabic)
├── cbow_arabic_updated.model       # Updated/refined CBOW model (Arabic)
└── skipgram_arabic.model           # Trained Skip-gram model (Arabic)
```

---

## 📌 Overview

This project covers two complementary approaches to Arabic word embeddings:

1. **Training from scratch** — Build and train CBOW and Skip-gram models on an Arabic corpus using Gensim
2. **Pre-built embeddings** — Load and query existing Arabic embedding models for downstream NLP tasks

Both architectures learn dense vector representations where semantically similar Arabic words cluster together in the embedding space.

---

## ⚙️ Installation

```bash
git clone https://github.com/razangit5-pixel/word2vec-hands-on.git
cd word2vec-hands-on
pip install gensim nltk pyarabic jupyter
```

---

## 🚀 Usage

### Notebook 1 — Train Arabic Word2Vec

```bash
jupyter notebook Word_Embeddings.ipynb
```

Covers training both CBOW and Skip-gram on Arabic text, preprocessing (tokenization, normalization), and saving the trained `.model` files.

### Notebook 2 — Pre-built Embeddings

```bash
jupyter notebook prebuilt_embrddings_model.ipynb
```

Demonstrates loading a pre-trained Arabic embedding model and performing word similarity queries.

### Load a Saved Model

```python
from gensim.models import Word2Vec

# Load trained CBOW model
model = Word2Vec.load("cbow_arabic.model")

# Find similar Arabic words
model.wv.most_similar("ملك", topn=5)

# Word analogy: king - man + woman = ?
model.wv.most_similar(positive=["ملك", "امرأة"], negative=["رجل"], topn=1)
```

---

## 🔍 Models Included

| Model File | Architecture | Language |
|---|---|---|
| `cbow_arabic.model` | CBOW | Arabic 🇸🇦 |
| `cbow_arabic_updated.model` | CBOW (refined) | Arabic 🇸🇦 |
| `skipgram_arabic.model` | Skip-gram | Arabic 🇸🇦 |

**CBOW** predicts a target word from its surrounding context words.  
**Skip-gram** predicts surrounding context words from a given target word — generally better for rare words.

---

## 🌐 Arabic NLP Notes

- Arabic text requires normalization before training (removing diacritics, normalizing Hamza, etc.)
- Tokenization should respect Arabic morphology
- Recommended preprocessing libraries: `pyarabic`, `camel-tools`, or custom regex normalization

---

## 📚 References

- [Mikolov et al. — Efficient Estimation of Word Representations in Vector Space (2013)](https://arxiv.org/abs/1301.3781)
- [Gensim Word2Vec Documentation](https://radimrehurek.com/gensim/models/word2vec.html)

---

## 👩‍💻 Author

**Razan** ([@razangit5-pixel](https://github.com/razangit5-pixel))  
NLP & AI Developer

---

## 📄 License

MIT License
