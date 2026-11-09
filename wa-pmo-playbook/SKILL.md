---
name: wa-pmo-playbook
description: Use when menyusun, mengirim internal, atau mendraf pesan WhatsApp proyek (reminder, eskalasi, konfirmasi keputusan, request data, info jadwal, rekap) atau saat membaca percakapan grup WA untuk diekstrak menjadi action item, keputusan, risiko, atau permintaan perubahan. Don't use when menulis dokumen formal (laporan Word, deck steerco, BAST).
slug: wa-pmo-playbook
---

# WA PMO Playbook — mengelola proyek ERP di Indonesia lewat WhatsApp

Di Indonesia, proyek berjalan di WhatsApp: keputusan diambil di grup, data dikirim sebagai foto,
persetujuan berupa "👍", dan eskalasi terjadi lewat japri. Skill ini mengubah kekacauan itu
menjadi jejak yang terkontrol, tanpa merusak hubungan dengan klien.

## 1. Arsitektur grup (dibuat di F1, dicatat di Communication Plan)

| Grup | Anggota | Fungsi | Agent boleh kirim langsung? |
|---|---|---|---|
| `[INT] <Kode Klien> – Tim` | Tim Kaitech saja | Koordinasi harian, reminder internal | Ya (Chaser, PMO Lead) |
| `[PRJ] <Klien> x Kaitech – <Modul/Fase>` | PM & key user kedua pihak | Operasional proyek | Tidak. Draft → PM kirim |
| `[MGT] <Klien> x Kaitech – Steerco` | Sponsor, PM, Khusnul | Keputusan & eskalasi manajemen | Tidak. Hanya manusia |
| `[WAR] <Klien> Go-Live` | Tim inti cutover | Selama cutover & hypercare minggu 1 | Tidak. Draft laporan per jam |

**Pesan pin standar** di grup `[PRJ]` (dipasang PM saat grup dibuat):
1. Tujuan grup dan jam respons (08.00–17.00 WIB hari kerja).
2. Aturan: keputusan dan permintaan perubahan dikonfirmasi ulang secara tertulis oleh PM
   Kaitech dan dicatat di lab0. "Yang tercatat di lab0 yang berlaku."
3. Data/dokumen dikirim sebagai file (bukan foto layar) bila memungkinkan.
4. Kanal eskalasi: PM klien ↔ PM Kaitech; di atasnya Sponsor ↔ Khusnul.

## 2. Mengekstrak sinyal dari percakapan WA

Saat membaca ekspor/feeding percakapan grup, klasifikasikan setiap pesan relevan:

| Sinyal | Ciri dalam pesan | Jadi apa di lab0 |
|---|---|---|
| Komitmen | ada PIC + tindakan + waktu ("Besok saya kirim datanya") | Action Item (`AI-`) dengan tenggat |
| Komitmen lemah | "siap", "oke", "👍", "noted", "nanti dicek" tanpa waktu | Action Item **tanpa tenggat** + tandai `[KOMITMEN LEMAH]`, minta tanggal |
| Keputusan | "kita pakai yang opsi B", "sudah ACC Pak Direktur" | Decision (`DEC-`) status *perlu konfirmasi tertulis* |
| Permintaan baru | "sekalian bisa ditambah…", "tolong dibuatkan laporan…" | Kandidat CR → agent Change Request |
| Masalah | "error", "nggak bisa", "kok beda", keluhan | Issue (`I-`) |
| Kekhawatiran | "takutnya…", "bulan depan orangnya cuti" | Risk (`R-`) |
| Ketergantungan | "nunggu dari IT pusat", "vendor lama belum kasih akses" | Dependency (`D-`) |

Aturan ekstraksi:
- **"Siap" bukan komitmen.** Komitmen sah = PIC + tindakan + tanggal. Jika belum lengkap,
  draft pesan klarifikasi yang sopan (template T3).
- **Voice note** tidak bisa diaudit: minta PM merangkum ke teks, lalu kirim konfirmasi T5.
- **Foto/screenshot sebagai bukti**: catat sumber (grup, pengirim, waktu) di lampiran record.
- **Pesan yang dihapus/diedit**: jika isinya keputusan, minta konfirmasi ulang tertulis.
- Selalu catat sumber: `WA [PRJ] Klien–Finance, 12 Nov 2026 14:32, Ibu Rina`.

## 3. Etika dan budaya (ini yang membedakan PMO senior)

1. **Sapaan**: "Bapak/Ibu" + nama depan. Untuk direksi: "Bapak/Ibu" + jabatan bila belum akrab.
   Jangan memakai "Anda" di grup klien.
2. **Pembuka halus**: "Selamat pagi Bapak/Ibu, mohon izin mengingatkan…",
   "Mohon bantuannya…", "Terima kasih atas waktunya…". Hindari kata "harus", "segera" di
   pesan pertama; "segera" baru dipakai di level eskalasi.
3. **Jangan pernah menegur atau mengeskalasi di grup terbuka.** Urutan: japri PIC → japri
   atasan PIC (oleh PM manusia) → forum formal (weekly/steerco). Mempermalukan orang di grup
   merusak kerja sama untuk sisa proyek.
4. **Hierarki klien**: jangan melompati PM klien langsung ke direksi klien. Eskalasi
   manajemen dilakukan Khusnul ke Sponsor, bukan agent.
5. **Satu pesan = satu topik**, maksimal ±8 baris. Gunakan nomor untuk daftar.
6. **Tag (@) secukupnya**: tag PIC yang diminta tindakan saja, bukan seluruh grup.
7. **Centang biru tanpa balasan** bukan persetujuan. Tunggu 1 hari kerja sebelum reminder.
8. **Jangan menyalahkan**: tulis fakta dan dampak ("data stok belum kami terima, sehingga
   mock load 1 bergeser"), bukan karakter ("Bapak telat").
9. **Apresiasi di depan umum, koreksi secara pribadi.** Ucapkan terima kasih di grup saat
   klien menyelesaikan item penting; ini memperkuat perilaku.

## 4. Jam dan kalender kirim

- Kirim **08.00–17.00 WIB**, hari kerja. Ideal: 08.30–10.00 dan 13.30–15.00.
- **Hindari Jumat 11.15–13.15** (Salat Jumat).
- **Ramadhan**: jam kerja klien biasanya lebih pendek; kirim 08.00–14.30; hindari menjelang
  berbuka. Jangan jadwalkan workshop panjang di sore hari.
- **Lebaran**: anggap ±1 minggu sebelum dan sesudah sebagai periode respons lambat. Jangan
  merencanakan go-live atau UAT besar dalam ±2 minggu dari Lebaran.
- **Akhir tahun (Des)**: klien BUMN fokus penyerapan anggaran dan tutup buku; dorong BAST
  dan penagihan sebelum pertengahan Desember.
- **Closing bulanan** (biasanya tanggal 1–7): tim finance/akuntansi klien sulit diajak UAT
  atau workshop. Cek di stakeholder register.
- Akhir pekan dan malam: hanya saat cutover/hypercare atau insiden Kritis, oleh manusia.

## 5. Tangga eskalasi (hari kerja setelah tenggat)

| Level | Kapan | Siapa | Kanal | Template |
|---|---|---|---|---|
| L0 | H-1 sebelum tenggat | Chaser (draft) | Grup [PRJ] via PM / internal langsung | T1 |
| L1 | H+1 | Chaser → PIC | Internal: grup [INT]. Klien: draft untuk PM, japri PIC | T2 |
| L2 | H+3 | PM manusia → PIC + atasan PIC | Japri, lalu weekly meeting | T4 |
| L3 | H+5 | PMO Lead → Head/GM terkait; catat sebagai Issue/Dependency | Japri + RAID | T6 |
| L4 | H+7 | Khusnul ↔ Sponsor klien | Telepon/japri; masuk agenda steerco | (manusia) |

Untuk item **pihak Klien** yang menggeser jadwal: sejak L2, catat sebagai Dependency milik
klien dengan tanggal komitmen awal dan dampaknya. Catatan ini melindungi Kaitech jika nanti
ada klaim keterlambatan atau denda.

## 6. Konfirmasi keputusan (wajib ≤ 1 hari kerja)

Setiap keputusan yang terjadi di WA atau telepon:
1. Catat sebagai `DEC-xxx` di lab0 berstatus *perlu konfirmasi*.
2. Draft pesan konfirmasi T5 untuk PM kirim ke grup [PRJ].
3. Jika tidak ada keberatan dalam 2 hari kerja, PM ubah status menjadi *dikonfirmasi*
   (diam = setuju hanya jika aturan ini tertulis di pesan pin & Communication Plan).
4. Keputusan berdampak scope/biaya/jadwal → wajib CR formal, tidak cukup konfirmasi WA.

## 7. Batasan agent

- Agent **boleh** mengirim langsung hanya ke grup `[INT]`.
- Agent **tidak pernah** mengirim ke grup klien, japri klien, atau grup manajemen.
  Semua untuk klien = draft di task lab0 dengan label `DRAFT-WA`, lengkap dengan tujuan
  (grup/japri, nama), waktu kirim yang disarankan, dan template yang dipakai.
- Agent tidak menyebut dirinya AI di pesan yang dikirim PM atas namanya; pesan ditulis
  sebagai suara PM Kaitech.

Template lengkap: `references/wa-templates.md`.
