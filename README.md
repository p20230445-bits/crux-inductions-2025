# CRUx Inductions 2025 — Task 1 & Task 2

This repository contains my solutions for CRUx Inductions 2025:

- **Task 1:** Classification on **Iris**
  - **(A) MLP from scratch**
  - **(B) KAN using the PyKAN library**
  - Short comparison of results
- **Task 2:** **MAMBA-style** sentiment classifier on **IMDb** with **early stopping**

All code is in the `notebooks/` folder. Each notebook is self-contained and runnable end-to-end.

---

## Open in Colab

> Replace `p20230445-bits` with your GitHub username.

- **Task 1A – MLP from scratch**  
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/p20230445-bits/crux-inductions-2025/blob/main/notebooks/Task1_MLP.ipynb)

- **Task 1B – KAN (PyKAN)**  
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/p20230445-bits/crux-inductions-2025/blob/main/notebooks/Task1_KAN.ipynb)

- **Task 2 – MAMBA sentiment classification (IMDb)**  
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/p20230445-bits/crux-inductions-2025/blob/main/notebooks/Task2_MAMBA_sentiment_classification.ipynb)

---

## Results

| Task | Dataset | Metric | Result |
|---|---|---:|---:|
| **Task 1A – MLP (from scratch)** | Iris | 5-fold CV accuracy (mean) | **0.9733** |
| **Task 1B – KAN (PyKAN)** | Iris | Test accuracy (single split) | **0.9333** |
| **Task 2 – MAMBA-style (PyTorch)** | IMDb | Test accuracy | **0.7959** |

---

## Repository structure
├─ notebooks/

│ ├─ Task1_MLP.ipynb

│ ├─ Task1_KAN.ipynb

│ └─ Task2_MAMBA_sentiment_classification.ipynb

├─ README.md

└─ requirements.txt

---

## How to run (Colab)

Colab is the simplest route; just open each notebook with the badge above and **Runtime → Run all**.  

Notes per task:

- **Task 1A – MLP from scratch (Iris)**  
  Pure NumPy/PyTorch basics; no special installs.

- **Task 1B – KAN using PyKAN (Iris)**  
  Clones PyKAN and trains with `model.fit(dataset, ...)`.

- **Task 2 – MAMBA-style sentiment classifier (IMDb)**  
  Uses Hugging Face `datasets` to load IMDb. Implements a simplified MAMBA block in pure PyTorch. Early stopping on validation accuracy.

---

## How to run (local)

Create a fresh virtual environment and install dependencies:

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install torch datasets scikit-learn matplotlib numpy tqdm

# For Task 1B (PyKAN)
git clone https://github.com/KindXiaoming/pykan.git
pip install -e pykan
```
---

## Repro tips

GPU: In Colab, set Runtime → Change runtime type → GPU.

Speed: For Task 2, use smaller MAX_LEN or fewer samples for quick tests.

Determinism: A fixed SEED=42 is used where applicable.

## Notebook details

Task1_MLP.ipynb — Implements MLP from scratch, 5-fold CV, mean accuracy ≈ 0.9733.

Task1_KAN.ipynb — Implements KAN using PyKAN on Iris, test accuracy ≈ 0.9333.

Task2_MAMBA_sentiment_classification.ipynb — Simplified MAMBA block for IMDb sentiment classification, test accuracy ≈ 0.7959.

## License

This repository is for CRUx Inductions 2025 evaluation. Code is for educational purposes.
