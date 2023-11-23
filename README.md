# Capstone_Module3_CaliforniaHousePricing_Regression
Prediksi harga rumah pada dataset California House Pricing
## **A. Bussiness Problem Understanding**

### **1. Context**

Sebuah hunian merupakan kebutuhan paling primer setiap individu manusia, oleh karena itu tempat tinggal menjadi hal paling mendasar dalam kehidupan manusia. Tempat tinggal saat ini memiliki berbagai pilihan mulai dari pilihan harga, luas bangunan, wilayah, dll. Banyak orang awam merasa sulit untuk mengetahui harga rumah sesuai yang paling sesuai. Begitu juga di Negara Amerika Serikat khususnya daerah California, yang terletak dibagian Barat Amerika. Hal ini pun menjadi tantangan sekaligus kesempatan bagi para developer rumah untuk dapat membangun suatu hunian dengan harga yang kompetitif dan memiliki fasilitas yang sesuai dengan kebutuhan untuk para calon orang yang akan menghuni rumah tersebut.

### **2. Problem Statement**

Setiap developer memiliki tantangan bagaimana menentukan harga rumah yang tepat, namun dengan tetap memperhatikan fasilitas yang diberikan, dan juga aspek pendukung lainnya. Dalam pasar properti yang kompetitif, agen perlu memberikan nilai tambah yang signifikan kepada klien mereka untuk memenangkan kepercayaan dan mendapatkan bisnis. Salah satu tantangan utama adalah menentukan harga yang akurat dan kompetitif untuk properti yang akan dijual. Faktor-faktor seperti kondisi pasar, lokasi, dan fitur properti dapat mempengaruhi harga, dan membuat penentuan harga yang salah dapat mengakibatkan keuntungan yang kurang optimal atau kesulitan dalam menjual properti. Para developer akan salah langkah jika membangun suatu hunian mewah, namun di daerah yang memiliki penghasilan yang rendah atau pun hunian yang biasa-biasa saja (notebene kecil) di kawasan orang yang berpenghasilan tinggi. Developer mempunyai tantangan bagaimana cara agar keuntungan finansial yang mereka dapat bisa secara maksimal.

### **3. Goals**

Tujuan dari pemodelan machine learning ini adalah:

1. Penentuan harga jual rumah, pada dataset berdasarkan berbagai aspek seperti : lokasi, umur bangunan, jumlah ruangan, jumlah kamar tidur, populasi, pendapatan, dan seberapa jauh dengan pantai.
2. Menentukan aspek paling penting dalam perhitungan harga rumah itu sendiri, seberapa besar korelasinya dengan harga rumah
3. Output bisa digunakan sebagai Pricing strategy kedepannya, untuk meminimalisir overpricing atau underpricing saat penentuan harga suatu rumah.

### **4. Analytic Approach**

Pada tahap ini, akan dilakukan analisis untuk bisa menemukan pola dari fitur yang ada pada dataset. Bisa dilihat dengan cara membangun suatu model machine learning yang berfungsi untuk memprediksi harga jual rumah, yang nantinya akan berguna bagi pihak developer dalam penentuan harga rumah di suatu kawasan. Dengan membangun suatu model machine learning regresi, diharapkan bisa membantu dalam proses penentuan harga berdasarkan fitur yang tersedia pada dataset.

### **6. Evaluation Metric**

Untuk model machine learning regresi, terdapat berbagai metriks evaluasi yang dapat digunakan:
1. RMSE: Nilai rata-rata dari selisih kuadrat antara nilai prediksi dan nilai aktual (error), kemudian diakarkan.
2. MAE: Nilai rata-rata dari absolut selisih antara nilai prediksi dan nilai aktual (error)
3. MAPE: Nilai rata-rata persentase dari dari selisih kuadrat antara nilai prediksi dan nilai aktual (error)

### **7. Model Limitation**

- median_house_value, nilai rumah dengan rentang $14999 - $432400
- median_income, pendapatan perkapita dengan rentang $0.499 - $15.0001
- population. populasi penduduk dengan rentang 3 - 35682 orang
- households, jumlah orang yang tinggal dalam 1 rumah dengan rentang 1 - 6082 orang
- house_median_age, usia rumah dengan rentang 1 - 52 tahun

### **Conclusion**

Berdasarkan hasil permodelan terbaik yaitu **`XGBoost`** maka didapat :

- Dari total 7 model yang dibuat, permodelan XGBoost adalah permodelan terbaik, dibuktikan dari nilai erornya yang paling kecil. Lalu setelah dilakukan tuning pada model tersebut, didapat hasil lebih baik.
- Fitur `ocean_proximity` dan `median_income` adalah fitur yang korelasinya paling tinggi dalam permodelan ini untuk memprediksi `median_house_value`.
- Limitasi pada permodelan ini yaitu hanya bisa memprediksi model dengan `median_house_value` pada rentang $14999 sampai dengan $432400 saja.

### **Recommendation**

Untuk Model Machine Learning :

- Agar permodelan machine learning lebih optimal, bisa dilakukan optimasi menggunakan GridSearch, karena teknik ini secara sistematis mencoba semua kombinasi hyperparameter yang memungkinkan dari suatu model untuk menemukan kombinasi yang memberikan performa terbaik. Namun kekurangan menggunakan GridSearch ini adalah karena memakan waktu yang cukup lama, karena mencoba semua kombinasi.
- Sebaiknya dilakukan juga evaluasi lebih lanjut, bisa dengan menerapkan `iterative feature selection` pada model. Tujuan dari iterative feature selection adalah untuk memilih subset fitur yang paling relevan atau memberikan kinerja terbaik untuk suatu model.

Untuk Developer Perumahan (Secara Bisnis) :

- Agar bisa memaksimalkan keuntungan, pihak developer perlu memperhatikan pendapatan perkapita penduduk sekitar. Pada dataset bisa dilihat melalui fitur `median_income`, supaya bisa lebih tepat dalam menempatkan calon pelanggan yang disasar.

Untuk Dataset :

- Dataset ini adalah data tahun 1990, maka dari itu bisa jadi datanya sudah kurang relevan untuk tahun 2023 ini. Perlu dilakukan update harga rumah terbaru, mengingat adanya inflasi yang fluktuatif setiap waktunya.
- Sebaiknya juga perlu dicari fitur pendukung yang dirasa kuat berpengaruh dalam memprediksi harga rumah. Misalnya fitur `luas_tanah`, `luas_bangunan`, dan `jarak_ke_fasilitas_umum` (rumah sakit, stasiun, halte bis, bandara, sekolah, dll).
