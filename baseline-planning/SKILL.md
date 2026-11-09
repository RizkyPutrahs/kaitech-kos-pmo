---
name: baseline-planning
description: Use when menyusun WBS, estimasi, jadwal, critical path, milestone-billing, atau mengunci dan merevisi baseline proyek (F2, atau setelah CR disetujui). Don't use when hanya memperbarui progress mingguan tanpa mengubah rencana.
slug: baseline-planning
---

# Baseline Planning (F2)

## 1. WBS
- Struktur level 1 = fase F1–F9. Level 2 = deliverable/area modul. Level 3 = work package.
- Aturan 8/80: work package 8–80 jam effort. Lebih besar → pecah.
- Setiap work package punya: ID WBS, nama berbentuk **kata benda hasil** ("BRD Modul
  Purchase disetujui"), bukan aktivitas ("mengerjakan BRD"), PIC, bobot, kriteria selesai,
  jenis bukti penerimaan.

## 2. Estimasi
- Tiga titik (optimis O, paling mungkin M, pesimis P); PERT = (O + 4M + P) / 6.
- Gunakan data historis Kaitech dari proyek sejenis bila ada di lab0.
- Faktor koreksi Indonesia-enterprise (terapkan pada aktivitas yang melibatkan klien):
  workshop & review klien ×1,3; pengumpulan data klien ×1,5; tanda tangan dokumen BUMN ×1,5
  (rantai disposisi/paraf).
- Effort ≠ durasi. Durasi mempertimbangkan ketersediaan key user (umumnya 30–50% waktu
  mereka, karena tetap menjalankan pekerjaan rutin).

## 3. Jadwal & kalender
1. Masukkan libur nasional & cuti bersama tahun berjalan dan tahun berikutnya.
2. Tandai: closing bulanan klien, periode Lebaran (±2 minggu tanpa go-live/UAT besar),
   Desember (tutup buku/penyerapan anggaran), audit tahunan klien, jadwal RUPS bila relevan.
3. Dependensi FS/SS; identifikasi **critical path**.
4. Buffer: **project buffer 10–15%** dari durasi critical path, diletakkan sebelum go-live
   (bukan disebar diam-diam per task). Buffer terlihat di rencana dan dikelola PMO.
5. Go-live idealnya di **awal bulan setelah closing** atau awal periode fiskal; hindari
   go-live di Jumat sore dan menjelang libur panjang.

## 4. Milestone & billing
- Setiap termin pembayaran harus menempel ke milestone yang **bisa dibuktikan** dengan BAST.
- Hindari termin yang bergantung pada hal di luar kendali Kaitech tanpa batas waktu
  (mis. "setelah go-live" tanpa klausul "atau maksimal X hari setelah UAT sign-off").
  Jika kontrak sudah begitu → `R-xxx` finansial.
- Tabel: MS-ID · Milestone · Gate · Tgl baseline · Bukti (BAST/BA UAT) · Termin % · Nilai.

## 5. Bobot
- Bobot proporsional terhadap effort baseline (mandays deliverable ÷ total mandays).
- Σ bobot = 100%. Cek ulang setiap kali WBS berubah.

## 6. Kunci baseline (G2)
1. Simpan sebagai versi v1.0 di lab0: WBS, tanggal mulai/selesai, effort, bobot, milestone.
2. Minta approval PM Kaitech dan Sponsor/PM klien (draft email/BA pengesahan jadwal).
3. Setelah terkunci: tanggal baseline **tidak diedit**. Perubahan hanya ke kolom forecast.

## 7. Re-baseline
Hanya jika: CR disetujui yang mengubah scope/jadwal, atau keputusan Steerco tertulis.
Langkah: salin baseline aktif → v(n+1).0 → terapkan perubahan → catat alasan + CR/DEC ref →
approval yang sama seperti G2 → arsipkan versi lama (tetap bisa dibaca untuk audit).
Larangan: re-baseline untuk "membuat laporan hijau".

## 8. Output wajib untuk human review
- Ringkasan: durasi total, tanggal go-live, critical path (urutan WBS), buffer, 5 asumsi
  jadwal terbesar, konflik kapasitas dari agent Resource.
