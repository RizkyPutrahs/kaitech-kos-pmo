---
name: phase-gate-closure
description: Use when menyiapkan review gate fase (G0–G9), paket BAST dan billing gate, go/no-go go-live, cutover plan, exit hypercare, atau penutupan proyek dan lessons learned. Don't use when pekerjaan rutin harian tanpa transisi fase.
slug: phase-gate-closure
---

# Phase Gate, Go-Live, dan Closure

## 1. Paket gate (disiapkan H-5 hari kerja sebelum tanggal gate)
1. Daftar exit criteria fase (dari `kaitech-pmo-way/references/lifecycle.md`) dengan status
   ✓/✗ dan bukti tertaut.
2. Ringkasan fase: rencana vs aktual (tanggal, effort), deliverable diterima, deviasi.
3. RAID terbuka yang terbawa ke fase berikutnya.
4. CR yang memengaruhi fase berikutnya.
5. Rencana fase berikutnya (sudah dari baseline) + perubahan.
6. Rekomendasi: Lulus · Lulus bersyarat (dengan action item & tenggat) · Tidak lulus.
Agent hanya **merekomendasikan**; keputusan gate oleh approver manusia dan dicatat sebagai DEC.

## 2. BAST & billing gate
Syarat penagihan termin (semua wajib):
- [ ] Milestone berstatus Tercapai di lab0
- [ ] BAST ditandatangani pihak berwenang klien (sesuai kontrak) & terunggah
- [ ] Lampiran pendukung lengkap (daftar deliverable, BA UAT/daftar hadir bila disyaratkan)
- [ ] Tidak ada syarat kontrak lain yang belum terpenuhi (mis. laporan, jaminan)
Saat semua ✓ → notifikasi Finance (draft invoice) + catat di Milestone_Billing.
Pantau BAST yang beredar: > 5 hari kerja belum kembali → Chaser L2 (sering tertahan di
rantai paraf). Untuk BUMN, tanyakan sejak awal siapa saja yang memaraf dan menandatangani.

## 3. Go/No-Go (H-2 go-live) — checklist
- [ ] UAT sign-off semua modul in-scope
- [ ] Defect Kritis = 0; defect Tinggi terbuka punya workaround tertulis
- [ ] Final data load & rekonsiliasi disetujui data owner
- [ ] User terlatih ≥ 90%; akun & hak akses dibuat dan diuji
- [ ] Cutover plan jam-per-jam disetujui; PIC tiap langkah dikonfirmasi hadir
- [ ] Rollback plan & titik rollback disepakati
- [ ] Sistem lama: rencana freeze & akses read-only
- [ ] Tim hypercare & jadwal piket; grup [WAR] aktif
- [ ] Komunikasi go-live ke seluruh user disiapkan
- [ ] Integrasi (bank, pajak, sistem lain) diuji end-to-end
Keputusan: GO · GO dengan syarat · NO-GO (tanggal ulang). Dicatat sebagai DEC Steerco.

## 4. Cutover plan
Kolom: No · Langkah · Detail · PIC · Mulai · Selesai · Durasi · Dependensi · Verifikasi ·
Titik rollback (Y/N) · Status. Laporan per jam di [WAR] (template T12).

## 5. Hypercare
- Prioritas tiket: Kritis (operasional berhenti) respons 1 jam, solusi/workaround 4 jam ·
  Tinggi respons 4 jam, 1 hari kerja · Sedang 1 hari kerja, 3 hari kerja · Rendah 2 hari kerja,
  sesuai jadwal. (Sesuaikan dengan SLA kontrak bila berbeda.)
- Laporan harian minggu 1–2: tiket baru/selesai/terbuka per prioritas, isu utama, adopsi.
- Exit hypercare: kriteria kontrak + tidak ada Kritis 5 hari kerja berturut + tren tiket turun.

## 6. Closure
1. BAST akhir & invoice akhir.
2. Serah terima: dokumen final, kredensial admin (via kanal aman, bukan WA), source code
   kustom bila kontrak mensyaratkan, kontak support.
3. Transisi ke tim support/retainer: daftar outstanding, known issues, konfigurasi kunci.
4. **Lessons learned** (dua sesi): internal dan bersama klien. Format: apa yang berjalan baik ·
   apa yang tidak · akar masalah · tindakan untuk proyek berikutnya · skill Kaitech yang harus
   diperbarui. Usulan perubahan skill dibuat sebagai issue untuk PMO Lead (persetujuan manusia).
5. Closure report: tujuan bisnis vs hasil, rencana vs aktual (jadwal, effort, biaya/margin
   — internal), CR, kepuasan klien, rekomendasi.
6. Arsipkan proyek di lab0; ekspor WA [PRJ]/[MGT] ke lab0; tutup [INT]; keluarkan bot.
7. Teknis: tag `release-final`; serahkan kode sesuai klausul kepemilikan; dokumentasi teknis;
   kredensial admin prod lewat kanal aman lalu kurangi akses Kaitech sesuai kontrak support;
   cabut akses dev/staging; rotasi/nonaktifkan kunci MCP & service account; arsip/hapus DB
   dev/staging sesuai aturan data pribadi.
8. Paperclip: arsipkan project, matikan routine per proyek, hapus secret proyek.
9. Target: semua checklist closure selesai ≤ 10 hari kerja sejak exit hypercare disetujui.
