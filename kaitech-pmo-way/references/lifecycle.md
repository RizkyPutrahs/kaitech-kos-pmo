# Lifecycle Proyek Kaitech F0–F9

Setiap fase punya: tujuan, entry criteria, aktivitas PMO, artefak wajib, exit criteria (gate),
dan approver. Gate **tidak boleh dilewati** tanpa approval manusia yang tercatat di lab0.
Jika satu exit criterion belum terpenuhi, gate boleh dilewati **bersyarat** hanya dengan
DEC (Decision) tertulis dari approver + action item penutup dengan tenggat.

---

## F0 — Persiapan (handover + setup, 10 hari kerja)
Lihat skill `project-setup` untuk urutan dan gate **Siap Mulai** (tanpa gate hijau tidak ada kickoff).

### F0a — Handover Sales → Delivery
**Tujuan:** tidak ada janji sales yang hilang atau tidak tercatat.
**Entry:** deal berstatus Won di CRM; kontrak/SPK/PO diterima atau LoI ditandatangani.
**Aktivitas PMO:**
1. Kumpulkan: kontrak/SPK, proposal final, KAK/RKS (bila tender), daftar modul, nilai & termin
   pembayaran, notulen presales, janji lisan sales (wawancara Sales, catat sebagai asumsi).
2. Susun **Handover Checklist** dan **daftar janji sales** → setiap janji jadi baris di
   Assumption log (`A-xxx`) berstatus "perlu dikonfirmasi ke klien".
3. Identifikasi gap proposal vs kontrak (modul, jumlah user, durasi, termin, denda).
4. Tetapkan PM, PMO, lead BA, lead IT. Buat project di lab0 (`PRJ-xxxx`).
**Artefak:** Handover Checklist, Assumption log awal, ringkasan kontrak (scope, termin, denda,
masa garansi/hypercare, SLA).
**Exit G0:** dokumen kontraktual terunggah, PM ditetapkan, gap proposal–kontrak terdaftar.
**Approver:** PMO Lead (Rizky) + Head of BA.

## F1 — Initiation & Kickoff
**Tujuan:** sponsor, struktur, dan aturan main disepakati.
**Entry:** G0 lulus.
**Aktivitas PMO:**
1. Draft **Project Charter**: latar belakang, tujuan bisnis terukur, scope in/out, asumsi,
   batasan, milestone tingkat tinggi, struktur proyek (Steerco, Sponsor, PM kedua pihak,
   key user per modul), toleransi.
2. **Stakeholder Register** + analisis power/interest + preferensi komunikasi.
3. **Communication Plan**: ritme rapat (weekly, steerco bulanan), format laporan, kanal WA
   (skill `wa-pmo-playbook`), matriks eskalasi kedua pihak.
4. Siapkan grup WA (internal, proyek-klien, steerco bila perlu) dengan pesan pin standar.
5. Deck kickoff; jadwalkan kickoff dengan sponsor hadir (jangan kickoff tanpa sponsor).
**Artefak:** Charter, Stakeholder Register, RACI tingkat tinggi, Communication Plan, deck &
MoM kickoff, daftar key user.
**Exit G1:** charter disetujui sponsor klien, kickoff terlaksana, key user per modul
ditunjuk tertulis (surat/email/memo internal klien). **Approver:** Sponsor klien + Khusnul.

## F2 — Planning & Baseline
**Tujuan:** rencana realistis, disepakati, dan dikunci.
**Entry:** G1 lulus.
**Aktivitas PMO:** (detail di skill `baseline-planning`)
1. WBS sampai level deliverable (maks 80 jam per work package).
2. Estimasi effort, dependensi, critical path, buffer.
3. Kalender: libur nasional, cuti bersama, closing bulanan klien, periode freeze (Lebaran,
   akhir tahun anggaran), ketersediaan key user.
4. Milestone & termin billing dipetakan ke deliverable yang bisa dibuktikan.
5. Resource plan + cek kapasitas lintas proyek (agent Resource).
6. Risk register awal (minimal 10 risiko standar ERP, lihat `raid-management`).
**Artefak:** WBS, jadwal baseline v1.0, milestone & billing plan, resource plan, risk register.
**Exit G2:** baseline disetujui PM klien & sponsor, dikunci di lab0 (v1.0).
**Approver:** PM Kaitech + Sponsor/PM klien.

## F3 — Discovery & Blueprint
**Tujuan:** kebutuhan terdokumentasi, terverifikasi, ditandatangani.
**Entry:** G2 lulus; key user tersedia sesuai jadwal workshop.
**Aktivitas PMO:** jadwal workshop per divisi, kehadiran key user, MoM ≤ 1 hari kerja,
artefak Discovery mengalir; permintaan di luar scope → CR. Setiap GAP-CUSTOM punya estimasi
dan keputusan (dalam scope atau CR).
**Artefak:** MoM workshop, BRD, FSD, Fit-Gap (FIT/GAP-CONFIG/GAP-CUSTOM), daftar CR kandidat.
**Exit G3:** BRD/FSD/Fit-Gap ditandatangani key user & sponsor; semua GAP-CUSTOM diputuskan.
**Approver:** Key user per modul + Sponsor klien.

## F4 — Build & Configuration
**Tujuan:** sistem dibangun sesuai blueprint dan teruji internal.
**Entry:** G3 lulus (atau bersyarat untuk modul yang sudah final).
**Aktivitas PMO:** task IT, iterasi mingguan, demo ke key user maks tiap 2 minggu (mencegah
kejutan di UAT), QA gate Kai QA Agent, kontrol perubahan konfigurasi.
**Artefak:** log konfigurasi, modul kustom + dokumentasi teknis, hasil QA/SIT.
**Exit G4:** SIT lulus (0 defect Kritis; Tinggi ≤ 3 dengan rencana perbaikan).
**Approver:** Lead tim IT + QA.

## F5 — Data Migration
**Tujuan:** data bersih dan termigrasi akurat.
**Entry:** template migrasi disepakati; data owner klien ditunjuk.
**Aktivitas PMO:** jadwal ekstraksi → cleansing → mock load 1 → mock load 2 → final load.
Keterlambatan data dari klien adalah penyebab delay paling umum: catat sebagai dependency
`D-xxx` milik klien dengan tanggal komitmen dan nama penanggung jawab.
**Artefak:** strategi migrasi, template, laporan rekonsiliasi per mock load.
**Exit G5:** mock load ke-2 lulus rekonsiliasi (saldo GL, stok, AR/AP cocok), disetujui data
owner. **Approver:** Data owner klien.

## F6 — UAT & Training
**Tujuan:** user menerima sistem dan siap memakainya.
**Entry:** G4 & G5 lulus; skenario UAT disetujui.
**Aktivitas PMO:** jadwal UAT per modul (hindari tanggal closing akuntansi klien), log defect,
retest, training key user & end user (train-the-trainer), daftar hadir sebagai bukti.
**Artefak:** skenario UAT, log defect, berita acara UAT, materi & absensi training.
**Exit G6:** UAT sign-off per modul; kehadiran training ≥ 90% peserta wajib.
**Approver:** Key user + Sponsor.

## F7 — Cutover & Go-Live
**Tujuan:** pindah ke sistem baru tanpa kehilangan data dan tanpa operasional berhenti.
**Entry:** G6 lulus.
**Aktivitas PMO:** cutover plan jam-per-jam (siapa, apa, kapan, titik rollback), freeze
transaksi lama, go/no-go meeting H-2 dengan checklist, war-room WA, laporan per jam.
**Artefak:** cutover plan, go/no-go checklist, rollback plan, laporan go-live.
**Exit G7:** keputusan GO tercatat (DEC) dan go-live terjadi. **Approver:** Steerco.

## F8 — Hypercare
**Tujuan:** stabilisasi.
**Aktivitas PMO:** tiket harian, SLA per prioritas, laporan harian minggu 1–2 lalu mingguan.
KPI stabilisasi: tiket baru/hari turun, tidak ada tiket Kritis 5 hari kerja berturut.
**Artefak:** log tiket, laporan hypercare, daftar outstanding.
**Exit G8:** kriteria exit hypercare di kontrak terpenuhi. **Approver:** Sponsor klien.

## F9 — Closure
**Tujuan:** ditutup secara kontraktual, finansial, dan pengetahuan.
**Aktivitas PMO:** BAST akhir, pelunasan termin, serah terima dokumen & akses, transisi ke
support/retainer, lessons learned (internal & bersama klien), arsip, usulan perbaikan skill.
**Artefak:** BAST akhir, closure report, lessons learned, usulan perbaikan skill.
**Exit G9:** BAST akhir ditandatangani; invoice akhir terbit. **Approver:** Khusnul + Sponsor.
