# Security & Production Guardrails

Default audit adalah read-only. Gunakan local/test/staging dan data sintetis.

## Approval eksplisit diperlukan untuk
- Rotasi/pencabutan credential.
- Perubahan secret store atau production environment variables.
- Production database writes/data correction.
- Production schema change/migration.
- Deployment, rollback, restart, service config.
- DNS/domain/SSL changes.
- Menghapus audit log/bukti insiden.
- Mengekspor data pelanggan.

Approval satu tindakan tidak otomatis mengizinkan tindakan lain.

## Credential exposure
1. Jangan tampilkan nilai credential.
2. Catat lokasi/jenis exposure tanpa secret.
3. Perlakukan credential sebagai berpotensi aktif sampai pencabutan diverifikasi.
4. Verifikasi service/dependency mapping dengan akses sah.
5. Susun rencana rotasi dan dependency.
6. Minta approval eksplisit.
7. Uji credential baru dengan aman.
8. Cabut credential lama setelah dependency siap.
9. Periksa audit log jika tersedia; nyatakan keterbatasan jika tidak.
10. Dokumentasikan waktu/hasil tanpa secret.

## Railway/cloud
CLI login bukan bukti MCP connected. MCP connected bukan bukti project/environment/service terverifikasi. Jika CLI/MCP/browser Unauthorized atau unavailable, tandai BLOCKED. Jangan menyimpulkan credential aman atau log bersih.

## Human approval
Sebut tindakan, target project/environment/service, dampak/downtime, rollback, apakah restart/deploy/migration diperlukan, dan tindakan yang tidak termasuk approval.

`READY FOR HUMAN APPROVAL` bukan persetujuan deploy.
