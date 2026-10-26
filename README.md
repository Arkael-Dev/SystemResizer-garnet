# SystemResizer-garnet

SystemResizer untuk flash GSI di Xiaomi Poco X6 5G (garnet).
Group dynamic partition: `qti_dynamic_partitions`.

## Wajib: disable vbmeta

Sebelum boot GSI, **vbmeta wajib dimatikan** (pakai `vbmeta.img` dari firmware stok garnet). Kalau tidak, HP bisa bootloop atau kembali ke fastboot/recovery.

```
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
```

Kalau perlu, flash ke kedua slot:

```
fastboot --disable-verity --disable-verification flash vbmeta_a vbmeta.img
fastboot --disable-verity --disable-verification flash vbmeta_b vbmeta.img
```

## Cara pakai

1. Backup data dan siapkan firmware stok.
2. Disable vbmeta (langkah di atas).
3. Masuk recovery custom, lalu flash `SystemResizer-garnet.zip`. Jangan reboot.
4. Flash GSI `.img` ke partisi **system** (Install Image, target System Image).
5. Format data, lalu reboot.

## Build

Isi zip ada di folder `src/`. Ubah ukuran system di `src/dynamic_partitions_op_list`, lalu push. Zip dibuild otomatis di tab Actions (Artifacts).

Untuk rilis:

```
git tag v1.1 && git push --tags
```

## Sumber

`update-binary` dan data patch berasal dari SystemResizer-for-GSI (post Telegram aslinya), hanya nama group di `dynamic_partitions_op_list` yang diubah untuk garnet.
