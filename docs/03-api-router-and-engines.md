# 03. Unified API Router & Rendering Engines

## 1. Arsitektur Multi-Provider API Gateway (BYOK)
Sistem tidak boleh melakukan *hardcode* ke satu vendor AI tertentu. Seluruh pemanggilan melewati lapisan *adapter/gateway* yang membaca konfigurasi API aktif milik *workspace*:

| Kategori | Fungsi Utama | Contoh Provider yang Didukung |
| :--- | :--- | :--- |
| **Text / Brain** | Kurasi berita, *viral scoring*, *scripting*, *scene JSON* | Google Gemini, Anthropic Claude, OpenAI GPT, OpenRouter/Groq |
| **Image Gen** | Ilustrasi adegan, *character sheet* referensi, aset slide | Gemini Multimodal, OpenAI, Fal.ai (Flux/SD), Replicate, ComfyUI |
| **Video Gen** | Klip bergerak sinematik, animasi karakter/B-roll AI | Fal.ai, Replicate, Runway/Luma API, ComfyUI (RunPod) |
| **Audio / TTS** | Narasi otomatis per adegan (selain opsi *upload* manual) | OpenAI TTS, ElevenLabs, Google TTS |

## 2. Engine Rendering Terstruktur
- **Remotion Engine (React-based):** Digunakan untuk merender adegan *motion graphics* (teks animasi, kartu statistik, *infographic*, *lower-third*) dan penggabungan komposisi video berbasis JSON *props*.
- **Canva Connect API (Grafis & Carousel):** Digunakan untuk mengisi data teks/gambar ke dalam template *carousel* atau *poster* yang terstruktur agar tipografi konsisten dan dapat diedit lanjut.
- **Strategi Skalabilitas (Hybrid):** Tahap MVP menggunakan API cloud *pay-as-you-go* untuk mempercepat validasi dengan biaya rendah, dengan jalur migrasi ke *self-hosted* ComfyUI (RunPod) saat volume produksi meningkat.
