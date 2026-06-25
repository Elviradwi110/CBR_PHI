# Case-Based Reasoning (CBR) untuk Putusan Pengadilan Hubungan Industrial (PHI)

## Deskripsi Project
Project ini merupakan implementasi metode Case-Based Reasoning (CBR) untuk melakukan pencarian dan prediksi kasus berdasarkan putusan Pengadilan Hubungan Industrial (PHI) yang diperoleh dari Direktori Putusan Mahkamah Agung Republik Indonesia.

Dataset terdiri dari 33 putusan PHI yang telah diekstraksi dari PDF, dibersihkan, direpresentasikan dalam bentuk teks, dan digunakan untuk proses retrieval serta evaluasi model.

---

## Tahap 1 - Case Base

Tujuan:
- Mengumpulkan putusan PHI
- Ekstraksi PDF ke TXT
- Pembersihan teks

File:
- `01_casebase.py`

Output:
- `data/raw/*.txt`

---

## Tahap 2 - Case Representation

Tujuan:
- Merepresentasikan kasus dalam bentuk terstruktur

File:
- `02_representation.py`
- `02_labeling.py`

Output:
- `data/processed/cases.csv`
- `data/processed/cases_labeled.csv`

Label yang digunakan:
- dikabulkan
- dikabulkan_sebagian
- ditolak
- tidak_diterima

---

## Tahap 3 - Case Retrieval

Metode:
- TF-IDF Vectorization
- Cosine Similarity

File:
- `03_retrieval.py`

Output:
- Top-K kasus yang paling mirip dengan query

---

## Tahap 4 - Case Solution Reuse

Metode:
- Menggunakan hasil retrieval untuk memberikan solusi/prediksi kasus baru

File:
- `04_predict.py`

Output:
- `data/result/predictions.csv`

---

## Tahap 5 - Evaluation

Metode:
- Support Vector Machine (SVM)
- Accuracy
- Precision
- Recall
- F1-Score

File:
- `05_evaluation.py`

Output:
- `data/eval/prediction_metrics.csv`
- `data/eval/retrieval_metrics.csv`

---

## Hasil Evaluasi

Accuracy : 42.86%

Precision : 52.38%

Recall : 42.86%

F1-Score : 35.71%

---

## Struktur Project

```text
CBR_PHI
│
├── README.md
├── 01_casebase.py
├── 02_representation.py
├── 02_labeling.py
├── 03_retrieval.py
├── 04_predict.py
├── 05_evaluation.py
│
├── data
│   ├── pdf
│   ├── raw
│   ├── processed
│   ├── eval
│   └── result
```

## Author

Nama: Elvira Dwi Irianty Woretma

Program Studi: Teknik Informatika

Mata Kuliah: Penalaran komputer