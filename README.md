# SystemResizer-garnet

SystemResizer untuk flash GSI di Xiaomi Poco X6 5G (garnet).
Group dynamic partition: `qti_dynamic_partitions`.

Isi zip ada di folder `src/`. Ubah ukuran system di `src/dynamic_partitions_op_list`, lalu push, zip dibuild otomatis di tab Actions (Artifacts).
Untuk rilis: `git tag v1.0 && git push --tags`.

Pakai: flash zip di recovery, lalu flash GSI ke system, format data, reboot.
