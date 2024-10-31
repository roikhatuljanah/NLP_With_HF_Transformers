<h1 align="center"> NLP With HuggingFace Transformers </h1>
<p align="center"> Berisi tentang pipeline dari HuggingFace Transformers untuk keperluan NLP (Natural Language Processing)</p>

<div align="center">

<img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54">
<img src="https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white">

</div>

<h2 align="center"> Analisis </h2> 
Proyek ini menggunakan model dari library transformers untuk melakukan analisis teks menggunakan dua metode utama: Zero-Shot Classification dan Question Answering. Dengan proyek ini, Anda dapat mengklasifikasikan teks ke dalam kategori yang ditentukan tanpa memerlukan data pelatihan dan menjawab pertanyaan berdasarkan konteks yang diberikan.

## Fitur

- **Zero-Shot Classification**: Mengklasifikasikan teks ke dalam kategori yang telah ditentukan tanpa memerlukan data pelatihan.
- **Question Answering**: Menjawab pertanyaan spesifik berdasarkan konteks yang diberikan.

## Instalasi

1. Clone repositori ini ke komputer Anda:
   ```bash
   git clone <URL_REPOSITORI>
   cd <NAMA_REPOSITORI>
   ```

2. Install dependensi yang diperlukan:
   ```bash
   pip install transformers torch
   ```

## Penggunaan

### Zero-Shot Classification

Anda dapat menggunakan zero-shot classification untuk mengklasifikasikan teks dengan model berikut:

```python
from transformers import pipeline

classifier = pipeline("zero-shot-classification")
result = classifier(
    "Teks yang ingin Anda klasifikasikan.",
    candidate_labels=["label1", "label2", "label3"]
)
print(result)
```

### Question Answering

Untuk menjawab pertanyaan berdasarkan konteks, gunakan kode berikut:

```python
from transformers import pipeline

qa_pipeline = pipeline("question-answering")
context = "Teks konteks yang berisi informasi."
question = "Pertanyaan yang ingin diajukan."
result = qa_pipeline(question=question, context=context)
print(result['answer'])
```

## Contoh

### Zero-Shot Classification

Misalnya, jika Anda ingin mengklasifikasikan pernyataan berikut:

```python
result = classifier("Ini adalah kursus tentang pemrograman Python.", candidate_labels=["pendidikan", "bisnis", "teknologi"])
```

### Question Answering

Untuk menjawab pertanyaan tentang informasi tertentu:

```python
context = "Albert Einstein (lahir 14 Maret 1879) adalah fisikawan teoretis yang dikenal dengan teori relativitas."
question = "Kapan Albert Einstein lahir?"
result = qa_pipeline(question=question, context=context)
print(result['answer'])
```
