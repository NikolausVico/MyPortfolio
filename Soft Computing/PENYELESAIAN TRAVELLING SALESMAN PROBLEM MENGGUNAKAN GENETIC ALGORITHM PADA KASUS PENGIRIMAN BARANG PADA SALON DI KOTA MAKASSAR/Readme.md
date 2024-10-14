PENYELESAIAN TRAVELLING SALESMAN PROBLEM MENGGUNAKAN GENETIC ALGORITHM PADA KASUS PENGIRIMAN BARANG PADA SALON DI KOTA MAKASSAR


LATAR BELAKANG
	Indonesia merupakan negara yang memiliki banyak pulau, provinsi dan kota, dan salah satu kota terbesar di Indonesia adalah kota Makassar yang berada di Sulawesi Selatan. Dalam kota yang besar akan terdapat banyak hal-hal yang membantu manusia untuk melakukan pekerjaan sehari-hari, salah satunya adalah toko rias atau salon. Terdapat banyak sekali salon di kota Makassar, dan hal ini menimbulkan suatu permasalahan dan peluang bisnis. Butuhnya salon akan bahan baku kecantikan atau perawatan rambut, menjadi suatu potensi bisnis yang dapat dilakukan oleh para pelaku bisnis retail di dunia kecantikan/perawatan rambut tersebut. Mereka akan dengan senang hati untuk melakukan transaksi dengan salon-salon ini, namun efisiensi tetap menjadi kunci mereka dalam bertransaksi.

Traveling Salesman Problem (TSP) merupakan sebuah permasalah optimasi yang dapat diterapkan pada berbagai kegiatan seperti pendistribusian barang, pengambilan tagihan listrik dan pedagang keliling. Masalah optimasi pada TSP sangat terkenal dan telah menjadi standar untuk mencoba algoritma yang  komputasional. Pokok dari permasalahan TSP adalah bagaimana seorang salesman harus dapat mengunjungi sejumlah kota atau lokasi yang telah diketahui jarak lokasi satu dengan yang lainnya. (Erdiwansyah, 2017)

Salah satu cara untuk menyelesaikan TSP ini adalah dengan menggunakan Genetic Algorithm (GA). Genetic Algorithm (GA) adalah bagian dari Evolutionary Algorithm yaitu suatu algoritma yang mencontoh proses evolusi alami dimana konsep utamanya adalah individu-individu yang paling unggul akan bertahan hidup, sedangkan individu-individu yang lemah akan punah (Engelbrecht). Genetic Algorithm ini merupakan salah satu cara yang umum digunakan dalam penyelesaian TSP ini

Kajian Teori
	Adapun kajian teor sederhanai yang kami gunakan dalam mengerjakan problem ini adalah sebagai berikut
Traveling Salesman Problems
Traveling Salesman Problem (TSP) merupakan sebuah permasalah optimasi yang dapat diterapkan pada berbagai kegiatan seperti pendistribusian barang, pengambilan tagihan listrik dan pedagang keliling. Masalah optimasi pada TSP sangat terkenal dan telah menjadi standar untuk mencoba algoritma yang  komputasional. Pokok dari permasalahan TSP adalah bagaimana seorang salesman harus dapat mengunjungi sejumlah kota atau lokasi yang telah diketahui jarak lokasi satu dengan yang lainnya.

TSP pertama kali diperkenalkan pada tahun 1930-an oleh Karl Menger seorang ahli matematika dan ekonomi. Menger menyebutnya sebagai “Messenger Problem” yakni masalah yang dihadapi oleh pengirim surat dan banyak pengelana. TSP ini merupakan masalah yang sangat kompleks, dikarenakan jika kita memiliki banyak sekali tujuan, maka hal ini akan membuat adanya banyak sekali kemungkinan rute yang dapat ditempuh, belum lagi rute yang ditempuh harus disaring agar menghasilkan cost atau target variabel yang diinginkan. Pada kasus ini target yang diinginkan adalah Minimasi Jarak, jadi TSP yang harus diselesaikan adalah terdapat berbagai lokasi dimana kami harus mencari rute yang menghasilkan jarak terkecil

Genetic Algorithm
Genetic Algorithm (GA) adalah bagian dari Evolutionary Algorithm yaitu suatu algoritma yang mencontoh proses evolusi alami dimana konsep utamanya adalah individu-individu yang paling unggul akan bertahan hidup, sedangkan individu-individu yang lemah akan punah[1]. Keunggulan individu-individu ini diuji melalui suatu fungsi yang dikenal sebagai fitness function. Fitness dalam GA didefinisikan sebagai gambaran kelayakan suatu solusi terhadap suatu permasalahan. Fitness Function akan menghasilkan suatu nilai fitness value yang akan menjadi referensi untuk proses GA selanjutnya. (Binus, 2018)

Proses GA dimulai dengan menentukan populasi awal initial population yang terdiri dari beberapa kromosom yang disusun oleh beberapa gen yang merupakan representasi dari kandidat-kandidat solusi dari suatu masalah. Kandidat-kandidat terbaik akan dipilih melalui proses selection, berdasarkan fitness value yang telah dihitung untuk setiap kromosom dalam populasi. Kandidat – kandidat terpilih dari proses ini adalah individu-individu yang akan mengisi mating pool yaitu suatu set dimana dua parents akan dibentuk dari sini. Dalam Evolutionary Algorithm prinsip bertahan muncul karena adanya proses reproduksi. Turunan offspring yang dihasilkan akan membawa sifat gen orangtuanya (parents) , oleh sebab itu parents dipilih dari mating pool yang merupakan kumpulan kandidat-kandidat terbaik dari suatu populasi. Dengan demikian turunan yang dihasilkan adalah turunan yang memiliki sifat unggul dari kedua orang tuanya.

Overview Studi Kasus
	Pada tugas ETS kali ini, kami mengambil studi kasus sebuah perusahaan penyedia bahan baku untuk salon kecantikan. Perusahaan ini memiliki beberapa cabang warehouse di Indonesia. Agar biaya pengiriman menjadi lebih efektif dan efisien, perusahaan akan mengirim barang ke customer melalui cabang warehouse terdekatnya. Untuk kepentingan tugas ETS ini, kelompok kami mengambil cabang warehouse di Makassar. Warehouse ini memiliki beberapa customer, tetapi untuk tugas ini kami hanya menggunakan data 20 customer saja. Di sini, kami seolah-olah ditugaskan untuk membantu perusahaan menentukan bagaimana rute pengiriman barang terdekat kepada 20 customer tersebut dengan aturan bahwa dalam satu kali proses pengiriman harus mengunjungi semua customer tersebut. Data masukan yang digunakan untuk menyelesaikan permasalahan tersebut adalah data geo latitude dan geo longitude yang merepresentasikan alamat customer. Geo Latitude (garis lintang) adalah jarak suatu lokasi dari garis khatulistiwa, diukur dalam derajat utara atau selatan dari khatulistiwa.  Sedangkan, Geo Longitude (garis bujur) adalah jarak suatu lokasi dari garis nol bujur yang berada di Greenwich, Inggris, diukur dalam derajat timur atau barat dari Greenwich. Kombinasi dari geo latitude dan longitude memberikan koordinat geografis yang unik untuk setiap lokasi di bumi. Berikut ini merupakan tampilan data awal yang akan digunakan untuk tugas ini






Pembahasan Penerapan Algoritma Genetika
Mendefinisikan data input dan parameter
Pada langkah ini, kami mendefinisikan data input berupa data koordinat sejumlah dua data input yaitu data geo longitude dan geo latitude. Data input tersebut merepresentasikan alamat customer pada koordinat geografis. Kemudian, akan ditentukan parameter-parameter algoritma genetika seperti ukuran populasi, persentase crossover, persentase mutasi, dan jumlah generasi. Berikut ini parameter yang digunakan untuk menyelesaikan permasalahan ini:
Ukuran populasi 200
Probabilitas crossover 0,8
Probabilitas mutasi 0,2
Generasi 700

Memvisualisasikan Alamat Customer
Langkah berikutnya, kami mencoba untuk memvisualisasikan data dari alamat customer ke dalam scatterplot. Tujuan dari visualisasi tahap awal ini akan membantu dalam memahami letak relatif antar customer satu dengan yang lain.


Inisialisasi Populasi Awal
Selanjutnya, akan dibuat fungsi menggunakan np.random.permutation dari NumPy yang bertujuan untuk menghasilkan populasi awal. Populasi awal ini akan digunakan sebagai titik awal dalam algoritma genetika untuk menemukan solusi terbaik. Populasi awal ini dibentuk dengan cara memilih secara acak urutan customer dari semua kemungkinan permutasi alamat customer yang diberikan. Variabel “cities_names”merepresentasikan list yang berisi nama-nama customer yang akan dijadikan sebagai populasi awal. Sedangkan, variabel “n_population”  adalah jumlah individu (kemungkinan jalur) dalam populasi.

Menghitung jarak antar dua customer
Pada tahap ini, kami menghitung jarak (dalam kilometer) antara dua titik koordinat geografis (latitude dan longitude) menggunakan rumus Haversine. Rumus ini berguna untuk menghitung jarak antara dua titik pada permukaan bulat seperti bumi. Fungsi ini menerima empat parameter: lat1 dan lon1 adalah koordinat latitude dan longitude dari titik pertama, sedangkan lat2 dan lon2 adalah koordinat latitude dan longitude dari titik kedua.

Lalu, kami membuat sebuah matriks jarak antara setiap pasang customer. Matriks ini akan digunakan sebagai masukan dalam algoritma genetika untuk menyelesaikan Traveling Salesman Problem (TSP) dengan mencari rute terpendek yang melintasi setiap kota tepat sekali dan kembali ke kota awal.

Menghitung Total Jarak yang ditempuh Individu
Langkah ini digunakan untuk menghitung total jarak yang ditempuh oleh seorang individu dalam populasi. Seorang individu direpresentasikan sebagai daftar yang berisi urutan customer yang akan dikunjungi. Fungsi ini melakukan perulangan melalui daftar customer dalam individu dan mengakumulasi jarak antara setiap pasang customer yang dikunjungi, termasuk jarak dari customer terakhir kembali ke customer awal. Jumlah total jarak ini kemudian dikembalikan sebagai output dari fungsi. Total jarak ini digunakan sebagai nilai fitness dalam algoritma genetika untuk mengevaluasi seberapa baik suatu solusi dalam populasi. Solusi dengan total jarak terpendek dianggap sebagai solusi yang optimal dalam  Traveling Salesman Problem (TSP).

Menghitung Fitness Probability
	Langkah selanjutnya yaitu menghitung fitness probability dari setiap individu dalam populasi. Proses ini melibatkan perhitungan total jarak yang ditempuh oleh setiap individu dalam populasi. Fungsi ini mengubah total jarak yang ditempuh oleh individu dalam populasi menjadi sebuah probabilitas untuk menentukan individu mana yang akan dipilih sebagai parent untuk reproduksi.

Pemilihan Parent
	Setelah menghitung fitness probability tiap individu. Selanjutnya akan dilakukan proses pemilihan parent dengan mengimplementasikan strategi seleksi menggunakan fungsi ‘roulette_wheel’. Fungsi ini menentukan individu mana yang akan dipilih sebagai orangtua untuk berkembang biak berikutnya dengan cara menghitung kumulatif jumlah fitness probability untuk setiap individu, kemudian menggunakan nilai acak antara 0 dan 1 untuk menentukan posisi "roulette_wheel" yang menentukan individu yang dipilih. Hasilnya, fungsi ini memilih satu individu dari populasi sebagai output berdasarkan fitness probability mereka, dengan individu yang memiliki fitness probability lebih tinggi memiliki kemungkinan yang lebih besar untuk dipilih.

Melakukan Crossover
	Langkah berikutnya yaitu melakukan perkawinan silang (crossover) antar induk dengan menggunakan fungsi. Proses ini bertujuan untuk menghasilkan keturunan (offspring) yang menggabungkan informasi dari kedua induk. Langkah-langkahnya mencakup pemilihan titik pemotongan secara acak, pembuatan dua keturunan dengan membagi dan menggabungkan urutan customer dari kedua induk, dan mengembalikan keturunan sebagai output. Dengan menggunakan strategi ini, keturunan memiliki potensi untuk mewarisi sifat-sifat baik dari kedua induk, sehingga meningkatkan kemungkinan untuk menemukan solusi yang optimal dalam algoritma genetika.

Mutasi
	Selanjutnya yaitu terjadi proses mutasi pada satu individu keturunan (offspring). Pada proses ini dua indeks acak dipilih untuk merepresentasikan dua customer yang akan ditukar posisinya dalam urutan kunjungan customer individu. Proses mutasi dilakukan dengan menukar posisi customer pada indeks yang dipilih sehingga menghasilkan individu keturunan yang telah dimutasi. Mutasi ini bertujuan untuk memperkenalkan variasi genetik ke dalam populasi.

Implementasi Algoritma Genetika
Proses dimulai dengan inisialisasi populasi awal. Kemudian, dilakukan seleksi orangtua (parents) berdasarkan fitness probability dengan metode roulette wheel. Setelah itu, dilakukan crossover antara induk dan mutasi untuk menghasilkan keturunan (offspring). Keturunan dan orangtua digabungkan menjadi satu populasi. Lalu, seleksi dilakukan kembali untuk memilih individu dengan  fitness probability terbaik. Proses ini diulang sebanyak n_generations kali. Pada akhirnya, solusi terbaik yang ditemukan akan dihitung total jaraknya untuk evaluasi performa algoritma. Hasil akhir dari algoritma ini adalah solusi terbaik yang ditemukan mengenai urutan kunjungan customer yang memberikan total jarak tempuh terpendek.



Output Solusi Algoritma Genetika
Kami akan menggunakan 3 skenario parameter yaitu skenario Rendah, Sedang, dan Tinggi. Parameter yang kami ubah adalah n_populasi dan n_generasi, untuk mutation rate dan crossover rate tidak kami ubah karena nilai tersebut sudah merupakan best practice berdasarkan hasil penelitian. Untuk parameter n_populasi kami akan menggunakan nilai 40, 100, dan 200 sedangkan untuk parameter n_generasi kami akan menggunakan nilai 200, 450, dan 700. Kami tetap menggunakan nilai generasi lebih rendah daripada populasi karena hal itu juga sudah sesuai teori yang ada.

n_populasi
n_generasi
Cost/DIstance (KM)
40
200
28.724
40
450
25.43
40
700
27.689
100
200
23.56
100
450
23.928
100
700
23.464
200
200
22.163


200
450
22.679
200
700
21.11


Setelah menerapkan algoritma genetika, diperoleh sebuah solusi berupa jarak rute terdekat yang harus ditempuh untuk mengunjungi semua customer yaitu 21,11 km. Selain itu, didapatkan juga urutan customer yang harus dikunjungi yang menghasilkan jarak terpendek tersebut.
Berikut ini daftar urutan customer yang harus dikunjungi untuk menghasilkan rute terpendek:
Rute Terpendek Nya: WATNIS SALON → ASSYIFA SALON → YASMIN SALON → ADHEL SALON → ELHA SALON, MAMOA RAYA → BARY 2 GOWA SALON → BEN ART MANURUKI SALON → NADIA PURNAMA SALON → HERMAN SALON MAPPAODDANG → BEAUTY 8 SALON → IWAN KUMALA SALON → RIAS TOKO → ANI SALON → EGHY SALON → NONA COSMETIK → HERMAN DG.TATA SALON → BULAN SALON GOWA → MAHA SURYA TOKO → INNER V SALON → RAHRA SALON


Visualiasi Solusi
	Berikut ini merupakan proses visualisasi solusi akhir yang dihasilkan. Melalui visualisasi ini, kita dapat dengan jelas melihat rute terpendek yang telah dihasilkan oleh algoritma genetika untuk mengatasi masalah pengiriman ke customer. Berdasarkan visualisasi tersebut, customer pertama yang harus dikunjungi yaitu WATNIS SALON dan customer terakhir yaitu RAHRA SALON.



Kesimpulan
	
Tugas ini bertujuan untuk menyelesaikan permasalahan distribusi barang ke salon kecantikan di Makassar dengan menggunakan Algoritma Genetika. Algoritma Genetika dapat membantu perusahaan menghemat biaya pengirimanntarkan barang ke semua customer, sehingga dapat meminimalkan biaya pengiriman.

Algoritma Genetika meniru teori evolusi untuk menemukan solusi terbaik dalam menyelesaikan permasalahan Traveling Salesman Problem (TSP). Algoritma ini dioptimalkan untuk kasus ini dengan parameter yang sesuai. Hasilnya, Algoritma Genetika berhasil menemukan rute terpendek dengan total jarak tempuh 21,11 km. Dengan urutan customer yang harus dikunjungi diawali dari WATNIS SALON hingga terakhir adalah RAHRA SALON. Dapat disimpulkan bahwa Algoritma Genetika terbukti efektif untuk menyelesaikan masalah TSP dalam kasus distribusi barang ke salon kecantikan di Makassar



Daftar Pustaka
Engelbrecht, A. P. (2005, December 16). Fundamentals of Computational Swarm Intelligence. Wiley. http://books.google.ie/books?id=3xhrQgAACAAJ&dq=Fundamentals+of+Computational+Swarm+Intelligence&hl=&cd=1&source=gbs_api
Erdiwansyah, et. al. (2017, Agustus 4). Analisis Hibridisasi Pencarian Lokal Dengan Populasi Dalam Travelling Salesman Problem (TSP)
Genetic Algorithm. (2018, December 8). School of Computer Science. https://socs.binus.ac.id/2018/12/08/genetic-algorithm/
