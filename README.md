# Autonomous AI Content Agency Platform

Platform manajemen dan produksi konten multi-brand/multi-klien berbasis AI dengan kontrol granular (*Human-in-the-Loop*) dan opsi otomasi penuh (*Auto-Pilot*).

## Dokumentasi Arsitektur (`/docs`)
1. **[01-system-overview.md](docs/01-system-overview.md)** — Visi produk, arsitektur multi-tenant workspace, jenis konten (Video & Desain Grafis), dan prinsip kerja.
2. **[02-workflow-pipeline.md](docs/02-workflow-pipeline.md)** — Alur kerja *end-to-end* mulai dari setup workspace, sumber ide, generasi aset, *frame inspector*, hingga *review* vs *auto-pilot* publishing.
3. **[03-api-router-and-engines.md](docs/03-api-router-and-engines.md)** — Arsitektur *Multi-Provider API Gateway* (BYOK), integrasi Generative AI, Remotion (Motion Graphics), dan Canva API.
4. **[04-database-and-roadmap.md](docs/04-database-and-roadmap.md)** — Skema entitas database inti dan fase pengembangan bertahap (MVP ke skala penuh).

## Aturan Pengembangan untuk AI Agent
- Selalu rujuk dokumen di folder `docs/` sebelum membuat struktur folder, endpoint, atau komponen UI baru.
- Kerjakan fitur secara modular per fase sesuai roadmap.
- Pastikan seluruh pemanggilan AI (Teks, Gambar, Video, Audio) melalui lapisan *Unified Provider Router* agar API Key dan model dapat diganti secara dinamis per workspace.
