# PRAKTIKUM4SQL
| Variable | Isi |
| -------- | --- |
| Nama | RADITYA TANSY LIZARA  |
| NIM | 312310454 |
| Kelas | TI.23.A5 |
| Mata Kuliah | Basis Data |

# Soal ( Pegawai )

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/681431a6-a340-4421-bff3-df8c2c66f653)

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
SELECT SUM(gaji) AS total_gaji FROM pegawai;
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



# Soal ( Hewan )

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/6c34fded-937a-429c-bd48-ed26f7e1152e)


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

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/06021723-0aa4-4ab3-860d-98f97df61196)


## Tugas Praktikum

**1. Tampilkan jumlah hewan yang dimiliki setiap owner.**

```
SELECT owner, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY owner;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/718def00-f534-40bf-83a8-817d7f13e8f4)


**2. Tampilkan jumlah hewan berdasarkan spesies**

```
SELECT species, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/a8ff6ebb-d157-4afd-82ef-d9e9f8893e2d)


**3. Tampilkan jumlah hewan berdasarkan jenis kelamin**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY sex;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/1f3af21f-40ac-4312-94ac-07f08105a3d4)


**4. Tampilkan jumlah hewan berdasarkan spesies dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan GROUP BY species, sex;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/69c1136e-b406-4d78-b7df-9a1665ddd24d)


**5. Tampilkan jumlah hewan berdasarkan spesis (cat dan dog saja) dan jenis kelamin**

```
SELECT species, sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE
species IN ('Cat', 'Dog')
GROUP BY species, sex;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/056f1060-f4bc-4051-83de-464027273891)


**6. Tampilkan jumlah hewan berdasarkan jenis kelamin yang diketahui saja**

```
SELECT sex, COUNT(*) AS jumlah_hewan FROM hewan WHERE sex IS NOT NULL GROUP BY sex;
```

***Output :***

![image](https://github.com/RadityaTansyLizara/PRAKTIKUM4SQL/assets/147571863/85e164ea-47ca-4d79-8842-5b218692b809)


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

Query Filter digunakan untuk membatasi hasil pencarian dengan menggunakan operator relasi seperti Sama Dengan, Lebih Besar, Kurang Dari, Lebih Besar Sama Dengan, Kurang atau Sama Dengan, dan Tidak Sama Dengan. Operator BETWEEN digunakan untuk mencari data dalam jangkauan tertentu. Alias digunakan untuk memberi nama lain pada field atau tabel. Operator DISTINCT digunakan untuk menghilangkan duplikasi. Operator LIKE digunakan untuk mencari data dengan menggunakan wildcard (_ atau %). Operator IN digunakan untuk memfilter data berdasarkan daftar yang ditentukan. Operator IS NULL digunakan untuk menampilkan data dengan nilai NULL

Pengurutan Data dilakukan menggunakan perintah ORDER BY dengan model ascending dan descending. Fungsi Aggregat seperti COUNT, SUM, AVG, MIN, dan MAX digunakan untuk menghitung jumlah, jumlah nilai, rata-rata, nilai terkecil, dan nilai terbesar dari suatu kolom. Clauses GROUP BY digunakan untuk mengelompokkan data berdasarkan field tertentu. Group CONCAT digunakan untuk menggabungkan string dalam field yang dikelompokkan. Klausa HAVING digunakan untuk memfilter hasil query

## SELESAI 
