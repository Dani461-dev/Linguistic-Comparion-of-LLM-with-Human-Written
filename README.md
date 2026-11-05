# Linguistic-Comparion-of-LLM-with-Human-Written
## Human vs LLM-Assisted Academic Writing

Analisis linguistik esai akademik berbahasa Inggris yang ditulis mahasiswa dengan dan tanpa bantuan Large Language Model (LLM). Proyek ini membandingkan empat kondisi penggunaan LLM pada tugas esai *Ensemble Learning* (Machine Learning II) menggunakan metrik corpus linguistics.

**Pertanyaan penelitian:** apa perbedaan fitur linguistik antara academic writing yang ditulis mahasiswa dan yang dihasilkan atau dibantu LLM, dan apa implikasinya terhadap pengajaran English for Academic Purposes (EAP)?

## Kategori data

| Kode | Kondisi | Keterangan |
|---|---|---|
| **H** | Human | Ditulis sendiri dari sumber web, tanpa LLM |
| **L1** | LLM untuk ide | LLM dipakai untuk mencari ide dan informasi (Claude) |
| **L2** | LLM untuk translate-paraphrase | Teks diterjemahkan dan diparafrasekan dengan LLM (Claude, ChatGPT) |
| **L3** | Satu prompt | Seluruh esai dihasilkan dari satu prompt (ChatGPT) |

Tahap A menganalisis empat esai utama, satu per kategori. Tahap B memakai 19 esai berbahasa Inggris dari tugas yang sama dengan esai sebagai unit analisis (H = 2, L1 = 9, L2 = 7, L3 = 1). Esai berbahasa Indonesia tidak diukur karena semua metrik dirancang untuk teks bahasa Inggris.

## Metrik yang diukur

| Dimensi | Metrik |
|---|---|
| Lexical diversity | TTR, MTLD (McCarthy & Jarvis, 2010), MATTR |
| Syntactic complexity | Rata-rata panjang kalimat, SD panjang kalimat, klausa subordinat per kalimat |
| Cohesion | Connective density per 100 kata, lexical overlap antar kalimat berurutan |
| Academic vocabulary | Cakupan Academic Word List (AWL) |
| Accuracy | Surface errors per 100 kata |
| Diction | Kata penanda LLM (core dan extended) per 1000 kata |
| Content | Cakupan subtopik dan kemiripan semantik antar esai |

## Temuan utama

Beberapa pola yang paling konsisten pada empat esai Tahap A:

- **Panjang kalimat L3 paling seragam.** SD panjang kalimat L3 = 2,6 kata, sedangkan kategori lain 6,5 sampai 13,3 kata (Brown-Forsythe p < 0,001).
- **Lexical overlap antar kalimat berurutan lebih tinggi pada H dan L1** dibanding L2 dan L3 (Welch ANOVA p = 0,004; kontras p < 0,001).
- **Kesalahan permukaan hanya ditemukan pada H**, meskipun jumlahnya terlalu kecil untuk diuji secara inferensial.
- **Lexical diversity L2 dan L3 lebih tinggi** daripada H dan L1, tetapi hanya satu nilai per esai sehingga tidak bisa diuji dengan ANOVA.

Pada Tahap B, arah beberapa temuan bertahan, tetapi tidak signifikan setelah koreksi Holm. Panjang kalimat tetap merupakan ciri esai yang paling stabil, sedangkan connective density dan kata penanda LLM tidak stabil. Dengan jumlah esai per kategori yang masih sedikit, hasil ini berlaku untuk korpus yang dianalisis dan belum bisa digeneralisasi.

## Struktur repositori

```
.
├── iceap.ipynb                   # Analisis utama: Tahap A (4 esai) + Tahap B (19 esai)
├── awl.txt                       # Daftar Academic Word List
├── awl_families.csv              # Word family untuk pencocokan AWL


## Catatan metodologis dan limitasi

- Tahap A memakai **n = 1 per kategori**, sehingga perbedaan bisa berasal dari gaya penulis, bukan tingkat penggunaan LLM. Hasil dibaca sebagai pola, bukan bukti kausal.
- Tool LLM berbeda antar kategori (Claude dan ChatGPT), sehingga menambah variasi yang tidak terkontrol.
- MTLD pada teks sekitar 235 kata rapuh, walaupun masih di atas batas minimal yang umum dipakai.
- Klausa subordinat dihitung dari label dependency parser spaCy, sehingga masih mungkin mengandung error parsing.
- Connective dan kata penanda LLM dihitung berbasis daftar, sehingga hasilnya bergantung pada daftar yang dipilih.
- Metrik yang dipakai tidak mengukur kualitas idea development, text organisation, atau kemampuan evaluating dan editing.

## Etika data dan privasi

Repositori ini memakai esai mahasiswa sebagai data. 
