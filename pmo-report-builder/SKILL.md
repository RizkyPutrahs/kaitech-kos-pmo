---
name: pmo-report-builder
description: Use when menghasilkan file Workbook PMO (xlsx), Laporan Status Mingguan (docx), atau deck steerco (pptx) dari data lab0. Don't use when hanya menjawab pertanyaan status di chat.
slug: pmo-report-builder
---

# PMO Report Builder

Dokumen dibuat oleh skrip, bukan ditulis model. Model hanya menulis narasi singkat
(ringkasan eksekutif, pencapaian, rencana) dan memeriksa hasil.

## Urutan
1. `pmo_workbook_export(project, status_date)` → simpan sebagai `data.json`.
2. `python scripts/fill_workbook.py data.json out/Workbook.xlsx` → buka nilai Dashboard
   (health, SPI, planned, earned) dari file hasil; ini sumber angka tunggal.
3. Tulis `narrative.json` (ringkasan ≤ 5 kalimat, pencapaian ≤ 6, rencana ≤ 6) berdasar
   angka langkah 2. Kesimpulan dulu, tanpa menyalahkan.
4. `node scripts/build_report.js data.json narrative.json out/Laporan.docx`.
5. Steerco saja: `node scripts/build_steerco.js data.json narrative.json out/Steerco.pptx`.
6. Cek konsistensi (skill status-reporting §5), lampirkan file ke task, draft Project Update.

## Kontrak skrip (dibangun tim Zhafron)
- Struktur `data.json` = sheet Workbook (Rencana_Proyek, Milestone_Billing, RAID,
  Change_Request, Action_Items, Riwayat_Mingguan) + identitas proyek.
- Template di `assets/` = file di folder `templates/` kit ini; skrip mengisi, tidak mendesain ulang.
- Skrip gagal → hentikan, laporkan error ke PMO Copilot. Jangan membuat dokumen manual sebagai pengganti.
