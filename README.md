# 🎓 EduBantu AI - Generator Modul Ajar & Soal Adaptif Kurikulum Merdeka

**EduBantu AI** adalah aplikasi web interaktif yang dirancang untuk membantu pendidik/guru merancang **Modul Ajar (RPP)**, **Ringkasan Materi Ajar**, dan **Bank Soal Adaptif** berstandar Kurikulum Merdeka secara otomatis.

Aplikasi ini dilengkapi dengan penulisan notasi matematika presisi tinggi menggunakan **KaTeX/LaTeX**, pratinjau responsif multi-tab, serta fitur ekspor dokumen ke **PDF** yang rapi.

---

## 🚀 Fitur Utama

- 📋 **Generator Modul Ajar (RPP)**: Menyusun Identitas Umum, Capaian Pembelajaran (CP), Tujuan Pembelajaran (TP), hingga Alokasi Waktu.
- 📖 **Ringkasan Materi Ajar**: Menyajikan ringkasan materi pembelajaran yang sistematis dan mudah dipahami sesuai tingkat pemahaman siswa (*Perlu Bimbingan*, *Standar*, atau *Mahir*).
- ❓ **Bank Soal & Pembahasan Adaptif**: Menggenerasi soal bertingkat (*Easy*, *Medium*, *HOTS*) lengkap dengan Kunci Jawaban dan Pembahasan.
- 📐 **Dukungan Formula Matematika (KaTeX)**: Rendering simbol dan persamaan matematika yang presisi.
- 📄 **Ekspor PDF Langsung**: Mengunduh seluruh dokumen hasil generasi ke dalam format PDF dalam sekali klik.
- ⚡ **Fallback Mock Data Mode**: Tetap dapat diuji dan digunakan secara penuh meskipun koneksi backend API sedang offline.

---

## 🛠️ Arsitektur Proyek

- **Frontend**: React.js, Tailwind CSS, `react-markdown`, `rehype-katex`, `html2pdf.js`
- **Backend / AI Orchestration**: Langflow (Google Gemini API / LLM)

---




Panduan Menjalankan Proyek di Lokal
1. Import Flow Backend ke Langflow
   
Buka aplikasi Langflow (Lokal / Desktop / Cloud Instance Anda).

Klik tombol New Flow -> Import / Upload.

Pilih berkas edubantu-langflow-flow.json. (ada di repository ini)

Buka flow yang telah di-import, lalu masukkan Google Gemini API Key  pada node Google Generative AI.

Jalankan (Run) flow untuk memastikan koneksi backend siap.

2. Menjalankan Frontend React
Buka terminal/command prompt, lalu masuk ke folder frontend React:

Bash
cd edubantu-ai
Unduh dan pasang seluruh dependensi project:

Bash
npm install
Buat file .env di dalam folder edubantu-ai (dapat menyalin dari .env.example):

Cuplikan kode
REACT_APP_LANGFLOW_URL=http://localhost:7860/api/v1/run/YOUR_FLOW_ID?stream=false
REACT_APP_LANGFLOW_API_KEY=your_langflow_api_key_here
(Catatan: Jika .env tidak diisi, aplikasi akan secara otomatis menggunakan Mock Data Mode untuk kebutuhan pengujian UI).

Jalankan aplikasi web:

Bash
npm start
Buka browser dan akses alamat http://localhost:3000.
