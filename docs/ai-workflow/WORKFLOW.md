# Workflow

## Stage 0 — Intake
Orchestrator memahami permintaan, acceptance criteria, branch, `git status --short`, local modifications, risiko, dan scope.

## Stage 1 — Audit
Gunakan `architect_security` untuk architecture, data flow, business rules, transaction integrity, dan security. QA dapat melakukan inventory test suite secara read-only. Jangan jalankan Developer pada tahap audit.

## Stage 2 — Plan & approval
Orchestrator mengelompokkan temuan, menentukan prioritas, acceptance criteria, file scope, risiko, dan approval yang diperlukan.

## Stage 3 — Implementation
Gunakan `developer`. Satu owner per kelompok file. Jangan parallel edit file yang sama. Perubahan di luar scope harus dihentikan dan diajukan.

## Stage 4 — QA
Gunakan `qa_uiux` untuk unit/integration/E2E, business rules, failure paths, permission, responsive UI. QA tidak memperbaiki source.

## Stage 5 — Independent review
Gunakan `reviewer_finalqc` untuk review diff dan evidence. Jika ada temuan, kembali ke implementation, lalu ulangi QA/review pada perubahan terkait.

## Stage 6 — Human release gate
Orchestrator menyajikan perubahan, file, temuan tersisa, hasil test, status agent, residual risk, dan tindakan yang butuh approval. Human owner menyetujui production.

## Pemilihan agent
- Penjelasan sederhana: Orchestrator saja.
- Audit arsitektur/security: Architect & Security.
- Bug kecil: Developer → QA/Reviewer sesuai risiko.
- Inventory/transaction/auth: Architect → Developer → QA → Reviewer.
- Release candidate: QA → Reviewer.
- Production incident: Architect read-only lalu human approval.

## Definition of Done
Acceptance criteria terpenuhi; business rules tidak berubah tanpa approval; test relevan lulus; independent review selesai; tidak ada Critical/High unresolved tanpa penerimaan risiko formal; laporan agent akurat; tidak ada perubahan production tanpa persetujuan.
