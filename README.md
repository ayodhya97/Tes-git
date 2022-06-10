# Explorasi dan Visualisasi Data COVID-19 di Jawa Timur menggunakan Pandas dan Matplotlib

# BACKGROUND
Saat ini, dunia sedang menghadapi krisis kesehatan secara global dan berdampak terhadap sosial ekonomi dikarenakan COVID-19 yang belum pernah terjadi sebelumnya. Di Indonesia kondisi tersebut semakin mengkhawatirkan dikarenakan telah terjadi lonjakan kasus yang kedua pada bulan Februari 2022. Pihak pemerintah Indonesia sendiri telah mengokonfirmasi sejak adanya kasus COVID-19 yang pertama kali terjadi, sehingga UNICEF telah memimpin berbagai upaya dalam merespon pandemi ini bersama dengan pemerintah WHO dan mitra lainnya. Upaya yang bisa dilakukan saat ini oleh pemerintah yaitu pembatasan sosial dan penutupan sekolah berdampak pada pendidikan, kesehatan mental, dan akses kepada pelayanan kesehatan dasar. Jawa Timur masih menjadi peringkat ke 4, provinsi yang penyumbang kasus covid di Indonesia dengan persentase sebanyak 9.6%. Maka dari itu dalam artikel ini ingin menggali lebih dalam bagaimana keadaan Covid di Jawa Timur dengan menggunakan data terbaru. Pemerintah juga melakukan pengumpulan data dan menyediakan data pertumbuhan kasus COVID-19 kepada publik. Sebagai salah satu contoh adalah portal covid19.go.id yang telah dilengkapi dengan dasbor dan grafik visualisasi agar masyrakat lebih mudah dalam memahami informasi. Serta banyak portal data COVID-19 lainnya yang disediakan oleh masing-masing pemerintah daerah.

# Data Collection
Rekapitulasi data COVID-19 Indonesia tersedia di API publik yang beralamat di https://data.covid19.go.id/public/api/update.json. Untuk mengakses API dengan menggunakan fungsi get dari library requests. Data yang akan digunakan merupakan data real-time langsung dari API (Application Programming Interface) yang telah disediakan pemerintah pada alamat covid19.go.id.
Status kode yang muncul dari permintaan untuk mengakses API adalah <Response [200]> yang artinya permintaan sukses untuk dipenuhi sehingga dapat dilanjukan untuk pemrosesan data. Berikut ini adalah headers dari resp, dapat dilihat bahwa hasil dari metadata yang tersimpan, rekapitulasi data COVID-10 terakhir diupdate pada tanggal 21 Maret 2022.

# Data Preparation
Hasil dari metadata tersebut tidak dapat langsung diproses, perlu dilakukan parsing data json ke dalam python untuk convert json format ke dictionary dengan key dan value-nya akan mengikuti format metadata sebelumnya.Setelah menjalankan method key() untuk melihat isi elemen yang ada pada raw data, dapat dilihat ringkasan yang meliputi jumlah total kasus COVID-19, persentase kematian dan tingkat kesembuhan.
Selanjutnya dilakukan parsing data json ke dalam python format yang terbentuk masih dalam tipe dictionary dengan memanfaatkan pandas.DataFrame() data akan diubah ke bentuk data tabular sehingga lebih mudah untuk menganalisis lebih lanjut. Pada tahap mengolah data perlu diketahui mengenai kolom apa saja yang tersedia dan memilih kolom mana saja yang akan dieksplorasi lebih dalam maupun untuk memilih kolom yang tidak digunakan. Dari dataframe cov_jatim_list terdapat beberapa hal yang harus diperbaiki yaitu format pada kolom tanggal sulit untuk dibaca dan tidak konsisten. Selain itu kolom yang akan diambil untuk visualisasi adalah kolom KASUS, MENINGGAL dan SEMBUH.

# Data Visualisasi
Kasus Harian Sembuh COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/sembuh.png)

Kasus Harian Positif COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/positif.png)

Kasus Harian Meninggal COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/meninggal.png)

Interpretasi:
- Terjadi dua kali lonjakan jumlah kasus pada harian sembuh dan harian positif, dengan durasi waktu yang hampir sama yaitu berturut-turut terjadi pada bulan Juli-Agustus 2021 untuk lonjakan kasus pertama dan Februari-Maret 2022 untuk lonjakan kasus kedua.
- Sedangkan pada kasus harian meninggal lonjakan yang signifikan hanya terlihat satu kali yaitu pada bulan Juli-Agusutus 2021.
- Penanganan pemerintah dalam menurunkan tingkat mortalitas sudah lebih sigap salah satu upaya tersebut adalah Penguatan Sistem Kesehatan dalam Pengendalian COVID-19, sehingga dapat menurukan tingkat kematian pada lonjakan kasus kedua.

# Bagaimana perkembangan kasus Covid-19 dalam rentang waktu pekanan
Untuk melihat perkembangan kasus tiap pekannya, yang akan dilakukan adalah membuat dataframe baru agar lebih mudah dalam membuat visualisasi data covid-19 tiap pekan. Dikarenakan kolom yang tersedia terbatas maka dari itu perlu beberapa tahapan yang perlukan untuk mengolah data.
1. Menjadikan frekuensi total kasus secara pekanan.
2. Membuat kolom baru berupa tahunnya saja.
3. Membuat kolom berupa urutan pekan pertahunnya.
4. Menambahkan 2 kolom untuk membandingkan per pekan dengan pekan kedepannya apakah total kasus semakin baik atau buruk.

Kasus Pekanan Positif COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/tiap%20pekan.png)

# Akumulasi kasus COVID-19
Setelah membuat bar plot untuk mengetahui bagaimana jumlah kasus aktif, sembuh dan meninggal setiap bulannya dan juga bar plot untuk membandingkan tiap pekan, kali ini perlu melihat bagaimana tren dari kasus COVID-19 berdasarkan akumulasi kasus aktif, sembuh dan meninggal. Untuk melihat tren dari waktu ke waktu dapat memanfaatkan line chart sebagai visualisasi datanya.

Tren Kasus COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/akumulasi.png)

Kesimpulan:
- Grafik Tren Kasus COVID-19 di Jawa Timur menggambarkan lebih tinggi akumulasi pada kasus sembuh dan dengan seiring waktu semakin meningkat.
- Akumulasi untuk kasus meninggal tidak terdapat pelonjakan yang signifikan dengan rentang masih di bawah 50000 kasus, namum masih terdapat sedikit peningkatan mulai dari bulan Juli 2021.
- Hampir sama seperti akumulasi meninggal, untuk akumulasi positif sedikit terjadi pelonjakan yang terjadi sekitar bulan Juli-Agustus 2021 dan kembali terjadi di bulan Februasi 2022.

Referensi:
https://www.unicef.org/indonesia/id/coronavirus
https://covid19.go.id/peta-sebaran
http://p2p.kemkes.go.id/penguatan-sistem-kesehatan-dalam-pengendalian-covid-19/
