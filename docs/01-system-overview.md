# 01. System Overview & Core Specifications

## 1. Visi Produk
Membangun aplikasi web **AI-Powered Content Agency Platform** yang mampu mengelola berbagai brand atau klien secara paralel dalam satu dashboard. Sistem menggabungkan kecepatan otomasi AI dengan presisi kontrol manusia (*Human-in-the-Loop*) agar output tetap konsisten, tajam, dan siap tayang.

## 2. Prinsip Utama Sistem
- **Multi-Tenant Brand Workspace:** Pemisahan penuh antar brand/akun (identitas brand, aset, karakter, dan API key tidak saling tercampur). Satu Brand tidak dikunci ke satu jenis konten tunggal, melainkan bebas membuat berbagai jenis video maupun desain grafis.
- **Brand Identity / Brand Kit:** Setiap Brand menyimpan standar identitas visual tetap (logo, palet warna, dan tipografi) agar konsisten di seluruh desain grafis maupun motion graphics.
- **Flexible Creation Mode:** Mendukung jalur **AI-Assisted** maupun **Manual Full-Control** (tanpa AI).
- **Execution Control (Review vs. Auto-Pilot):**
  - *Review Mode:* Pengguna dapat memeriksa dan mengedit aset per adegan/slide (*frame-by-frame*) serta mengecek *timeline* sebelum *final render*.
  - *Auto-Pilot Mode:* Sistem menjalankan seluruh alur otomatis hingga *render* dan *auto-schedule/auto-post* (dengan *guardrail* per workspace).
- **Model & Vendor Agnostic:** Semua penyedia AI (Claude, Gemini, OpenAI, Fal.ai, Replicate, dll.) dapat ditukar kapan saja menggunakan mekanisme *Bring Your Own Key (BYOK)*.

## 3. Jenis Konten yang Didukung (Content Type Picker)

### A. Video
1. **Video AI Story / Edukasi:** Video pendek (9:16) maupun panjang (16:9) dengan gaya visual berbasis AI (*realistic, cartoon, anime*, dll.).
2. **Video Stickman:** Video narasi/edukasi bergaya ilustrasi *stickman* yang ekspresif.
3. **Video Motion Graphics (Remotion):** Video berbasis komponen React untuk teks dinamis, statistik, *comparison*, *infographic*, dan *timeline* yang mengikuti **Brand Kit** (warna, font, logo).
4. **Video Hybrid (AI Visual + Remotion):** Menggabungkan adegan visual AI dan *motion graphics* dalam satu *timeline* yang sama.
5. **Video UGC / Influencer:** Video gaya kreator kasual dengan fitur **Character Sheet** untuk menjaga konsistensi wajah, pakaian, dan gaya karakter di seluruh adegan maupun antar video.

### B. Desain Grafis
1. **Carousel (Multi-Slide):** Rangkaian slide edukasi, daftar fakta, atau *storytelling* berurutan yang konsisten dengan **Brand Kit**.
2. **Poster / Single Graphic:** Desain satu lembar untuk pengumuman, kutipan, promosi, atau *cover*.
