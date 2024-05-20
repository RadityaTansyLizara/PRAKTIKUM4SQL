# PRAKTIKUM4SQL
| Variable | Isi |
| -------- | --- |
| Nama | RADITYA TANSY LIZARA  |
| NIM | 312310454 |
| Kelas | TI.23.A5 |
| Mata Kuliah | Basis Data |

# Soal Latihan Praktikum ( Pegawai )
GAMBAR SOAL
**Perintah SQL :**

```
CREATE TABLE pegawai (
    idpegawai VARCHAR(5) PRIMARY KEY,
    nama_depan VARCHAR(10) NOT NULL,
    nama_belakang VARCHAR(15) NOT NULL,
    email VARCHAR(25) UNIQUE KEY,
    telepon VARCHAR(15),
    tgl_kontrak DATA,
    id_job VARCHAR(5),
    gaji INT,
    tunjangan INT
    );

INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);
```

***Output :***

![OUTPUT SOAL TABLE 1](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/1cf0c0cd-9aba-447c-995f-afd55ee544d1)


## Tugas Praktikum

**1. Tampilkan pegawai yang gajinya bukan 2.000.000 dan 1.250.000 !**

```
SELECT*FROM pegawai WHERE gaji NOT IN (2000000, 1250000);
```

***Output :***

![GAJI PEGAWAI BUKAN 2JT](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/2ebcc6af-f0bd-44ad-8e8e-6ffa16ac7340)


**2. Tampilkan pegawai yang tunjangannya NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NULL;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/5719c1a7-148a-490a-993f-971726458b57)


**3. Tampilkan pegawai yang tunjangannya tidak NULL!**

```
SELECT*FROM pegawai WHERE tunjangan IS NOT NULL;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/6e1fe8a8-e5b1-420b-bd49-f55788d1b31f)


**4. Tampilkan/hitung jumlah baris/record tabel pegawai!**

```
SELECT COUNT(*) AS jumlah_pegawai FROM pegawai;
```

***Output :***

 ![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/3ca3582b-069a-4302-aa40-42f8d6e3c82f)


 **5. Tampilkan/hitung jumlah total gaji di tabel pegawai!**

```
SELECT SUM(gaji) AS ttl_gaji FROM pegawai;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/19001bed-d4bf-4985-86d4-dfd40885af57)


**6. Tampilkan/hitung rata-rata gaji pegawai!**

```
SELECT AVG(gaji) AS mean_gaji FROM pegawai;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/13554aff-7199-424f-b1a6-1abeb98b5450)


**7. Tampilkan gaji terkecil!**

```
SELECT MIN(gaji) AS terkecil FROM pegawai;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/1ddb1764-90f3-42fb-99b3-229256b09ae5)


**8. Tampilkan gaji terbesar!**

```
SELECT MAX(gaji) AS terbesar FROM pegawai;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/a19a2c11-7ae9-4490-972c-48d659bbf006)



# Soal Latihan Praktikum ( Hewan )

GAMBAR SOAL

**Perintah SQL :**

```
CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );

INSERT INTO hewan VALUES
    ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
    ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
    ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
    ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
    ('p5', 'Fang', 'Benny', 'Dog', 'M'),
    ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
    ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
    ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
    ('p9', 'Slim', 'Benny', 'Snake', 'M');
```

***Output :***

GAMBAR

## Tugas Praktikum

**1. Tampilkan jumlah hewan yang dimiliki setiap owner.**

```
SELECT owner, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY owner;
```

***Output :***

GAMBAR

**2. Tampilkan jumlah hewan berdasarkan spesies**

```
SELECT species, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY species;
```

***Output :***

GAMBAR

**3. Tampilkan jumlah hewan berdasarkan jenis kelamin**

```
SELECT sex, COUNT(*) AS jmlh_hewan FROM hewan GROUP BY sex;
```

***Output :***

GAMBAR

**4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```

***Output :***

GAMBAR

**5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE
species IN ('Cat', 'Dog')
GROUP BY species, sex;
```

***Output :***

GAMBAR

**6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

***Output :***

GAMBAR

## Tulis semua perintah-perintah SQL percobaan di atas beserta outputnya!

```
CREATE DATABASE praktikum4;
USE praktikum4;
CREATE TABLE pegawai (
    idpegawai VARCHAR (5) PRIMARY KEY,
    nama_depan VARCHAR (10) NOT NULL,
    nama_belakang VARCHAR (15) NOT NULL,
    email VARCHAR (25) UNIQUE KEY,
    telepon VARCHAR (15),
    tgl_kontrak DATE,
    id_job VARCHAR (5),
    gaji INT,
    tunjangan INT
    );

INSERT INTO pegawai VALUES
    ('E001', 'Ferry', 'Gustiawan', 'ferry@yahoo.com', '07117059004', '2005-09-01', 'L0001', 2000000, 500000),
	('E002', 'Aris', 'Ganiardi', 'aris@yahoo.com', '081312345678', '2006-09-01', 'L0002', 2000000, 200000),
	('E003', 'Faiz', 'Ahnad', 'faiz@gmail.com', '081367384322', '2006-10-01', 'L0003', 1500000, NULL),
	('E004', 'Emna', 'Bunton', 'emna@gmail.com', '081363484342', '2006-10-01', 'L0004', 1500000, 9),
	('E005', 'Mike', 'Scoff', 'mike@plasa.com', '08163454555', '2007-09-01', 'L0005', 1250000, 9),
	('E006', 'Lincoln', 'Burrows', 'linc@yahoo.com', '08527388432', '2008-09-01', 'L0006', 1750000, NULL);

SELECT * FROM pegawai;

SELECT * FROM pegawai WHERE gaji NOT IN (2000000, 1250000);

SELECT * FROM pegawai WHERE tunjangan IS NULL;

SELECT * FROM pegawai WHERE tunjangan IS NOT NULL;

SELECT COUNT(*) AS jumlah_pegawai FROM pegawai;

SELECT SUM(gaji) AS total_gaji FROM pegawai;

SELECT AVG(gaji) AS rata_rata_gaji FROM pegawai;

SELECT MIN(gaji) AS gaji_terkecil FROM pegawai;

SELECT MAX(gaji) AS gaji_terbesar FROM pegawai;

CREATE TABLE hewan (
    id VARCHAR (5) PRIMARY KEY,
    name VARCHAR (10) NOT NULL,
    owner VARCHAR (10),
    species VARCHAR (10),
    sex enum('M', 'F')
    );

INSERT INTO hewan (id, name, owner, species, sex)
VALUES ('p1', 'Puffball', 'Diane', 'Hamster', 'F'),
       ('p2', 'Claws', 'Gwen', 'Cat', 'M'),
       ('p3', 'Fluffy', 'Haro 1d', 'Cat', 'F'),
       ('p4', 'Buffy', 'Haro 1d', 'Dog', 'F'),
       ('p5', 'Fang', 'Benny', 'Dog', 'M'),
       ('p6', 'Bowser', 'Diane', 'Dog', 'M'),
       ('p7', 'Chirpy', 'Gwen', 'Bird', 'F'),
       ('p8', 'Whistler', 'Gwen', 'Bird', NULL),
       ('p9', 'Slim', 'Benny', 'Snake', 'M');

SELECT * from hewan;

SELECT owner, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY owner;

SELECT species, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species;

SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY sex;

SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;

SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE species IN ('Cat', 'Dog') GROUP BY species, sex;

SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

## Berikan Kesimpulan Anda !

Terdapat beberapa ***Query Filter*** yang ditemukan pada tugas praktikum 4 :

- Operator `IN` digunakan untuk memfilter data yang terdapat pada list IN
- Operator `NOT IN` digunakan untuk memfilter data yang tidak terdapat pada list IN
- Operator `IS NULL` digunakan untuk menampilkan data dengan nilai data NULL
- Operator `IS NOT NULL` digunakan untuk menampilkan data dengan nilai data tidak NULL
- `COUNT` adalah perintah yang digunakan untuk menghitung jumlah baris suatu kolom pada tabel.
- `SUM` adalah perintah yang digunakan untuk menghitung jumlah nilai suatu kolom pada tabel.
- `AVG` adalah perintah yang digunakan untuk menghitung rata-rata dari nilai suatu kolom pada tabel.
- `MIN` adalah perintah yang digunakan untuk menampilkan nilai terkecil dari suatu kolom pada tabel.
- `MAX` adalah perintah yang digunakan untuk menampilkan nilai terbesar dari suatu kolom pada tabel.
- Klausa `GROUP BY` berfungsi untuk mengelompokkan data berdasarkan field tertentu.

## FINISH 
