# 02. End-to-End Workflow Pipeline

## Tahap 1: Autentikasi & Brand Setup (Workspace & Brand Kit)
1. **Login & Brand Switcher:** Pengguna masuk dan memilih atau membuat Brand (Workspace) baru.
2. **Brand Identity (Brand Kit):** Mengatur identitas komunikasi (*niche*, *tone of voice*) serta standar visual tetap milik Brand:
   - Logo Brand (`logo_url`)
   - Palet Warna (`primary_color`, `secondary_color`, `accent_color`, `background_color`)
   - Tipografi (`heading_font`, `body_font`)
3. **API Key & Model Router Setup:** Memasukkan API key dan memilih model default untuk kategori *Text, Image, Video,* dan *Audio*.
4. **Character Bank (Khusus UGC/Influencer):** Membuat dan menyimpan **Character Sheet** (gambar referensi, deskripsi tampilan terkunci, gaya bicara, dan preset suara).
5. **Sumber Referensi (Opsional):** Menambahkan RSS Feed atau sumber berita target. Opsi ini dapat diabaikan jika pengguna ingin menulis topik secara manual.

## Tahap 2: Pembuatan Proyek via Content Type Picker
1. **Pilih Kartu Jenis Konten:** Di dalam Brand, pengguna mengklik langsung jenis konten yang ingin dibuat (`Carousel`, `Poster`, `Video Motion Graphics`, `Video Stickman`, `Video UGC`, `Video AI Story`, atau `Video Hybrid`).
2. **Konfigurasi Spesifik Proyek:** Formulir otomatis menyesuaikan jenis konten yang diklik (atur *aspect ratio*, durasi video atau jumlah *slide* carousel, serta mode eksekusi *Review* vs *Auto-Pilot*).
3. **Pilih Jalur Input:**
   - *Jalur Manual:* Pengguna menulis topik, ide, dan skrip/isi slide sendiri tanpa bantuan AI.
   - *Jalur AI-Assisted:* Memilih saran topik dari hasil *scraper/RSS* (yang sudah dikurasi/dinilai skor potensinya), menempelkan *URL* artikel tertentu, atau mengetik kata kunci singkat.

## Tahap 3: Scripting & Scene / Slide Breakdown
- Jika memakai AI, *LLM Router* menghasilkan struktur data terstandarisasi (JSON) berisi:
  - Judul, *hook*, narasi/teks per adegan atau *slide*, *caption*, dan *hashtag*.
  - Penanda tipe render per adegan (`ai_visual`, `motion_remotion`, atau `graphic_slide`), *visual prompt* (otomatis menyisipkan *anchor* karakter jika mode UGC aktif), serta referensi **Brand Kit** (warna, font, logo).

## Tahap 4: Generasi Aset Media
- **Visual / Motion / Slide:** Sistem merender gambar/klip AI, komponen Remotion, atau draf *slide* grafis sesuai konfigurasi proyek dan **Brand Kit**.
- **Audio / Voiceover (Untuk Video):**
  - *Opsi A:* Generasi otomatis melalui AI Text-to-Speech (TTS).
  - *Opsi B:* Unggah manual (*upload*) file audio rekaman suara pengguna sendiri.

## Tahap 5: Granular Inspection & Timeline Preview (Jika Review Mode Aktif)
- **Scene / Slide Inspector:** Pengguna meninjau hasil tiap adegan atau *slide*. Pengguna dapat mengedit teks, *prompt*, mengganti tipe adegan, *regenerate* visual tertentu, atau memperbarui audio tanpa merender ulang keseluruhan proyek.
- **Timeline Preview:** Mengecek urutan adegan, pemotongan/penyesuaian klip, transisi, dan sinkronisasi audio sebelum *final render*.

## Tahap 6: Final Render & Publishing
- **Final Render:** Menggabungkan seluruh adegan, *motion graphics*, dan audio menjadi file video MP4 akhir atau paket gambar desain (termasuk opsi sinkronisasi ke template Canva untuk *carousel/poster*).
- **Output & Distribusi:** Unduh manual, masuk ke jadwal antrean (*scheduler*), atau langsung *auto-post* ke platform tujuan (jika *Auto-Pilot Mode* aktif).
