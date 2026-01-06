# Skip-gram with Negative Sampling on Wikipedia

This project implements **Skip-gram with Negative Sampling (SGNS)** from scratch and trains it on a Wikipedia text dump.  
It compares the learned word embeddings with **Gensim's Word2Vec** using **cosine similarity**, evaluates them on **word analogy tasks**, and analyzes **bias in word embeddings**.

---

## 📌 Objectives

- Implement Skip-gram with Negative Sampling from scratch
- Train embeddings on Wikipedia (enwik8)
- Train Gensim Word2Vec for comparison
- Compare both embeddings using cosine similarity
- Evaluate word analogies (e.g., `king - man + woman ≈ queen`)
- Detect and analyze bias in word embeddings

---

## 📚 Dataset

- **Wikipedia dump:** enwik8  
  Source: http://mattmahoney.net/dc/textdata.html  
- The dataset is downloaded automatically inside the notebook.

---

## 🧠 Methodology

### Skip-gram with Negative Sampling (SGNS)

- For each target word, predict surrounding context words
- Use **negative sampling** to sample incorrect context words
- Train two embedding matrices: target and context
- Optimize using stochastic gradient descent

### Gensim Word2Vec

- Trained using the same settings (Skip-gram, negative sampling, same window size and dimension)
- Used as a strong baseline for comparison

---

## 📐 Evaluation

### 1. Cosine Similarity Comparison
- Compare vectors from:
  - Our implementation
  - Gensim Word2Vec
- Check similarity structure and nearest neighbors

### 2. Word Analogy Task
Examples:
```

king - man + woman ≈ queen
paris - france + italy ≈ rome

```
- Implemented using the vector parallelogram method

### 3. Bias Detection
- Define **gender direction** using:
```

he - she, man - woman, male - female

```
- Measure bias of words like:
```

doctor, nurse, engineer, teacher, programmer, homemaker

````
- Show that embeddings capture societal biases from data

---

## 🛠️ Tech Stack

- Python
- PyTorch
- Gensim
- NumPy
- Matplotlib
- Jupyter Notebook

---

## 🚀 How to Run

### Option 1: Run on Google Colab (Recommended)

1. Upload `skipgram_wikipedia.ipynb` to Colab
2. Run all cells

The dataset will be downloaded automatically.

---

### Option 2: Run Locally

```bash
pip install -r requirements.txt
jupyter notebook
````

Then open:

```
skipgram_wikipedia.ipynb
```

---

## 📁 Project Structure

```
skipgram-wikipedia/
│
├── skipgram_wikipedia.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

## ⚠️ Notes

* The Wikipedia dataset is **not included** in the repository (too large)
* It is downloaded automatically when running the notebook
* Uses **enwik8 (100MB)** for practical training time

---

## 📊 Results

* Skip-gram embeddings show meaningful semantic structure
* Gensim embeddings perform better due to more optimized training
* Both models show **clear gender bias**, confirming that embeddings reflect societal data bias

---

## 🧠 Key Takeaways

* Word meaning can be represented as vectors using distributional semantics
* Skip-gram with Negative Sampling learns embeddings by prediction, not counting
* Vector arithmetic enables analogical reasoning
* Embeddings **learn social biases** present in training data

---

## 📖 References

* Mikolov et al., *Efficient Estimation of Word Representations in Vector Space*
* Jurafsky & Martin, *Speech and Language Processing*, Chapter 5
* Stanford CS224N: Vector Semantics & Word Embeddings
* [https://radimrehurek.com/gensim/models/word2vec.html](https://radimrehurek.com/gensim/models/word2vec.html)

---

## 🛡 License

This project is licensed under the [MIT License](LICENSE).  
You are free to use, modify, and distribute this code with attribution.

---

## Author

**Adithya Sai Srinivas**
📧 muttaadithyasaisrinivas@gmail.com  
🌐 [Portfolio](https://adithya369.pages.dev) • [LinkedIn](https://linkedin.com/in/adithyasaisrinivas)
