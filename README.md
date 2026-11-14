# 🤖 Tenantify AI — Backend Rekomendasi & Moderasi NLU

**Tenantify AI** merupakan layanan backend berbasis kecerdasan buatan yang mendukung fitur rekomendasi produk UMKM dan moderasi komentar pada platform Tenantify.

Layanan ini menggunakan pendekatan **Content-Based Filtering** dengan model multilingual `BAAI/bge-m3` dan `FAISS Index` untuk menghasilkan rekomendasi produk yang relevan. Selain itu, tersedia sistem **Natural Language Understanding (NLU)** untuk mengklasifikasikan dan memoderasi komentar pengguna.

## ✨ Fitur Utama

- **Rekomendasi Produk Berbasis AI** — Menghasilkan rekomendasi produk berdasarkan kemiripan semantik menggunakan model multilingual `BAAI/bge-m3`.
- **Semantic Product Search** — Mencari produk berdasarkan pemahaman makna dan konteks teks.
- **Complementary Product Recommendation** — Memberikan rekomendasi produk pelengkap berdasarkan riwayat atau keranjang pesanan.
- **NLU Text Moderation** — Mengklasifikasikan komentar pembeli untuk membantu proses moderasi konten.
- **Batch Comment Moderation** — Memproses beberapa komentar sekaligus dalam satu permintaan API.
- **REST API Integration** — Menyediakan endpoint yang dapat diintegrasikan dengan aplikasi utama Tenantify.

## 🛠️ Teknologi yang Digunakan

| Lapisan | Teknologi |
|---|---|
| Bahasa Pemrograman | Python 3.10 |
| API Interface | Gradio |
| Model Embedding | BAAI/bge-m3 |
| Vector Search | FAISS |
| Metode Rekomendasi | Content-Based Filtering |
| NLP | Natural Language Understanding |
| Deployment | Hugging Face Spaces |

## 🔌 Dokumentasi API

Backend menyediakan beberapa endpoint untuk mendukung integrasi dengan aplikasi utama Tenantify.

| Metode | Endpoint | Deskripsi |
|---|---|---|
| GET | `/docs` | Dokumentasi API Swagger |
| GET | `/health` | Pemeriksaan status layanan |
| GET | `/products` | Mengambil daftar produk |
| GET | `/orders` | Mengambil riwayat pesanan |
| POST | `/recommend/by-product` | Rekomendasi berdasarkan produk pilihan |
| POST | `/recommend/by-order` | Rekomendasi produk pelengkap berdasarkan pesanan |
| POST | `/comments/classify` | Klasifikasi satu komentar pembeli |
| POST | `/comments/moderate-batch` | Moderasi beberapa komentar sekaligus |

## 📂 Struktur Proyek

```text
tenantify-ml-models/
├── data/                    # Dataset dan data pendukung
├── app.py                   # Entry point aplikasi backend
├── main.py                  # Modul utama layanan
├── comment_moderator.py     # Modul moderasi komentar
├── test_nlu_moderator.py    # Pengujian moderasi NLU
├── Tenantify_NLU.ipynb      # Eksperimen dan pengembangan model NLU
├── tenantify_al.py          # Modul pendukung AI
├── requirements.txt         # Daftar dependensi Python
├── .env.example             # Contoh konfigurasi environment
├── API_DOCUMENTATION.md     # Dokumentasi endpoint API
├── DEPLOYMENT.md            # Panduan deployment
└── README.md                # Dokumentasi proyek
```

## ⚙️ Panduan Instalasi & Menjalankan Proyek

### 1. Prasyarat

Pastikan perangkat sudah memiliki:

- Python 3.10
- pip (Python Package Installer)
- Git

### 2. Clone Repository

```bash
git clone <URL_REPOSITORY>
```

Masuk ke direktori proyek:

```bash
cd tenantify-ml-models
```

### 3. Buat Virtual Environment

Buat lingkungan virtual agar dependensi proyek terisolasi dari instalasi Python lainnya.

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**Linux / macOS:**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Instal Dependensi

Instal seluruh dependensi yang dibutuhkan:

```bash
pip install -r requirements.txt
```

### 5. Konfigurasi Environment

Salin file `.env.example` menjadi `.env`.

**Windows:**

```bash
copy .env.example .env
```

**Linux / macOS:**

```bash
cp .env.example .env
```

Sesuaikan nilai konfigurasi berdasarkan kebutuhan aplikasi dan layanan yang digunakan.

### 6. Jalankan Backend

Jalankan aplikasi menggunakan entry point utama:

```bash
python app.py
```

Setelah aplikasi berjalan, akses layanan melalui alamat lokal yang ditampilkan pada terminal.

Dokumentasi API tersedia melalui endpoint `/docs` apabila layanan REST API aktif.

## 🧪 Pengujian

Untuk menjalankan pengujian modul moderasi NLU:

```bash
python test_nlu_moderator.py
```

## 🚀 Deployment

Tenantify AI menggunakan **Hugging Face Spaces** sebagai platform deployment backend.

Konfigurasi deployment menggunakan Gradio SDK dengan Python 3.10 dan `app.py` sebagai entry point aplikasi.

Untuk panduan deployment lebih lanjut, silakan lihat:

- `DEPLOYMENT.md` — Panduan konfigurasi dan deployment.
- `API_DOCUMENTATION.md` — Dokumentasi integrasi API.

## 👥 Penanggung Jawab

**Muhammad Sausan Syafiq - AI Engineer**

---

<p align="center">
  Bagian dari ekosistem <strong>Tenantify</strong>
  <br/>
  Dibuat dengan 🤖 untuk mendukung digitalisasi UMKM.
</p>
