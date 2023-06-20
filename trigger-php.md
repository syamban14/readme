# Membuat Trigger di PHP Script

## Pengertian Trigger

Trigger adalah nama suatu object database yang berkaitan dengan tabel, dimana trigger akan langsung aktif / jalan secara otomatis ketika suatu event terjadi pada tabel.
Beberapa kegunaan trigger adalah :

- Untuk memeriksa value yang akan di `INSERT` kedalam tabel.
- Untuk melakukan perhitungan terhadap value yang ada pada saat `UPDATE`

Trigger dibuat untuk langsung aktif pada saat perintah `INSERT`, `DELETE` atau `UPDATE` dieksekusi untuk tabel yang berkaitan dengan trigger.
Trigger dapat dibuat aktif baik sebelum atau sesudah perintah penyebab trigger dieksekusi.
Contoh trigger dapat dibuat untuk dijalankan saat sebelum suatu baris record di `INSERT` atau di `UPDATE` kedalan tabel.

link : <https://en.wikipedia.org/wiki/Database_trigger>

Contoh trigger :

```php
CREATE TRIGGER `test`.`test` BEFORE INSERT ON `test`.`table` FOR EACH ROW BEGIN SET NEW.field=CONCAT("string:",NEW.field); END
```

- trigger bernama : `test`
- trigger dibuat didalam database : `test`
- trigger melekat pada tabel : `table`
- trigger otomatis jalan pada saat ada perintah `INSERT` dilakukan terhadap tabel `table`
- proses yang ada di dalam trigger dijalankan `SEBELUM` proses `INSERT` dilakukan
- perintah trigger yang berjalan adalah pada setiap record yang di `INSERT`, tiap field `FIELD` diubah menjadi `"string:"` + `FIELD`
- jadi tiap kali ada perintah : `INSERT INTO table (field) VALUES ("abc");`

yang masuk ke tabel jadi field `string:abc` bukan `fiel abc`

Sumber : <https://diskusiweb.com/discussion/44049/membuat-triger-lewat-script-php>
