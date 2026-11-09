---
name: kaitech-pmo-way
description: Use when melakukan pekerjaan PMO apa pun di proyek Kaitech (rencana, progress, eskalasi, RAID, CR, laporan, gate) untuk memakai definisi, penomoran, status, aturan RAG, dan lifecycle baku Kaitech. Don't use when task murni teknis coding atau konfigurasi Odoo tanpa aspek manajemen proyek.
slug: kaitech-pmo-way
---

# Kaitech PMO Way — standar dasar semua agent PMO

Skill ini adalah "bahasa bersama". Semua agent PMO memakai definisi yang SAMA agar angka,
status, dan istilah di lab0, laporan, dan WA konsisten. Jika ada konflik antara skill lain
dan skill ini, skill ini yang menang, kecuali instruksi eksplisit dari human penanggung jawab.

## 1. Tujuh prinsip yang tidak bisa ditawar

1. **Satu sumber kebenaran: lab0.** Angka yang tidak bisa ditelusuri ke record lab0 tidak
   boleh muncul di laporan.
2. **Progress = bukti.** Tidak ada persentase tanpa bukti yang tertaut (lihat skill
   `evidence-progress`). "Sudah 80% Pak" di WA bukan progress.
3. **Baseline itu kontrak.** Setelah G2, tanggal dan scope baseline hanya berubah lewat
   Change Request yang disetujui. Forecast boleh bergerak; baseline tidak.
4. **Management by exception.** Laporkan deviasi yang melewati toleransi, bukan semua hal.
   Toleransi default ada di bagian 5.
5. **Tulis untuk diaudit.** Klien BUMN dan auditor Big 4 akan bertanya "kapan diputuskan,
   oleh siapa, buktinya mana". Setiap keputusan punya tanggal, pemutus, dan referensi.
6. **Draft oleh AI, keputusan oleh manusia.** Agent tidak pernah mengirim ke klien,
   menandatangani, menyetujui CR, atau mengubah baseline.
7. **Jangan menebak.** Data kurang → tandai `[DATA KURANG]`, buat action item untuk
   melengkapi, dan lanjutkan bagian lain.

## 2. Penomoran baku

| Objek | Format | Contoh |
|---|---|---|
| Proyek | `PRJ-<NNNN>` | PRJ-0012 |
| Fase | `F0`–`F9` | F3 |
| Gate | `G0`–`G9` | G2 |
| WBS | `<Fase>.<n>.<n>` | 3.2.1 |
| Milestone | `MS-<NN>` | MS-04 |
| Risk / Assumption / Issue / Dependency / Decision | `R-` `A-` `I-` `D-` `DEC-` + `<NNN>` | R-007, DEC-015 |
| Change Request | `CR-<NNN>` | CR-003 |
| Action item | `AI-<NNN>` | AI-042 |
| BAST | `BAST/<PRJ>/<NN>/<bulan romawi>/<tahun>` | BAST/PRJ-0012/02/XI/2026 |
| Laporan | `RPT-W<minggu ISO>-<tahun>` | RPT-W45-2026 |

## 3. Kosakata status (wajib persis)

- Task / deliverable: `Belum Mulai` · `Berjalan` · `Review Internal` · `Review Klien` ·
  `Diterima` · `Ditunda` · `Dibatalkan`
- RAID: `Terbuka` · `Dalam Mitigasi` · `Menunggu Klien` · `Ditutup`
- CR: `Draft` · `Diajukan` · `Dianalisis` · `Menunggu Keputusan` · `Disetujui` · `Ditolak` ·
  `Ditunda`
- Action item: `Terbuka` · `Selesai` · `Lewat Tenggat` · `Dibatalkan`
- Milestone: `Dijadwalkan` · `Berisiko` · `Tercapai` · `Terlambat`

## 4. Waktu dan kalender

- Zona waktu **WIB (UTC+7)**, kecuali klien menyatakan WITA/WIT. Tulis zona jika lintas zona.
- Format tanggal di laporan: `12 Nov 2026`. Di data/Excel: `2026-11-12`.
- **Hari kerja** = Senin–Jumat, di luar libur nasional dan cuti bersama SKB 3 Menteri tahun
  berjalan, dan di luar hari libur internal klien yang tercatat di stakeholder register.
- Semua umur/tenggat dihitung dalam **hari kerja**, kecuali disebut "hari kalender".

## 5. Toleransi default (PRINCE2-style) — melewati ini = eksepsi, wajib eskalasi

| Dimensi | Toleransi PM | Lewat → eskalasi ke |
|---|---|---|
| Jadwal milestone | ≤ 5 hari kerja dari baseline | PMO Lead → Khusnul |
| Jadwal go-live | 0 hari (setiap pergeseran) | Steerco |
| Effort fase | ≤ 10% di atas baseline mandays | PMO Lead → GM IT |
| Scope | 0 (semua perubahan via CR) | PM → Sponsor klien |
| Biaya/margin proyek | margin turun ≤ 5 poin | Khusnul |
| Risiko | skor ≥ 15 atau dampak go-live | PMO Lead → Steerco |

## 6. Aturan RAG (dipakai di semua laporan)

RAG keseluruhan berasal dari **Health Score** (skill `health-score`):
- **Hijau** ≥ 80 · **Kuning** 60–79 · **Merah** < 60.
- Override otomatis ke **Merah**: milestone billing bergeser > 10 hari kerja, isu kritis
  memblokir go-live, atau sponsor klien menyatakan ketidakpuasan tertulis.
- Agent **tidak boleh menaikkan** warna di atas hasil hitung. Human boleh, dengan alasan
  tertulis yang dicatat di Project Update lab0.
- Dilarang "watermelon reporting" (hijau di luar, merah di dalam). Jika ragu antara dua
  warna, pilih yang lebih buruk dan jelaskan.

## 7. Gaya tulis

- Bahasa Indonesia baku-bisnis; istilah teknis/PM boleh Inggris (baseline, cutover, UAT).
- Kalimat pertama = kesimpulan. Konteks setelahnya.
- Setiap masalah ditulis: **apa – dampak – penyebab – tindakan – PIC – tenggat**.
- Fakta `[OBSERVED]` (tertaut ke record) dibedakan dari `[DUGAAN]`.
- Nama orang klien: gunakan sapaan (Bapak/Ibu) dan jabatan di dokumen formal.

## 8. Referensi

- `references/lifecycle.md` — F0–F9, entry/exit criteria, artefak, approver per gate.
- `references/definitions.md` — glosarium dan definisi metrik.
- `references/standards-mapping.md` — pemetaan ke PMBOK 7, PRINCE2 7, ISO 21502.
