# Glowviera Codex Multi-Agent Workflow — 5 Roles

Paket ini menyiapkan workflow yang mengutamakan stabilitas, integritas data, keamanan, auditability, dan release gate.

## Model 5 peran
1. Orchestrator / Technical Lead — agent utama Codex, bukan subagent tambahan.
2. Architect & Security — subagent audit arsitektur, data, business rules, dan keamanan.
3. Developer — subagent implementasi perubahan yang disetujui.
4. QA & UI/UX Auditor — subagent pengujian dan audit pengalaman pengguna.
5. Independent Reviewer & Final QC — subagent review independen dan release gate.

Jadi ada empat custom subagent, dikoordinasikan oleh agent utama. Jangan menjalankan semuanya untuk setiap tugas.

## Isi
- `AGENTS.md`: aturan utama repository.
- `.codex/config.toml`: pengaturan multi-agent dan registrasi role.
- `.codex/agents/*.toml`: empat custom subagent.
- `docs/ai-workflow/`: workflow, accountability, guardrails, checklist, dan prompt.

## Catatan
- Backup/commit kondisi repository sebelum instalasi.
- Jangan overwrite `AGENTS.md` atau `.codex/config.toml` yang sudah ada; merge manual.
- Custom agents mewarisi permission/sandbox sesi induk. Instruksi read-only bukan security boundary.
- Model tidak dipatok agar mewarisi model sesi induk dan menghindari model yang tidak tersedia.
- Tidak ada credential, token, atau DATABASE_URL dalam paket ini.

Dokumentasi: https://learn.chatgpt.com/docs/agent-configuration/subagents
