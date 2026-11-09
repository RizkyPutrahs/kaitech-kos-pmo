---
name: delivery-guardrails
description: Use when memeriksa apakah pekerjaan proyek mematuhi aturan main Kaitech (alur dev-staging-prod, change ticket, data produksi, kredensial, akses MCP, kanal komunikasi) atau saat menulis pesan pin aturan main. Don't use when menyusun rencana atau laporan status.
slug: delivery-guardrails
---

# Delivery Guardrails

## Teknis
1. Alur: feature → dev (agent boleh merge setelah CI) → staging (review lead IT + QA) → main → prod.
   Agent tidak pernah merge ke staging/main.
2. Rilis prod hanya di jendela rilis (Selasa–Kamis setelah jam kerja klien), dengan change ticket:
   isi, approver (lead IT + PM; klien untuk rilis besar), backup, rollback, release note.
   Tidak ada rilis Jumat sore, menjelang libur panjang, atau saat closing untuk modul keuangan.
3. Hotfix: branch dari main, lead menyetujui, merge balik, laporan insiden ≤ 2 hari kerja.
4. Data prod tidak pernah ke dev; staging dianonimkan; koreksi data prod via skrip yang direview
   + persetujuan tertulis data owner.
5. Kredensial hanya di secret manager/secret Paperclip; akun per orang; admin prod ≤ 2 orang Kaitech;
   akses dicabut di hari yang sama saat orang keluar proyek.
6. Agent tanpa akses tulis prod; hasil agent direview manusia sebelum staging atau klien.
7. MCP: service account per environment, hak minimum, audit, rate limit, IP allowlist,
   rotasi kunci 3 bulanan dan saat close.

## Komunikasi
8. Satu juru bicara per pihak. Biaya/jadwal/scope → email + CR, bukan WA.
9. Keputusan lisan/WA dikonfirmasi tertulis ≤ 1 hari kerja (DEC di lab0).
10. Masalah internal tidak pernah di grup klien. Agent tidak pernah di grup eksternal.
11. Urutan bukti: kontrak > surat resmi > email > MoM disetujui > konfirmasi WA tertulis > WA biasa.

## Saat menemukan pelanggaran
Catat fakta (apa, kapan, siapa, bukti) → Issue di RAID → alert sesuai skill alert-rules
(perubahan prod tanpa ticket = Critical #14). Jangan menegur orang secara langsung.
