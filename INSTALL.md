# Instalasi aman

1. Buka root repository di VS Code.
2. Backup atau commit kondisi repository saat ini.
3. Ekstrak paket ke folder sementara.
4. Salin `AGENTS.md`, `.codex/`, dan `docs/ai-workflow/` ke root repository.
5. Jika file tujuan sudah ada, jangan overwrite. Merge manual.
6. Jika `.codex/config.toml` sudah ada, gabungkan tabel `[agents]` dan role tables; pertahankan seluruh setting existing seperti MCP, model, sandbox, dan approval.
7. Restart Codex/VS Code bila agent belum terdeteksi.
8. Jalankan smoke test di bawah.

## Smoke test (read-only)
Baca AGENTS.md dan docs/ai-workflow/WORKFLOW.md. Jangan mengubah file.
Verifikasi custom agent architect_security, developer, qa_uiux, dan reviewer_finalqc terdeteksi.
Delegasikan audit read-only singkat kepada architect_security dan qa_uiux. Jangan jalankan developer.
Tunggu hasil agent yang benar-benar berhasil dibuat. Laporkan COMPLETED, FAILED, BLOCKED, atau NOT EXECUTED.
Jangan mengklaim delegasi yang tidak terjadi.

Jika spawn tidak tersedia, catat error dan gunakan fallback single-agent secara transparan.
Jangan memberi semua agent akses unrestricted untuk mengatasi masalah.

## Rollback
Hapus hanya file custom agent yang ditambahkan paket ini dan revert hanya perubahan config yang dibuat.
Jangan menghapus seluruh `.codex` jika berisi konfigurasi existing.
