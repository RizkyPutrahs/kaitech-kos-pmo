---
name: status-reporting
description: Use when menyusun laporan status mingguan (Word), deck steering committee (PowerPoint), pembaruan workbook PMO (Excel), rekap WA, atau laporan portofolio internal. Don't use when menulis dokumen blueprint/BRD/FSD.
slug: status-reporting
---

# Status Reporting

## 1. Jenis laporan & jadwal

| Laporan | Template | Draft oleh | Siap review | Terkirim | Approver |
|---|---|---|---|---|---|
| Workbook PMO (sumber angka) | `Kaitech_PMO_Workbook.xlsx` | Reporting | Kamis 15:00 | — (internal) | PMO Lead |
| Laporan Status Mingguan | `Laporan_Status_Mingguan.docx` | Reporting | Kamis 17:00 | Jumat ≤ 12:00 | PM proyek |
| Rekap WA mingguan | T10 `wa-pmo-playbook` | Reporting | Jumat 12:00 | Jumat 13:30–15:00 | PM |
| Deck Steerco | `Steerco_Deck.pptx` | Reporting | H-3 rapat | H-1 (pre-read) | Khusnul |
| Portofolio internal | ringkas di Paperclip/lab0 | PMO Lead | Senin 07:30 | Senin 08:00 | — |

## 2. Urutan penyusunan (selalu sama)
1. **Bekukan data** per tanggal status (Kamis 14:00 WIB): progress, milestone, RAID, CR, action.
2. Isi/refresh Workbook (sheet Rencana_Proyek, Milestone_Billing, RAID, Change_Request,
   Action_Items) dari lab0. Dashboard menghitung otomatis.
3. Ambil Health Score & RAG dari Dashboard. Jangan menghitung ulang di dokumen lain.
4. Susun Laporan Word dengan angka yang **sama persis** dengan Workbook.
5. Untuk steerco: deck mengambil angka dari Workbook yang sama + kurva S historis.
6. Cek konsistensi (lihat §5), lalu kirim ke reviewer.

## 3. Struktur Laporan Status Mingguan (Word)
1. Header: proyek, periode, nomor laporan, tanggal status, PM kedua pihak.
2. **Ringkasan eksekutif** (≤ 5 kalimat): status RAG + health, progress vs rencana, hal
   terpenting minggu ini, keputusan yang dibutuhkan.
3. Status per dimensi (tabel 5 dimensi + skor + komentar).
4. Progress per fase/deliverable (tabel: bobot, rencana %, aktual %, varian, status).
5. Milestone & termin (tabel).
6. Pencapaian minggu ini (maks 6 butir, berbasis bukti).
7. Rencana minggu depan (maks 6 butir, dengan PIC).
8. Risiko & isu utama (top 5, dengan mitigasi & owner).
9. Change Request (status & umur).
10. **Pending klien** (item, PIC klien, tanggal diminta, tenggat, umur, dampak). Bagian ini
    wajib ada setiap minggu, meskipun kosong ("Tidak ada").
11. Keputusan yang dibutuhkan (keputusan, dari siapa, tenggat, konsekuensi jika terlambat).
12. Lampiran: link lab0, daftar MoM minggu ini.

## 4. Struktur Deck Steerco (maks 12 slide, pre-read H-1)
1. Judul · 2. Ringkasan eksekutif (health + 3 pesan) · 3. Progress vs baseline (kurva S) ·
4. Milestone & timeline · 5. Status per fase · 6. Risiko & isu Kritis · 7. Change Request ·
8. Pending klien & dependency · 9. Termin & billing gate · 10. Rencana 30 hari ·
11. **Keputusan yang diminta dari Steerco** · 12. Penutup.
Satu pesan per slide; judul slide berupa kesimpulan ("Progress 4 poin di bawah rencana
karena data migrasi terlambat"), bukan topik ("Progress").

## 5. Checklist konsistensi sebelum kirim
- [ ] Angka progress, SPI, health identik di Excel, Word, PPT, dan rekap WA.
- [ ] Semua item merah/kuning punya tindakan, PIC, tenggat.
- [ ] Tidak ada nama klien yang salah eja; jabatan benar.
- [ ] Pending klien ditulis faktual tanpa menyalahkan.
- [ ] Tidak ada informasi internal (margin, rate, isu internal tim) di dokumen klien.
- [ ] Nomor laporan & tanggal status benar.
- [ ] Bahasa: kesimpulan dulu, ringkas.

## 6. Nada laporan
Jujur dan dini. Kabar buruk disampaikan bersama rencana tindakan. Jangan menunggu steerco
untuk menyampaikan deviasi besar: PM menelepon sponsor dulu, laporan mengonfirmasi.
