---
name: project-setup
description: Use when menyiapkan proyek baru sebelum kickoff (fase F0 Persiapan) — rencana 10 hari, tim manusia dan tim AI, grup WA internal/eksternal, Odoo dev/staging/prod, repo git, MCP per environment, project Paperclip, dan pemeriksaan gate Siap Mulai. Don't use when proyek sudah lewat kickoff.
slug: project-setup
---

# Project Setup (F0 Persiapan)

Tidak ada kickoff sebelum gate **Siap Mulai** hijau. Target 10 hari kerja sejak deal Won.

## 1. Urutan
H1–2 administrasi (handover, PRJ-xxxx, NDA, ringkasan kontrak: scope, termin, denda, SLA,
kepemilikan kode, hosting) → H2–3 tim manusia + PIC klien tertulis → H3 kanal WA & milis →
H3–6 sistem (repo, Odoo dev & staging, MCP, Paperclip) → H6–8 baseline draft, timeline,
kalender klien, risk register → H9 gate Siap Mulai → H10 kickoff (sponsor hadir).

## 2. Yang dibuat agent (draft) vs manusia
- Agent: rencana 10 hari sebagai task di lab0, checklist, draft charter, draft pesan pin WA,
  draft surat penunjukan PIC klien, cek otomatis gate.
- Manusia: membuat grup WA, membuat repo & database, memberi akses, menyetujui gate.

## 3. Konvensi nama (wajib)
| Objek | Format |
|---|---|
| Grup WA internal | `[INT] PRJ-xxxx <Klien> – Tim` |
| Grup WA eksternal | `[PRJ] <Klien> x Kaitech – <modul/fase>` · `[MGT] <Klien> x Kaitech – Steerco` |
| Milis | `prj-xxxx@` |
| Database Odoo | `<klien>-dev`, `<klien>-staging`, `<klien>-prod` |
| Repo | `kaitech/<klien>-odoo` · branch `main`/`staging`/`dev`/`feature/<id-task>-<slug>` |
| Service account MCP | `svc_<klien>_dev`, `svc_<klien>_stg`, `svc_<klien>_prd` |
| Project Paperclip | `PRJ-xxxx – <Klien>` |

## 4. Gate Siap Mulai (cek H9)
| Syarat | Bukti di lab0 | Pemeriksa |
|---|---|---|
| Kontrak, NDA, ringkasan kontrak | dokumen | Rizky |
| Tim Kaitech & PIC klien tertulis | RACI + surat/email | Rizky |
| WA & milis aktif, pin terpasang | tangkapan layar | Rizky |
| Repo, CI hijau, Odoo dev & staging jalan | link + hasil CI | Lead IT |
| MCP dev & staging terhubung; prod sesuai aturan | hasil uji koneksi | Lead IT |
| Project Paperclip & agent tim siap | run uji sukses | Lead IT |
| Draft baseline & timeline | draft | Rizky |
Agent menandai ✓/✗ + bukti; Rizky yang menyatakan lulus. Item ✗ di H-2 kickoff → alert #15.

Checklist lengkap per area: `references/checklist.md`.
