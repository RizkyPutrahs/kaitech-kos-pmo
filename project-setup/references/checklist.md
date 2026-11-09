# Checklist F0 per area

## Tim manusia
- [ ] RACI per deliverable (Kaitech & klien) masuk charter
- [ ] Kapasitas: tidak ada orang > 100% di 8 minggu pertama
- [ ] Cadangan untuk tiap peran kunci (modul kustom, migrasi)
- [ ] Kontak klien: nama, jabatan, kanal, jam kerja, periode closing, rantai paraf dokumen

## Tim AI (Paperclip)
- [ ] Project Paperclip + goal tertaut ke goal perusahaan
- [ ] Agent tim ditetapkan lead IT; pembagian kerja AI vs manusia tertulis
- [ ] Secret dev/staging sebagai secret Paperclip, hanya untuk agent proyek ini
- [ ] Isolated Workspaces aktif bila > 1 agent di repo yang sama

## WA & email
- [ ] [INT] (bot PMO ikut) · [PRJ] (tanpa bot, pin dipasang PM) · [MGT] bila perlu · milis

## Odoo
- [ ] Versi, edisi, modul sama di dev/staging/prod
- [ ] Hosting & pemilik server prod tertulis sesuai kontrak
- [ ] Staging dianonimkan (UU No. 27/2022 Pelindungan Data Pribadi)
- [ ] Backup prod harian + uji restore sebelum go-live

## Git
- [ ] Repo privat, akses per orang; `main` & `staging` diproteksi
- [ ] CI: lint, install modul di DB kosong, unit test
- [ ] Template PR: ID task lab0, cara uji, dampak migrasi

## MCP
- [ ] Service account per environment, hak minimum, audit log, rate limit, IP allowlist
- [ ] Agent dev: dev tulis, staging baca, prod tidak ada
- [ ] Prod: tanpa akses tulis agent; untuk BUMN self-hosted

## Sambungan
- [ ] ID task lab0 di setiap commit, PR, issue Paperclip
- [ ] Webhook PR merged → lab0 (bukti progress)
- [ ] Connector GitHub Paperclip dibatasi ke repo proyek
