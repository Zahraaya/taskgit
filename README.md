# taskgit

## Task 1

Kelas MarketingDataETL adalah bagian dari proses Extract, Transform, Load (ETL) yang digunakan untuk memproses data pemasaran.

Konstruktor **init** dari kelas ini inisialisasi atribut data dengan nilai None.

Metode extract(file_path) digunakan untuk membaca data dari file CSV yang diberikan melalui file_path. Data yang dibaca kemudian disimpan dalam atribut data dan dikembalikan.

Metode transform() digunakan untuk membersihkan data. Kolom 'purchase_date' dikonversi menjadi format datetime menggunakan pd.to_datetime(). Baris yang memiliki nilai kosong dalam kolom 'purchase_date' dibuang menggunakan dropna(), dan indeks data di-reset menggunakan reset_index(drop=True). Data yang telah dibersihkan kemudian disimpan kembali dalam atribut data.

Metode store(transformed_data, store_path) digunakan untuk menyimpan data yang telah ditransformasi ke dalam file CSV yang diberikan melalui store_path. Data disimpan tanpa menyertakan indeks.

## Task 2

Kode ini mendefinisikan dua kelas, yaitu MarketingDataETL dan TargetedMarketingETL, yang digunakan untuk melakukan proses ekstraksi, transformasi, dan penyimpanan data pemasaran.

Kelas MarketingDataETL memiliki metode extract() yang digunakan untuk membaca data dari file CSV dan menampilkan data sebelum transformasi. Metode transform() digunakan untuk membersihkan data dengan menghapus baris yang memiliki nilai kosong dalam kolom 'purchase_date' dan mengonversi kolom 'purchase_date' ke dalam format datetime jika memungkinkan.

Kelas TargetedMarketingETL merupakan turunan dari MarketingDataETL. Kelas ini menambahkan metode segment_customers() yang digunakan untuk mengelompokkan pelanggan berdasarkan jumlah yang dihabiskan. Metode transform() di-overide untuk memanggil metode transform() dari kelas induk dan kemudian memanggil metode segment_customers().

Setelah melakukan ekstraksi dan transformasi, data yang telah di-segmentasi disimpan dalam format Excel menggunakan metode store_segmented_data().

Instansiasi objek dari TargetedMarketingETL dilakukan dengan mengekstrak data, melakukan transformasi, dan menyimpan data yang telah di-segmentasi ke dalam file Excel dengan nama "segmented_data_etl.xlsx".
