# Agent Accountability

## Status
`NOT STARTED`, `RUNNING`, `COMPLETED`, `FAILED`, `BLOCKED`, `NOT EXECUTED`.

Jika spawn ditolak atau tool tidak tersedia, catat error dan tandai FAILED/BLOCKED/NOT EXECUTED sesuai keadaan. Jangan klaim agent selesai jika thread dan hasilnya tidak ada. Single-agent fallback harus disebutkan transparan dan tidak menggantikan independent review.

## Execution ledger
Catat Task ID, role, delegation attempted, thread created, result received, status, scope, evidence, findings, dan handoff.

## Finding
Setiap finding: ID unik, severity, title, file/symbol/line, trigger, impact, evidence, recommendation, owner, status, verification.

## Test evidence
Catat command persis, environment tanpa secret, expected, actual, PASS/FAIL/BLOCKED/NOT EXECUTED, dan artifact path aman. Build PASS bukan bukti seluruh business rules benar.

## Laporan
Pisahkan verified facts, assumptions, unknowns, failed checks, unexecuted checks, dan approval required.
