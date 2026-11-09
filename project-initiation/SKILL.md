---
name: project-initiation
description: Use when proyek baru masuk dari Sales (F0 handover) atau sedang disiapkan kickoff (F1) untuk menyusun handover checklist, daftar janji sales, project charter, stakeholder register, communication plan, dan setup grup WA. Don't use when proyek sudah melewati G1.
slug: project-initiation
---

# Project Initiation (F0–F1)

## A. Handover Sales → Delivery (F0)

Langkah berurutan:
1. Tarik dari lab0/CRM: kontrak/SPK/PO, proposal final, KAK/RKS, nilai & termin, notulen
   presales. Jika ada yang tidak ditemukan → Action Item ke Sales, tenggat 2 hari kerja.
2. Isi **Handover Checklist** (semua wajib ✓ sebelum G0):
   - [ ] Kontrak/SPK ditandatangani terunggah
   - [ ] Scope modul & jumlah user tercatat
   - [ ] Termin pembayaran & syarat penagihan tiap termin
   - [ ] Klausul denda keterlambatan (nilai, batas maksimum, pemicu)
   - [ ] Durasi proyek & tanggal go-live yang dijanjikan
   - [ ] Masa hypercare/garansi & SLA
   - [ ] Kontak sponsor & PM klien
   - [ ] Janji lisan Sales terdaftar sebagai asumsi
3. **Wawancara janji sales**: buat issue untuk Head of Sales/Khusnul berisi pertanyaan:
   "Apa yang dijanjikan di luar dokumen? Demo apa yang ditunjukkan? Siapa yang paling
   berpengaruh di klien? Apa kekhawatiran klien yang muncul saat presales?" Setiap jawaban →
   `A-xxx` (asumsi) atau `R-xxx` (risiko).
4. **Gap proposal vs kontrak**: tabel 3 kolom (Item · Proposal · Kontrak). Perbedaan apa pun
   adalah risiko scope; kirim ke PM manusia sebelum kickoff.
5. Draft keputusan penetapan tim (PM, BA lead, IT lead) untuk approval PMO Lead.

## B. Project Charter (F1) — struktur wajib

1. Identitas proyek (PRJ, klien, nilai kontrak tidak ditulis di versi untuk klien jika
   internal saja), sponsor, PM kedua pihak.
2. Latar belakang & masalah bisnis.
3. **Tujuan bisnis terukur** (minimal 3, format SMART). Contoh: "Closing bulanan dari H+15
   menjadi H+5 dalam 3 bulan setelah go-live."
4. Scope in / scope out (eksplisit; scope out sama pentingnya).
5. Deliverable utama & kriteria penerimaan.
6. Milestone tingkat tinggi (F-level) dan termin terkait.
7. Asumsi & batasan (termasuk kewajiban klien: key user, data, infrastruktur, akses).
8. Struktur organisasi proyek: Steerco, Sponsor, PM, key user per modul, data owner.
9. Toleransi & jalur eskalasi (dari `kaitech-pmo-way` §5).
10. Risiko awal teratas (5).
11. Persetujuan (nama, jabatan, tanggal).

Kewajiban klien **harus tertulis** di charter. Tanpa ini, setiap keterlambatan klien
akan dianggap keterlambatan Kaitech.

## C. Stakeholder Register

Kolom: Nama · Jabatan · Organisasi · Peran proyek · Power (1–5) · Interest (1–5) ·
Sikap (Pendukung/Netral/Skeptis/Penentang) · Kanal & jam preferensi · Grup WA ·
Catatan (mis. closing tgl 1–5, sering dinas luar).
Strategi per kuadran: Power tinggi–Interest tinggi = kelola dekat (steerco, update personal
oleh Khusnul/PM); Power tinggi–Interest rendah = jaga puas (ringkasan bulanan);
Power rendah–Interest tinggi = jaga informasi (grup [PRJ], demo); lainnya = pantau.
Skeptis/penentang berpengaruh → otomatis `R-xxx` adopsi.

## D. Communication Plan

| Komunikasi | Frekuensi | Audiens | Pemilik | Kanal | Artefak |
|---|---|---|---|---|---|
| Weekly progress meeting | Mingguan | PM & key user | PM Kaitech | Meet/onsite | MoM ≤ 1 hari kerja |
| Laporan status mingguan | Jumat 12:00 | PM & sponsor klien | PM Kaitech | Email + rekap WA | Word + PDF |
| Steering committee | Bulanan / per gate | Steerco | Khusnul + PM | Onsite | Deck + MoM |
| Reminder harian | Harian | Tim internal | Chaser | WA [INT] | — |
| Koordinasi operasional | Ad hoc | Tim kedua pihak | PM | WA [PRJ] | DEC/AI di lab0 |

## E. Setup WA

Buat draft pembentukan grup sesuai `wa-pmo-playbook` §1 dan pesan pin standar. PM manusia
yang membuat grup dan memasang pin.

## F. Deck & agenda kickoff

Agenda 90 menit: pembukaan sponsor (10) · tujuan & scope (15) · metodologi & lifecycle F0–F9
(15) · jadwal & milestone (15) · struktur & peran, termasuk kewajiban klien (15) · cara kerja
& komunikasi, termasuk aturan WA (10) · risiko awal & next steps (10).
