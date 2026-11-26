# 04. Core Data Schema & Development Roadmap

## 1. Entitas Database Inti
- `users` — Data akun pengguna dan autentikasi.
- `workspaces` — Profil brand/klien (`name`, `niche`, `tone_of_voice`, `default_visual_style`, `execution_mode`: `review` | `autopilot`).
- `workspace_api_keys` — Penyimpanan terenkripsi API key per workspace (`category`: `text` | `image` | `video` | `audio`, `provider`, `model_name`, `api_key`, `is_active`).
- `character_sheets` — Profil karakter konsisten untuk UGC (`workspace_id`, `name`, `reference_images[]`, `appearance_anchor`, `voice_preset`).
- `content_sources` — Daftar RSS feed, sumber berita, atau *URL drop* per workspace.
- `projects` — Unit proyek konten (`workspace_id`, `media_type`: `video` | `design`, `sub_type`, `aspect_ratio`, `creation_mode`: `ai` | `manual`, `status`).
- `project_scenes` — Daftar adegan/slide berurutan (`project_id`, `order_index`, `render_type`: `ai_visual` | `motion_remotion` | `graphic_slide`, `narration_text`, `visual_prompt`, `remotion_props`, `asset_url`, `audio_url`).

## 2. Roadmap Pengembangan Bertahap

### Fase 1: Foundation & Workspace Setup
- Inisialisasi struktur proyek (*Frontend* Next.js/React + *Backend* Python FastAPI + Database).
- Sistem autentikasi, pembuatan *workspace*, pengaturan *brand identity*, dan manajemen *Multi-Provider API Key*.

### Fase 2: Core Content Pipeline (MVP)
- Modul input ide (Manual, *URL drop*, dan RSS dasar).
- Integrasi *LLM Router* (Gemini/Claude/OpenAI) untuk menghasilkan skrip dan struktur `project_scenes`.
- Generasi visual awal (gambar) & audio (TTS + *upload* manual) serta **Scene/Frame Inspector** untuk edit per adegan.

### Fase 3: Remotion Motion Graphics & Video Assembly
- Integrasi template dasar **Remotion** untuk *motion graphics* dan mode *hybrid*.
- *Timeline preview* sebelum *final render* dan ekspor video MP4 lengkap dengan opsi *Review Mode* vs *Auto-Pilot Mode*.

### Fase 4: UGC Character Sheet, Desain Grafis & Auto-Publishing
- Implementasi penuh **Character Sheet** untuk konsistensi karakter UGC.
- Modul desain *Carousel/Poster* + integrasi Canva API.
- Penjadwalan (*scheduler*) dan publikasi otomatis ke platform media sosial.
