---
name: raid-management
description: Use when mencatat, menilai, memperbarui, atau melaporkan Risk, Assumption, Issue, Dependency, dan Decision (RAID) proyek, termasuk mengekstraknya dari MoM, komentar task, atau percakapan WA. Don't use when menangani permintaan perubahan scope formal (pakai change-control).
slug: raid-management
---

# RAID Management

## 1. Definisi tegas
- **Risk (R)**: kejadian yang *mungkin* terjadi di masa depan dan berdampak. Punya probabilitas.
- **Assumption (A)**: hal yang dianggap benar untuk perencanaan, belum terbukti. Harus divalidasi.
- **Issue (I)**: masalah yang *sedang* terjadi. Tidak punya probabilitas; punya urgensi.
- **Dependency (D)**: pekerjaan Kaitech yang menunggu pihak lain (klien, vendor, tim lain).
- **Decision (DEC)**: keputusan yang sudah diambil, dengan pemutus dan tanggal.
Risk yang terjadi → tutup R, buka I dengan referensi R.
Assumption yang terbukti salah → tutup A, buka I atau R.

## 2. Penilaian risiko
Probabilitas (P) 1–5 · Dampak (D) 1–5 · Skor = P × D.

| Skor | Level | Perlakuan |
|---|---|---|
| 15–25 | Kritis | Masuk laporan mingguan & steerco; owner manajemen; tinjau mingguan |
| 8–14 | Tinggi | Masuk laporan mingguan; mitigasi aktif |
| 4–7 | Sedang | Pantau dua mingguan |
| 1–3 | Rendah | Pantau bulanan |

Skala dampak: 1 tidak terasa · 2 geser < 3 hari kerja · 3 geser milestone ≤ 5 hari kerja atau
effort +5% · 4 geser milestone > 5 hari kerja / effort +10% / termin tertunda · 5 go-live
gagal/bergeser, denda, atau reputasi di level direksi.
Respons: Hindari · Mitigasi · Transfer · Terima (wajib DEC jika Terima untuk skor ≥ 8).

## 3. Field wajib
ID · Tipe · Judul (≤ 10 kata) · Deskripsi (sebab → kejadian → dampak) · Sumber (MoM/WA/task,
tanggal, orang) · P · D · Skor · Owner (satu nama) · Respons & rencana tindakan · Tenggat ·
Status · Tanggal buka · Tanggal tinjau terakhir · Referensi terkait (AI/CR/DEC).

## 4. Risk register awal standar ERP Indonesia (pakai saat F2, sesuaikan)
1. Key user tidak tersedia karena beban operasional rutin.
2. Data master/saldo awal klien terlambat atau kualitas rendah.
3. Proses bisnis klien belum baku/berbeda antar cabang/unit.
4. Sponsor berganti (rotasi/mutasi jabatan, umum di BUMN).
5. Rantai approval dokumen (BRD, BA, BAST) panjang → tanda tangan lambat.
6. Permintaan kustom bertambah setelah blueprint (scope creep).
7. Integrasi dengan sistem lain (bank, e-Faktur/Coretax, sistem induk/holding) terlambat aksesnya.
8. Infrastruktur/akses server/VPN klien terlambat disiapkan.
9. Resistensi user terhadap perubahan (adopsi).
10. Periode Lebaran/akhir tahun menggeser jadwal workshop/UAT.
11. Ketergantungan pada satu orang kunci di tim Kaitech.
12. Perubahan regulasi (pajak/akuntansi) di tengah proyek.

## 5. Ekstraksi dari MoM & WA
Baca dengan kategori sinyal di `wa-pmo-playbook` §2. Untuk setiap temuan:
1. Cek duplikat dengan RAID terbuka (judul/objek mirip) → perbarui, jangan buat baru.
2. Buat draft record dengan sumber lengkap.
3. Keputusan → DEC berstatus *perlu konfirmasi* + draft T5.

## 6. Tinjauan harian (agent RAID, 15:00)
- RAID tanpa owner atau tanpa tenggat → lengkapi atau tanya PM.
- Tenggat mitigasi lewat → Action Item ke owner + masukkan antrean Chaser.
- Risiko Kritis baru → notifikasi PMO Lead segera (jangan tunggu laporan mingguan).
- Dependency pihak klien lewat tanggal komitmen → hitung dampak ke jadwal, kirim ke Planning.
- Assumption yang belum divalidasi > 15 hari kerja → buat Action Item validasi.

## 7. Output untuk laporan
Top 5 risiko (skor tertinggi), semua isu Kritis/Tinggi terbuka, dependency klien yang
menggeser jadwal, keputusan minggu ini, keputusan yang dibutuhkan (dari siapa, kapan).
