# 01. System Overview & Core Specifications

## 1. Visi Produk
Membangun aplikasi web **AI-Powered Content Agency Platform** yang mampu mengelola berbagai brand atau klien secara paralel dalam satu dashboard. Sistem menggabungkan kecepatan otomasi AI dengan presisi kontrol manusia (*Human-in-the-Loop*) agar output tetap konsisten, tajam, dan siap tayang.

## 2. Prinsip Utama Sistem
- **Multi-Tenant Workspace:** Pemisahan penuh antar brand/akun (data, aturan niche, style visual, karakter, dan API key tidak saling tercampur).
- **Flexible Creation Mode:** Mendukung jalur **AI-Assisted** maupun **Manual Full-Control** (tanpa AI).
- **Execution Control (Review vs. Auto-Pilot):**
  - *Review Mode:* Pengguna dapat memeriksa dan mengedit aset per adegan (*frame-by-frame*) serta mengecek *timeline* sebelum *final render*.
  - *Auto-Pilot Mode:* Sistem menjalankan seluruh alur otomatis hingga *render* dan *auto-schedule/auto-post* (dengan *guardrail* per workspace).
- **Model & Vendor Agnostic:** Semua penyedia AI (Claude, Gemini, OpenAI, Fal.ai, Replicate, dll.) dapat ditukar kapan saja menggunakan mekanisme *Bring Your Own Key (BYOK)*.

## 3. Jenis Konten yang Didukung

### A. Video
1. **Edukasi, Fakta & Storytelling:** Video pendek (9:16) maupun panjang (16:9) dengan pilihan gaya visual (*realistic, cartoon, anime, stickman*, dll.).
2. **Motion Graphics Video (Remotion):** Video berbasis komponen React untuk teks dinamis, statistik, *comparison*, *infographic*, dan *timeline* yang presisi tanpa *glitch* visual acak.
3. **Hybrid Video (AI Visual + Remotion):** Menggabungkan adegan visual AI dan *motion graphics* dalam satu *timeline* yang sama.
4. **UGC / Influencer Video Mode:** Video gaya kreator kasual dengan fitur **Character Sheet** untuk menjaga konsistensi wajah, pakaian, dan gaya karakter di seluruh adegan maupun antar video.

### B. Desain Grafis
1. **Carousel (Multi-Slide):** Rangkaian slide edukasi, daftar fakta, atau *storytelling* berurutan.
2. **Poster / Single Graphic:** Desain satu lembar untuk pengumuman, kutipan, promosi, atau *cover*.
