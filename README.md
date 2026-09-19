# RAG-Benchmark-Lab

*Hands-on, empirical benchmarks for every stage of a RAG pipeline — one lab, one component at a time.*

![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg)

## About

Most RAG tutorials tell you *what* a component does. This repo is about testing *how well it actually works* — with real-world documents, real numbers, and side-by-side comparisons you can reproduce yourself.

Each lab in this series picks one stage of a RAG pipeline (document parsing, chunking, embedding, retrieval, and so on), benchmarks the most commonly used tools for it, and documents the results in an accompanying article. This repo holds the code: the notebooks, the raw outputs, and everything needed to rerun the tests on your own documents.

Written to accompany a series of articles on [Medium](#) — link to each lab's article is in the table below.

## 📚 Series Roadmap

| Lab | Topic | Status | Article | Code |
|---|---|---|---|---|
| 01 | Document Parsing (PyMuPDF vs Docling vs LlamaParse vs Landing.AI DPT) | ✅ Published | [Read on Medium](#) | [`01-document-parsing/`](./01-document-parsing) |
| 02 | Text Splitting & Chunking Strategies | 🚧 In progress | — | [`02-text-splitter/`](./02-text-splitter) |
| 03+ | TBD | 🗓️ Planned | — | — |

**Note:** the exact order and scope of Lab 03 onward is still being decided. Candidate topics under consideration (not committed, subject to change):

- Embedding model comparison (retrieval quality vs cost vs latency)
- Vector database / retrieval benchmark (similarity search accuracy, speed at scale)
- Reranking strategies
- Chunk size & overlap sensitivity analysis
- End-to-end RAG evaluation (answer quality, faithfulness, hallucination rate)

Suggestions and requests are welcome — feel free to open an [issue](../../issues) if there's a component you'd like to see benchmarked.

## 🗂️ Repo Structure

Each lab lives in its own numbered folder, self-contained with its own notebook and outputs:

```
RAG-Benchmark-Lab/
├── 01-document-parsing/
│   ├── document_parsing_benchmark.ipynb
│   └── outputs/              # parsed results per tool (.md / .txt)
├── 02-text-splitter/
│   └── ...                   # coming soon
├── LICENSE
└── README.md
```

## 🚀 Running the Labs

Every notebook in this repo is written to run in **both Google Colab and local Jupyter** without modification — it auto-detects the environment and adjusts accordingly (Drive mounting and Colab Secrets in Colab; a local `.env` file and local output folder outside Colab).

**Option A — Google Colab (fastest, no setup)**
Click the badge in each lab's folder, or open directly:
`https://colab.research.google.com/github/Supra-San/RAG-Benchmark-Lab/blob/main/<lab-folder>/<notebook>.ipynb`

**Option B — Local Jupyter**
```bash
git clone https://github.com/Supra-San/RAG-Benchmark-Lab.git
cd RAG-Benchmark-Lab/01-document-parsing
pip install -r requirements.txt   # or run the install cell inside the notebook
jupyter notebook
```
Create a `.env` file in the lab's folder with any required API keys, e.g.:
```
LLAMA_PARSE_API_KEY=your-key-here
DPT_APIKEY=your-key-here
```

## 🛠️ Tools Covered So Far

| Category | Tools |
|---|---|
| Document Parsing | PyMuPDF, Docling, LlamaParse, Landing.AI DPT |

This list grows with each new lab — see the roadmap above.

## 🤝 Connect

This repo is maintained alongside a Medium article series. If you found it useful:

- **Read the articles:** [Medium](#)
- **Connect:** [LinkedIn](#)

Feedback, corrections, and PRs are welcome — especially if you spot something that could make a benchmark fairer or more reproducible.

## 📄 License

Code in this repo is licensed under [Apache-2.0](./LICENSE). Article text and figures (published separately on Medium) are licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) unless noted otherwise.
