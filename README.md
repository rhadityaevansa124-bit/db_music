# Dalam SQL, JOIN minimal ada 2 tabel

Karena fungsi JOIN adalah menggabungkan data dari satu tabel dengan tabel lain berdasarkan kolom yang berhubungan (biasanya primary key dan foreign key).

Kalau cuma 1 tabel, itu bukan JOIN — itu hanya SELECT biasa.

Langkah yang akan kita lakukan setelah ini adalah MEMBUAT TABLE

# Membuat Table
#> create table artis(

    -> id_artis int primary key auto_increment,
    
    -> nama_artis varchar(100) not null);

#> create table lagu (

    -> id_lagu INT AUTO_INCREMENT PRIMARY KEY,
    
    -> judul_lagu VARCHAR(150) NOT NULL,
    
    -> id_artis INT,
    
    -> FOREIGN KEY (id_artis) REFERENCES artis(id_artis)
    
    -> ON UPDATE CASCADE
    
    -> ON DELETE CASCADE);    

Setelah Table dibuat kita akan menggabungkan data menggunakan INNER JOIN <br>
Sebelumnya Kita input data terlebih dahulu ke dalam Table <br>

#> insert into artis values ('','ArielNoah'),('',''RizkyFebian'),('',''NikeArdila');

# Menggabungkan data menggunakan INNER JOIN    

Pengertian:

INNER JOIN menampilkan hanya data yang memiliki pasangan di kedua tabel.

Jika tidak ada pasangan, maka tidak ditampilkan.

![alt text](https://www.w3schools.com/sql/img_inner_join.png?raw=true)

### Contoh Syntax INNER JOIN:
SELECT column_name(s)

FROM table1

INNER JOIN table2

ON table1.column_name = table2.column_name;

### Praktek
 select artis.id_artis, lagu.judul_lagu from artis inner join lagu on artis.id_artis = lagu.id_artis; <br>

### Hasil

+----------+-----------------------+

| id_artis | judul_lagu            |

+----------+-----------------------+

|        1 | Separuh Aku           |

|        2 | Tinggallah Ku Sendiri |

|        3 | Mantra Cinta          |

+----------+-----------------------+

# Menggabungkan data menggunakan LEFT JOIN
Pengertian:

LEFT JOIN menampilkan semua data dari tabel kiri, walaupun tidak punya pasangan di tabel kanan.

![alt text](https://www.w3schools.com/sql/img_left_join.png?raw=true)

### Contoh Syntax INNER JOIN:
SELECT column_name(s)

FROM table1

LEFT JOIN table2

ON table1.column_name = table2.column_name;

### Praktek
select artis.id_artis, lagu.judul_lagu from artis left join lagu on artis.id_artis = lagu.id_artis;

### Hasil

+----------+-----------------------+

| id_artis | judul_lagu            |

+----------+-----------------------+

|        1 | Separuh Aku           |

|        2 | Tinggallah Ku Sendiri |

|        3 | Mantra Cinta          |

+----------+-----------------------+

# Menggabungkan data menggunakan RIGHT JOIN
Pengertian:

RIGHT JOIN menampilkan semua data dari tabel kanan, walaupun tidak punya pasangan di tabel kiri.

![alt text](https://www.w3schools.com/sql/img_right_join.png?raw=true)

### Contoh Syntax RIGHT JOIN:
SELECT column_name(s)

FROM table1

RIGHT JOIN table2

ON table1.column_name = table2.column_name;

### Praktek
select artis.id_artis, lagu.judul_lagu from artis right join lagu on artis.id_artis = lagu.id_artis;

### Hasil

+----------+-----------------------+

| id_artis | judul_lagu            |

+----------+-----------------------+

|        1 | Separuh Aku           |

|        2 | Tinggallah Ku Sendiri |

|        3 | Mantra Cinta          |

+----------+-----------------------+
