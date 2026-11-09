---
name: alert-rules
description: Use when menentukan apakah suatu kondisi proyek atau tim harus memicu alert, level alert (Info, Warning, Critical), siapa penerimanya, dan bagaimana menulis pesannya. Don't use when menyusun laporan mingguan biasa tanpa kondisi menyimpang.
slug: alert-rules
---

# Alert Rules

## 1. Level
- **Info** → digest harian ke PIC.
- **Warning** → hari yang sama ke PIC + lead (atau penerima di tabel).
- **Critical** → segera (jam kerja) ke Khusnul + Rizky, tanpa menunggu brief.

## 2. Aturan (ambang dihitung lab0; agent memakai hasilnya)
| # | Pemicu | Ambang | Level | Penerima |
|---|---|---|---|---|
| 1 | Tidak update lab0 | 1 hari kerja | Info | PIC |
| 2 | Tidak update lab0 | 2 hari kerja berturut | Warning | PIC + lead |
| 3 | Task internal telat | H+1 | Warning | PIC |
| 4 | Task internal telat | H+3 | Warning | PIC + lead |
| 5 | Blocked tanpa jalan keluar | > 2 hari kerja | Warning | Lead + Rizky |
| 6 | Komitmen mingguan berisiko | Rabu, realisasi < 40% | Warning | Lead |
| 7 | SPI proyek | < 0,90 | Warning | Lead + Rizky |
| 8 | SPI proyek | < 0,80 | Critical | Khusnul + lead |
| 9 | Milestone bergeser | forecast > 5 hari kerja | Critical | Khusnul + PM |
| 10 | Health Merah | skor < 60 / override | Critical | Khusnul + PM |
| 11 | Kelebihan beban orang | > 100% di 2 minggu ke depan | Warning | Aga |
| 12 | CR menggantung | > 10 hari kerja | Warning | PM |
| 13 | Pending klien | L3 / L4 | Warning / Critical | Rizky / Khusnul |
| 14 | Perubahan prod tanpa change ticket | terdeteksi | Critical | Khusnul + lead IT |
| 15 | Proyek F0 belum Siap Mulai | H-2 kickoff | Warning | Rizky + PM |

## 3. Format pesan (semua level)
```
[<LEVEL>] <PRJ> — <judul ≤ 8 kata>
Apa: <fakta + angka>
Sejak: <tgl>   Dampak: <milestone/jadwal/biaya>
Diminta: <satu tindakan> dari <siapa> paling lambat <kapan>
Ref: <ID lab0>
```

## 4. Anti-kebisingan
- Satu pesan per orang per hari untuk Info/Warning; gabungkan item.
- Alert sama tidak diulang < 2 hari kerja kecuali level naik.
- Critical hanya jam 08.00–17.00 WIB; di luar itu hanya saat cutover/hypercare (manusia).
- Setiap alert wajib berisi satu tindakan yang diminta. Tanpa tindakan = bukan alert.
- Setiap Critical juga dicatat sebagai Issue di RAID.
