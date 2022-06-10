# Explorasi dan Visualisasi Data COVID-19 di Jawa Timur menggunakan Pandas dan Matplotlib

# BACKGROUND
Saat ini, dunia sedang menghadapi krisis kesehatan secara global dan berdampak terhadap sosial ekonomi dikarenakan COVID-19 yang belum pernah terjadi sebelumnya. Di Indonesia kondisi tersebut semakin mengkhawatirkan dikarenakan telah terjadi lonjakan kasus yang kedua pada bulan Februari 2022. Pihak pemerintah Indonesia sendiri telah mengokonfirmasi sejak adanya kasus COVID-19 yang pertama kali terjadi, sehingga UNICEF telah memimpin berbagai upaya dalam merespon pandemi ini bersama dengan pemerintah WHO dan mitra lainnya. Sehingga upaya yang bisa dilakukan saat ini oleh pemerintah yaitu pembatasan sosial dan penutupan sekolah berdampak pada pendidikan, kesehatan mental, dan akses kepada pelayanan kesehatan dasar. Jawa Timur masih menjadi peringkat ke 4, provinsi yang penyumbang kasus covid di Indonesia dengan persentase sebanyak 9.6%. Maka dari itu dalam artikel ini ingin menggali lebih dalam bagaimana keadaan Covid di Jawa Timur dengan menggunakan data terbaru. Pemerintah juga melakukan pengumpulan data dan menyediakan data pertumbuhan kasus COVID19 kepada publik. Sebagai salah satu contoh adalah portal covid19.go.id yang telah dilengkapi dengan dasbor dan grafik visualisasi agar masyrakat lebih mudah dalam memahami informasi. Serta banyak portal data COVID-19 lainnya yang disediakan oleh masing-masing pemerintah daerah.

# Data Collection
Rekapitulasi data COVID-19 Indonesia tersedia di API publik yang beralamat di https://data.covid19.go.id/public/api/update.json. Untuk mengakses API adalah dengan menggunakan fungsi get dari library requests. Data yang akan digunakan diambil merupakan data real-time langsung dari API (Application Programming Interface) yang telah disediakan pemerintah pada alamat covid19.go.id.

# Data Preparation
Hasil dari metadata tersebut tidak dapat langsung diproses, perlu dilakukan parsing data json ke dalam python untuk convert json format ke dictionary dengan key dan value-nya akan mengikuti format metadata sebelumnya.

# Data Visualisasi
Kasus Harian Sembuh COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/sembuh.png)

Kasus Harian Positif COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/positif.png)

Kasus Harian Meninggal COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/meninggal.png)

# Bagaimana perkembangan kasus Covid-19 dalam rentang waktu pekanan
Kasus Pekanan Positif COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/tiap%20pekan.png)

# Akumulasi kasus COVID-19
Tren Kasus COVID-19 di Jawa Timur
![alt text](https://github.com/ayodhyaGA/COVID19-JATIM/blob/master/akumulasi.png)
