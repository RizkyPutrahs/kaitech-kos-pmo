---
name: health-score
description: Use when menghitung Health Score dan status RAG proyek atau portofolio untuk laporan, Project Update lab0, atau dashboard. Don't use when hanya mencatat data RAID atau progress tanpa menyimpulkan status.
slug: health-score
---

# Health Score (0–100) dan RAG

## 1. Lima dimensi

| Dimensi | Bobot | Metrik | Skor |
|---|---|---|---|
| Jadwal | 30% | SPI | ≥ 0,95 → 100 · 0,85–<0,95 → 70 · 0,75–<0,85 → 40 · < 0,75 → 0 |
| Milestone | 20% | Milestone jatuh tempo yang tercapai tepat waktu (toleransi 5 hari kerja) | persentase × 100; tidak ada yang jatuh tempo → 100 |
| RAID | 20% | Jumlah risiko Kritis + isu Kritis/Tinggi terbuka | 0 → 100 · 1–2 → 60 · ≥ 3 → 20 |
| Action & pending klien | 15% | Action item lewat tenggat (semua pihak) | 0 → 100 · 1–3 → 70 · 4–6 → 40 · > 6 → 10 |
| Scope | 15% | CR di Menunggu Keputusan > 10 hari kerja | 0 → 100 · 1 → 60 · ≥ 2 → 20 |

Health = Σ (bobot × skor dimensi), dibulatkan.

## 2. RAG
Hijau ≥ 80 · Kuning 60–79 · Merah < 60.
Override ke Merah (apa pun skornya): milestone billing bergeser > 10 hari kerja; isu Kritis
memblokir go-live; ketidakpuasan tertulis sponsor; go-live tergeser tanpa keputusan Steerco.

## 3. Aturan
- Agent tidak menaikkan warna. Human boleh menaikkan dengan alasan tertulis di Project Update.
- Tampilkan **skor per dimensi** di setiap laporan, bukan hanya warna total, agar pembaca
  tahu sumber masalah.
- Tren: bandingkan dengan 2 minggu sebelumnya (↑ ↓ →).
- Isi Project Update native Odoo: status On track (Hijau) / At risk (Kuning) / Off track
  (Merah) + ringkasan 3 kalimat.

## 4. Portofolio (untuk Khusnul, Senin)
Tabel semua proyek aktif: Proyek · Fase · Health · RAG · Tren · SPI · Milestone berikut ·
Termin berikut & status billing gate · Eksepsi. Urutkan dari Health terendah.
