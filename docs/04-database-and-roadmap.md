# 04. Core Data Schema & Development Roadmap

## 1. Entitas Database Inti
- `users` — Data akun pengguna dan autentikasi.
- `workspaces` — Profil Brand (`name`, `niche`, `tone_of_voice`, `logo_url`, `primary_color`, `secondary_color`, `accent_color`, `background_color`, `heading_font`, `body_font`, `execution_mode`: `review` | `autopilot`).
- `workspace_api_keys` — Penyimpanan terenkripsi API key per Brand (`category`: `text` | `image` | `video` | `audio`, `provider`, `model_name`, `api_key`, `is_active`).
- `character_sheets` — Profil karakter konsisten untuk UGC (`workspace_id`, `name`, `reference_images[]`, `appearance_anchor`, `voice_preset`).
- `content_sources` — Daftar RSS feed, sumber berita, atau *URL drop* per Brand.
- `projects` — Unit proyek konten di dalam Brand (`workspace_id`, `content_type`: `carousel` | `poster` | `video_motion_graphics` | `video_stickman` | `video_ugc` | `video_ai_story` | `video_hybrid`, `aspect_ratio`, `duration_or_slides`, `creation_mode`: `ai` | `manual`, `status`).
- `project_scenes` — Daftar adegan/slide berurutan (`project_id`, `order_index`, `render_type`: `ai_visual` | `motion_remotion` | `graphic_slide`, `narration_text`, `visual_prompt`, `remotion_props`, `asset_url`, `audio_url`).

## 2. Roadmap Pengembangan Bertahap

### Fase 1: Foundation & Brand Workspace Setup
- Inisialisasi struktur proyek (*Frontend* Next.js/React + *Backend* Python FastAPI + Database).
- Sistem autentikasi, pembuatan *Brand Workspace*, pengaturan **Brand Identity / Brand Kit** (logo, palet warna, tipografi), dan manajemen *Multi-Provider API Key*.

### Fase 2: Content Type Picker & Core Content Pipeline (MVP)
- Halaman pembuatan proyek berbasis **Content Type Picker** (pilihan kartu jenis konten yang tinggal diklik di dalam Brand).
- Modul input ide (Manual, *URL drop*, dan RSS dasar).
- Integrasi *LLM Router* (Gemini/Claude/OpenAI) untuk menghasilkan skrip dan struktur `project_scenes` yang terhubung dengan **Brand Kit**.
- Generasi visual awal (gambar/slide) & audio (TTS + *upload* manual) serta **Scene / Slide Inspector** untuk edit per adegan/slide.

### Fase 3: Remotion Motion Graphics & Video Assembly
- Integrasi template **Remotion** untuk *motion graphics* (otomatis membaca warna, font, dan logo dari **Brand Kit**) serta mode *hybrid*.
- *Timeline preview* & penyusunan klip sebelum *final render*, dan ekspor video MP4 lengkap dengan opsi *Review Mode* vs *Auto-Pilot Mode*.

### Fase 4: UGC Character Sheet, Desain Grafis Lanjutan & Auto-Publishing
- Implementasi penuh **Character Sheet** untuk konsistensi karakter UGC.
- Integrasi lanjut template *Carousel/Poster* (termasuk Canva Connect API).
- Penjadwalan (*scheduler*) dan publikasi otomatis ke platform media sosial.
