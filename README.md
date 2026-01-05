# Text Summarization Portfolio Project (Sumy, Gensim, Summa)

## Project Overview
This project demonstrates **text summarization** using multiple Python libraries and classical extractive algorithms.  
The objective is to extract and summarize the main ideas from an online article and compare outputs across different approaches, then select the **best summary** with a clear justification.

The workflow includes:
1. Web scraping (extracting article text from HTML)
2. Text cleaning and preparation
3. Running multiple summarization algorithms
4. Comparing summaries (length and quality)
5. Producing a final recommendation and saving results to a `.txt` report

---

## What is Text Summarization?
Text summarization is the process of capturing the **most important gist** of a long piece of text.

### Types of Summarization
**Extractive Summarization**
- Selects key sentences from the original text
- Arranges them to form a summary
- Output sentences are taken directly from the source

**Abstractive Summarization**
- Generates new sentences that may not appear in the original text
- Paraphrases and compresses meaning (usually deep learning based)

This project focuses on **extractive** summarization (classical methods), which is lightweight, fast, and suitable for learning core NLP pipeline skills.

---

## Methods Implemented

### Library 1: Sumy (Multiple Algorithms)
Used the following summarizers:
- **TextRank** (graph-based ranking similar to PageRank)
- **LexRank** (graph-based centrality method, commonly used in multi-document contexts)
- **Luhn** (heuristic, frequency-based importance scoring)
- **LSA** (Latent Semantic Analysis, matrix decomposition-based)

### Library 2: Gensim (TextRank Summarization)
- Used `gensim.summarization.summarize()` (available in gensim 3.x)
- Included error handling because Gensim may fail if text is short/noisy

### Library 3: Summa (TextRank)
- Used `summa.summarizer.summarize()`
- Works directly on plain extracted text and produces compact summaries

---

## Data Source (Article)
The summarization target is a Medium article:
- URL: https://medium.com/@subashgandyer/papa-what-is-a-neural-network-c5e5cc427c7

Text was scraped using **BeautifulSoup** by extracting `<p>` paragraph tags.

---

## Implementation Highlights
- Built reusable scraping functions:
  - `get_page(url)` to fetch HTML
  - `collect_text(soup)` to extract readable text
- Generated summaries from:
  - Summa
  - Gensim
  - Sumy (TextRank, LexRank, Luhn, LSA)
- Stored summaries in a Python dictionary for structured comparison
- Wrote all outputs to a final report file:  
  **`summary_comparison.txt`**
  - Includes each method’s summary
  - Includes basic summary stats (approx. word/sentence counts)
  - Ends with a final decision note

---

## Output Files
This project produces two submission-ready files:
1. **Notebook:** `.ipynb`  
   Contains code execution, scraping, summarization, and comparison logic.
2. **Summary Report:** `summary_comparison.txt`  
   Contains summaries for each method + final conclusion.

---

## Final Conclusion (Best Method Selection)
**Chosen Method:** `Summa (TextRank-based)`

**Why Summa was selected**
- Produces a more coherent and compact summary compared to other extractive outputs
- Minimal setup and fewer dependencies than some alternatives
- Works directly on extracted text (no heavy parsing step required)
- Reliable for quick summarization of web articles

Note: In some cases, Gensim may fail due to input constraints (e.g., text cleanliness or length), so Summa was more consistent in execution.

---

## Technologies Used
- Python
- BeautifulSoup4
- Requests
- Sumy
- Summa
- Gensim (3.x)
- NLTK (tokenization support for Sumy workflows)

---

## Skills Demonstrated
- Web scraping and text extraction from HTML
- Text preprocessing for NLP tasks
- Applying and comparing multiple extractive summarization algorithms
- Basic evaluation of outputs (compactness, relevance, coherence)
- Writing automated result reports to `.txt`
- Robust coding practices (try/except fallback handling)

---

## Future Enhancements
- Add automated evaluation metrics such as ROUGE
- Improve text cleaning (remove citations, navigation text, repeated boilerplate)
- Compare against transformer-based abstractive models (BART, T5, PEGASUS)
- Build a small Streamlit app for interactive summarization

---
