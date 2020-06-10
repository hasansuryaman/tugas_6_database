# Tugas 6 Database

### 1. Buat tabel latihan_1 dengan dua kolom, a dan b dengan spesifikasi:

- Kolom a di definisikan sebagai INTEGER, memiliki atribut UNSIGNED, di set sebagai PRIMARY KEY dan penomoran otomatis AUTO_INCREMENT.
- Kolom b di definisikan sebagai VARCHAR yang sanggup menampung maksimal 10 karakter. Jika kolom ini tidak diisi, string ‘merdeka’ akan menjadi string default. Kolom b juga tidak bisa diisi nilai NULL.
- Tabel latihan_1 menggunakan storage engine MyISAM serta charset ascii. Nomor urut auto increment dimulai dari 100.
- Silahkan buat tabel latihan_1 dengan spesifikasi diatas sebelum lanjut ke nomor 2.
```mysql
CREATE TABLE latihan_1 (a INT UNSIGNED PRIMARY KEY AUTO_INCREMENT, b VARCHAR(10) DEFAULT 'merdeka' NOT NULL) AUTO_INCREMENT=100 ENGINE=MyISAM CHARACTER SET ascii;
```

### 2. Ubah storage engine tabel latihan_1 menjadi InnoDB.
```mysql
ALTER TABLE latihan_1 ENGINE=InnoDB;
```

### 3. Ubah nama kolom b menjadi c dari tabel latihan_1, dimana kolom c ini juga memiliki tipe data yang sama dengan kolom b (termasuk atribut).
```mysql
ALTER TABLE latihan_1 CHANGE b c VARCHAR(10) NOT NULL DEFAULT 'merdeka';
```

### 4. Tambah kolom baru bernama b ke dalam tabel latihan_1. Kolom b di definisikan dengan tipe data DATE. Jika kolom b tidak diisi nilai, tanggal 01-01-2018 akan menjadi nilai default. Tempatkan kolom b setelah kolom a. Artinya, setelah langkah ini dijalankan tabel latihan_1 akan memiliki 3 kolom: a, b dan c.
```mysql
ALTER TABLE latihan_1 ADD COLUMN b DATE DEFAULT '2018-01-01' AFTER a;
```

### 5. Buat tabel latihan_2 yang memiliki struktur sama persis seperti tabel latihan_1.
```mysql
CREATE TABLE latihan_2 LIKE latihan_1;
```

### 6. Ubah storage engine tabel latihan_2 menjadi MEMORY.
```mysql
ALTER TABLE latihan_2 ENGINE = MEMORY;
```

### 7. Ubah nama tabel latihan_2 menjadi latihan_3.
```mysql
ALTER TABLE latihan_2 RENAME TO latihan_3;
```

### 8. Buat temporary table dengan nama latihan_4. Tabel ini berisi 1 kolom a sebagai TIMESTAMP.
```mysql
CREATE TEMPORARY TABLE latihan_4(a TIMESTAMP);
```

### 9. Hapus tabel latihan_1, latihan_3 dan latihan_4 dalam 1 perintah query.
```mysql
DROP TABLE IF EXISTS latihan_1, latihan_3, latihan_4;
```
