---
name: evidence-progress
description: Use when menghitung atau memperbarui progress proyek, persentase deliverable, planned vs earned, SPI, atau memverifikasi klaim progress dari tim/klien. Don't use when menyusun rencana baru atau mengubah baseline.
slug: evidence-progress
---

# Evidence-based Progress

## 1. Skala progress (hanya lima nilai ini)

| Nilai | Kondisi | Bukti minimal yang harus tertaut di lab0 |
|---|---|---|
| 0% | Belum mulai | — |
| 25% | Dikerjakan, ada hasil awal | Draft dokumen / commit / konfigurasi awal tertaut |
| 50% | Hasil lengkap, review internal | Dokumen versi lengkap / PR dibuka / checklist QA internal |
| 75% | Direview klien atau lulus uji internal | Bukti dikirim ke klien (email/WA tercatat) / SIT lulus |
| 100% | Diterima | Approval klien tertulis / BA UAT / BAST / sign-off lab0 |

Tidak ada 10%, 60%, 90%. Klaim tanpa bukti = turun ke level bukti tertinggi yang ada.

## 2. Rumus
- Planned % deliverable pada tanggal status (TS):
  `0 jika TS < mulai_baseline; 1 jika TS ≥ selesai_baseline; selain itu (TS − mulai) ÷ (selesai − mulai)`
- Planned % proyek = Σ (bobot × planned % deliverable)
- Earned % proyek = Σ (bobot × progress bukti)
- SPI = Earned % ÷ Planned % (jika Planned % = 0, SPI = 1)
- Varian deliverable (hari kerja) = forecast_selesai − baseline_selesai

## 3. Prosedur harian (agent Progress)
1. Ambil semua deliverable berstatus Berjalan/Review dari lab0.
2. Untuk setiap deliverable, cek bukti baru sejak run terakhir (lampiran, approval, PR merge,
   hasil QA, BAST).
3. Usulkan perubahan progress **hanya naik ke level yang didukung bukti**. Jika bukti hilang
   atau ditarik (mis. klien menolak dokumen), usulkan turun dan catat alasannya.
4. Tulis perubahan sebagai draft di lab0; PM menyetujui (atau auto-approve jika bukti adalah
   approval sistem lab0 itu sendiri).
5. Hitung ulang Planned/Earned/SPI; kirim angka ke agent Reporting & PMO Lead.

## 4. Deteksi anomali (laporkan ke PMO Lead)
- Deliverable di 75% > 10 hari kerja (klien belum memberi keputusan → pending klien).
- Deliverable lewat baseline selesai tetapi progress < 50%.
- Lonjakan progress > 50 poin dalam satu minggu tanpa bukti bertahap.
- Klaim progress di WA/MoM yang tidak cocok dengan bukti di lab0.
- SPI < 0,9 dua minggu berturut-turut → tren, bukan kebetulan.

## 5. Kurva S
Simpan Planned % dan Earned % per minggu (tanggal Jumat) untuk grafik kurva S di laporan dan
steerco. Jangan merekonstruksi angka minggu lalu; angka historis dibekukan setiap Jumat.
