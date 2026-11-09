---
name: change-control
description: Use when ada permintaan baru, penambahan, atau perubahan dari klien atau internal yang mungkin di luar scope/baseline, untuk mengklasifikasi, menganalisis dampak, dan mendraf Change Request. Don't use when perubahan hanya koreksi defect sesuai spesifikasi yang sudah disetujui.
slug: change-control
---

# Change Control

## 1. Prinsip
- Scope = kontrak + charter + BRD/FSD yang ditandatangani. Di luar itu = perubahan.
- **Tidak ada pekerjaan di luar scope tanpa CR disetujui**, sekecil apa pun ("sekalian saja"
  adalah sumber kebocoran margin terbesar). Pengecualian hanya dengan DEC tertulis dari
  Khusnul (mis. goodwill strategis), tetap dicatat sebagai CR berbiaya Rp 0.
- Agent tidak menjanjikan apa pun kepada klien, termasuk "bisa" atau "tidak bisa".

## 2. Klasifikasi permintaan
| Kelas | Kriteria | Tindakan |
|---|---|---|
| Dalam scope | Tercakup BRD/FSD/kontrak | Tutup sebagai klarifikasi; buat task biasa |
| Defect | Hasil tidak sesuai spesifikasi disetujui | Bukan CR; masuk log defect |
| CR minor | ≤ 3 mandays, tidak menggeser milestone | CR ringkas, approval PM klien |
| CR mayor | > 3 mandays, atau menggeser milestone, atau mengubah biaya | CR lengkap, approval Sponsor; Steerco bila menggeser go-live |
| Tidak jelas | Butuh klarifikasi | Draft pertanyaan klarifikasi ke PM |

## 3. Analisis dampak (wajib semua dimensi)
1. Deskripsi permintaan dalam kalimat klien + interpretasi teknis.
2. Pendekatan: native/konfigurasi dulu; kustom hanya jika perlu (tandai `[PERLU KONFIRMASI]`
   teknis dari lead IT).
3. Effort (mandays per peran) — estimasi dari lead IT/BA, bukan karangan agent.
4. Dampak jadwal: apakah menyentuh critical path? Berapa hari kerja?
5. Dampak biaya: mandays × rate kartu harga Kaitech (diambil dari lab0, bukan diingat).
6. Dampak risiko, dokumen (BRD/FSD perlu revisi?), testing, training, migrasi.
7. Opsi: (a) kerjakan sekarang dengan biaya & geser jadwal, (b) kerjakan setelah go-live
   (fase 2), (c) tolak/alternatif native. Sertakan rekomendasi PM.

## 4. Alur
Draft → Diajukan (PM review) → Dianalisis (estimasi IT/BA masuk) → Menunggu Keputusan
(dikirim ke klien oleh PM) → Disetujui/Ditolak/Ditunda.
- CR Disetujui → kirim ke agent Planning untuk re-baseline & update bobot; ke Reporting.
- Umur di Menunggu Keputusan > 10 hari kerja → eksepsi; masuk laporan & steerco.

## 5. Deteksi otomatis
Sumber: MoM, WA, komentar task, email. Frasa pemicu: "sekalian", "tambahan", "bisa nggak
dibuatkan", "ternyata kami juga butuh", "di sistem lama bisa", "minta laporan baru",
"ubah alur approval", "tambah cabang/user/perusahaan". Setiap pemicu → kandidat CR, dicek
terhadap BRD/FSD (via lab0) sebelum dibuat draft.

## 6. Format CR (ringkas untuk klien)
No. CR · Tanggal · Pemohon · Latar belakang · Deskripsi perubahan · Dampak (jadwal, biaya,
lainnya) · Opsi & rekomendasi · Persetujuan (nama, jabatan, tanggal, tanda tangan).
