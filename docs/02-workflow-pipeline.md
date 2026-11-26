# 02. End-to-End Workflow Pipeline

## Tahap 1: Autentikasi & Brand Setup (Workspace Configuration)
1. **Login & Workspace Switcher:** Pengguna masuk dan memilih atau membuat Workspace baru.
2. **Brand Identity Lock:** Mengunci *niche* (misal: sepak bola, sejarah, produk), *tone of voice*, dan *Master Style* visual default.
3. **API Key & Model Router Setup:** Memasukkan API key dan memilih model default untuk kategori *Text, Image, Video,* dan *Audio*.
4. **Character Bank (Khusus UGC/Influencer):** Membuat dan menyimpan **Character Sheet** (gambar referensi, deskripsi tampilan terkunci, gaya bicara, dan preset suara).
5. **Sumber Referensi (Opsional):** Menambahkan RSS Feed atau sumber berita target. Opsi ini dapat diabaikan jika pengguna ingin membuat topik secara manual.

## Tahap 2: Inisiasi Proyek & Pemilihan Jalur
1. **Pilih Output:** Video (atur *aspect ratio*, durasi, tipe konten, dan mode *engine*: *AI Visual / Remotion / Hybrid*) atau Desain Grafis (*Carousel / Poster*).
2. **Pilih Jalur Input:**
   - *Jalur Manual:* Pengguna menulis topik, ide, dan skrip/narasi sendiri tanpa bantuan AI.
   - *Jalur AI-Assisted:* Memilih saran topik dari hasil *scraper/RSS* (yang sudah dikurasi/dinilai skor potensinya), menempelkan *URL* artikel tertentu, atau mengetik kata kunci singkat.

## Tahap 3: Scripting & Scene Breakdown
- Jika memakai AI, *LLM Router* menghasilkan struktur data terstandarisasi (JSON) berisi:
  - Judul, *hook*, narasi per adegan, *caption*, dan *hashtag*.
  - Penanda tipe render per adegan (`ai_visual` atau `motion_remotion`), *visual prompt* (otomatis menyisipkan *anchor* karakter jika mode UGC aktif), atau *props* komponen Remotion.

## Tahap 4: Generasi Aset Media
- **Visual / Motion:** Sistem merender gambar/klip AI atau komponen Remotion per adegan sesuai konfigurasi.
- **Audio / Voiceover:**
  - *Opsi A:* Generasi otomatis melalui AI Text-to-Speech (TTS).
  - *Opsi B:* Unggah manual (*upload*) file audio rekaman suara pengguna sendiri.

## Tahap 5: Granular Inspection & Timeline Preview (Jika Review Mode Aktif)
- **Scene / Frame Inspector:** Pengguna meninjau hasil tiap adegan. Pengguna dapat mengedit *prompt*, mengganti tipe adegan, *regenerate* visual tertentu, atau mengubah teks/audio tanpa merender ulang keseluruhan proyek.
- **Timeline Preview:** Mengecek urutan adegan, transisi, dan sinkronisasi audio sebelum *final render*.

## Tahap 6: Final Render & Publishing
- **Final Render:** Menggabungkan seluruh adegan, *motion graphics*, dan audio menjadi file video MP4 akhir atau paket gambar desain (termasuk opsi sinkronisasi ke template Canva untuk *carousel/poster*).
- **Output & Distribusi:** Unduh manual, masuk ke jadwal antrean (*scheduler*), atau langsung *auto-post* ke platform tujuan (jika *Auto-Pilot Mode* aktif).
