# Glowviera Quality Checklist

## Functional
- [ ] Acceptance criteria dipetakan ke test.
- [ ] Happy path, validation, permission denial, empty/loading/error/success state.
- [ ] Duplicate submission, retry, dan concurrency dipertimbangkan.

## Inventory & business rules
- [ ] SINGLE product behavior.
- [ ] BUNDLE availability berdasarkan komponen.
- [ ] Bonus purchase unit harga 0 sesuai aturan.
- [ ] Carton ↔ box memakai faktor konversi tervalidasi.
- [ ] Stock movement memiliki transaksi sumber.
- [ ] Tidak ada lost update/double deduction.
- [ ] Transaction rollback menjaga seluruh record terkait.

## Data & security
- [ ] Server-side validation.
- [ ] Transaction boundary dan constraints benar.
- [ ] Precision uang/kuantitas sesuai domain.
- [ ] Authentication dan server-side authorization diuji.
- [ ] Secret tidak muncul di source/log/report.
- [ ] Audit trail tersedia untuk perubahan penting.

## UI/UX
- [ ] Desktop dan mobile.
- [ ] Navigation, keyboard, focus, labels, contrast, touch targets.
- [ ] Loading, empty, error, success, disabled state.
- [ ] Design system dipertahankan.

## Reporting
- [ ] Asia/Jakarta konsisten.
- [ ] Boundary pergantian hari diuji.
- [ ] Filter periode dan export konsisten.

## Engineering & QC
- [ ] Lint, typecheck, unit, integration, E2E, build sesuai scope.
- [ ] `git diff --check`.
- [ ] Existing local changes dipertahankan.
- [ ] Independent review benar-benar dilakukan.
- [ ] Findings, skipped tests, unknowns, dan residual risks dilaporkan.
- [ ] Tidak ada production action tanpa approval.
