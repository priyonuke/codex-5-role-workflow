# Prompt Library

## 1. Initial read-only audit
Baca `AGENTS.md` dan `docs/ai-workflow/`. Jangan mengubah file, database, environment, secret, deployment, atau production.
Delegasikan `architect_security` untuk audit architecture/data/business rules/security dan `qa_uiux` untuk inventory test suite serta critical journeys. Tunggu hasil subagent yang benar-benar berhasil dibuat. Jika spawn gagal, catat error dan status NOT EXECUTED/BLOCKED. Jangan implementasi. Hasilkan findings ber-ID, severity, evidence, impact, dan rekomendasi.

## 2. Approved implementation
Implementasikan hanya finding: [FINDING ID].
Acceptance criteria: [CRITERIA].
Scope file: [FILE/AREA].
Out of scope: [LIMITS].
Periksa `git status --short`, pertahankan local modifications, gunakan developer, lakukan perubahan minimal, tambahkan test, dan jangan ubah schema/secret/production/deployment tanpa approval terpisah.

## 3. QA
Delegasikan `qa_uiux` untuk menguji [TASK ID] berdasarkan acceptance criteria. Jangan ubah source. Jalankan test relevan yang ditemukan di repository. Laporkan command, expected, actual, dan PASS/FAIL/BLOCKED/NOT EXECUTED.

## 4. Independent review
Delegasikan `reviewer_finalqc` untuk meninjau diff dan evidence. Jangan edit source. Periksa correctness, security, authorization, data integrity, race conditions, test coverage, business rules, dan scope creep. Put findings first. Keputusan: BLOCKED, NOT READY, atau READY FOR HUMAN APPROVAL.

## 5. Security incident — read-only
Jangan rotasi/revoke credential, ubah secret, restart, migration, deploy, atau ubah production data.
Verifikasi akun, project/environment/service mapping, exposure location tanpa nilai secret, dependency, dan audit log yang tersedia. Jika CLI/MCP/browser unavailable atau Unauthorized, tandai BLOCKED. Jangan menyimpulkan credential aman. Sajikan rencana remediation untuk human approval.

## 6. Final release assessment
Kumpulkan laporan Architect, Developer, QA, Reviewer. Verifikasi execution ledger dan test evidence. Laporkan unresolved findings, business rules, security status, residual risk, dan approval yang diperlukan. Jangan deploy. Status tertinggi `READY FOR HUMAN APPROVAL`.
