# Template Pesan WA

Ganti teks dalam `<…>`. Pertahankan nada. Maksimal ±8 baris per pesan.

---

## T1 — Pengingat H-1 (sopan, informatif)
```
Selamat pagi Bapak/Ibu <Nama>,
Mohon izin mengingatkan, besok <hari, tgl> adalah tenggat untuk:
<n>. <item singkat> (<AI-xxx>)
Item ini dibutuhkan untuk <dampak/aktivitas berikutnya>.
Apabila ada kendala, mohon dikabari agar kami bisa bantu sesuaikan.
Terima kasih 🙏
```

## T2 — Reminder L1 (H+1)
```
Selamat pagi Bapak/Ibu <Nama>,
Mohon izin follow up untuk <item> yang dijadwalkan <tgl tenggat>.
Saat ini kami masih menunggu agar <aktivitas berikutnya> dapat berjalan sesuai jadwal.
Kira-kira kapan Bapak/Ibu bisa kirimkan? Kami siap bantu bila ada yang perlu dijelaskan.
Terima kasih.
```

## T3 — Klarifikasi komitmen lemah ("siap/oke")
```
Terima kasih Bapak/Ibu <Nama> 🙏
Agar kami bisa sesuaikan jadwal tim, boleh kami catat target tanggalnya untuk <item>?
Misalnya <tanggal usulan>, apakah memungkinkan?
```

## T4 — Eskalasi L2 (oleh PM manusia, japri ke PIC + atasan)
```
Selamat siang Bapak/Ibu <Atasan>,
Mohon izin menyampaikan, <item> untuk <modul> yang ditargetkan <tgl> belum kami terima
(sudah kami follow up <tgl-tgl>).
Dampaknya: <aktivitas> bergeser ±<n> hari kerja dan berpotensi memengaruhi <milestone>.
Mohon arahan Bapak/Ibu, apakah kita bisa sepakati tanggal baru <usulan>?
Terima kasih atas bantuannya.
```

## T5 — Konfirmasi keputusan
```
Selamat sore Bapak/Ibu,
Menindaklanjuti diskusi <hari ini/di rapat/di telepon> <tgl>, kami konfirmasi keputusan berikut:
<DEC-xxx>: <isi keputusan dalam 1–2 kalimat>
Diputuskan oleh: <Nama, Jabatan>
Dampak: <tidak ada / ke jadwal / ke scope (akan diproses via CR-xxx)>
Apabila ada yang kurang tepat, mohon dikoreksi paling lambat <tgl +2 hari kerja>.
Terima kasih.
```

## T6 — Notifikasi deviasi/keterlambatan (pihak Kaitech, jujur & dini)
```
Selamat pagi Bapak/Ibu,
Kami ingin menyampaikan lebih awal: <deliverable> diperkirakan selesai <tgl forecast>,
mundur <n> hari kerja dari rencana <tgl baseline>.
Penyebab: <singkat, faktual>.
Langkah kami: <mitigasi>. Dampak ke <milestone/go-live>: <ada/tidak ada>.
Detail akan kami bahas di weekly meeting <hari>. Mohon maaf atas ketidaknyamanannya.
```

## T7 — Permintaan data/dokumen
```
Selamat pagi Bapak/Ibu <Nama>,
Untuk persiapan <aktivitas>, mohon bantuannya menyiapkan:
1. <data/dokumen> — format <xlsx/pdf>, contoh terlampir
2. <…>
Target kami terima: <tgl>. PIC dari kami: <nama PM/BA>.
Terima kasih 🙏
```

## T8 — Permintaan approval / tanda tangan BAST
```
Selamat siang Bapak/Ibu <Nama>,
<Deliverable> telah selesai dan direview bersama pada <tgl>.
Terlampir Berita Acara <BAST/…No.> untuk ditandatangani.
Mohon bantuannya agar dapat kami terima kembali paling lambat <tgl>.
Bila ada catatan, kami siap bahas. Terima kasih.
```

## T9 — Info jadwal rapat/workshop
```
Selamat pagi Bapak/Ibu,
Mengundang <peserta> untuk <workshop/rapat> <topik>:
🗓 <Hari, tgl> · ⏰ <jam> WIB · 📍 <lokasi/link>
Persiapan: <yang perlu dibawa>. Mohon konfirmasi kehadiran 🙏
```

## T10 — Rekap mingguan singkat di grup (Jumat, setelah laporan formal terkirim)
```
Selamat sore Bapak/Ibu, rekap proyek minggu ke-<n>:
Status: <🟢/🟡/🔴> · Progress <x>% (rencana <y>%)
Selesai: <1–2 hal>
Minggu depan: <1–2 hal>
Mohon bantuan: <item pending klien + tgl>
Laporan lengkap sudah kami kirim via email. Selamat berakhir pekan 🙏
```

## T11 — Internal [INT] reminder harian (agent boleh kirim langsung)
```
☀️ Chaser <tgl> — <Kode Proyek>
Lewat tenggat:
• <AI-xxx> <item> — @<PIC> — H+<n>
Jatuh tempo hari ini:
• <AI-xxx> <item> — @<PIC>
Mohon update status di lab0 sebelum 16.00. Kendala → balas di thread ini.
```

## T12 — Laporan per jam saat cutover (draft untuk [WAR])
```
⏱ Update Cutover <jam> WIB
Selesai: <langkah #, ringkas>
Berjalan: <langkah #> (ETA <jam>)
Isu: <tidak ada / I-xxx singkat>
Status vs rencana: <on time / +<n> menit>
Rollback point berikutnya: <jam>
```
