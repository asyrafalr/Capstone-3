# Capstone-3

Asuransi perjalanan adalah salah satu jenis asuransi yang memberikan perlindungan selama kita melakukan perjalanan baik dalam maupun luar negeri.
Beberapa orang mungkin masih asing dengan asuransi perjalanan, tapi pada saat ini beberapa negara di dunia bahkan sudah mewajibkan para turis atau para pendatang untuk memiliki asuransi perjalanan, contohnya seperti negara-negara di Eropa dan Amerika. Asuransi perjalanan pada umumnya memiliki harga yang sangat murah atau mungkin hanya sepersekian apabila dibandingkan dengan total harga perjalanan dan benefit yang bisa didapatkan.Ada perusahaan asuransi yang menawarkan premi mulai dari Rp15.000, yang berbeda yang disesuaikan denga pertanggungan yang diinginkan, lama perjalanan dan tujuan perjalanan.

Kemudian apa saja yang manfaat yang didapatkan dengan penggunaan asuransi perjalanan ? Pada dasarnya asuransi perjalanan menawarkan manfaat berupa pertanggungan biaya medis wisatawan selama perjalanan, kemudian juga perlindungan, seperti perlindungan akan keterlambatan penerbangan, kehilangan bagasi, penundaan jadwal perjalanan hingga pembatalan penerbangan, sampai perlindungan terhadap rumah apabila bepergian meninggalkan rumah dalam jangka waktu yang cukup lama. [(Sumber: OJK)](https://sikapiuangmu.ojk.go.id/FrontEnd/CMS/Article/20551)

 Dalam kasus ini, perusahaan yang bergerak di bidang asuransi perjalanan ingin mengetahui pemegang surat perjanjian asuransi atau pemegang polis-nya akan mengajukan klaim asuransi untuk mendapatkan coverage atau tidak. Data dalam dataset ini merupakan data historis yang terdiri dari tujuan, produk asuransi, dan lain-lain di miliki oleh perusahaan asuransi perjalanan berdasarkan pemegang polisnya.

### Problem Statement
 Dalam industri asuransi perjalanan, pengajuan klaim yang tidak terduga dapat memberikan dampak signifikan terhadap aliran kas dan pengelolaan risiko perusahaan. Untuk mengatasi hal ini, perusahaan asuransi ingin mengembangkan sebuah model prediktif yang dapat secara akurat menentukan probabilitas pengajuan klaim berdasarkan berbagai faktor seperti produk asuransi, destinasi, durasi perjalanan, dan profil demografis pemegang polis. Model ini diharapkan dapat membantu perusahaan dalam membuat keputusan yang lebih tepat dalam menentukan apakah seseorang akan melakukan klaim atau tidak pada asuransi perjalanannya

### Goals
- Mengidentifikasi fitur-fitur yang paling berpengaruh terhadap kemungkinan klaim.
- Mengembangkan model prediktif yang dapat dengan akurat memprediksi kemungkinan klaim berdasarkan data yang tersedia.
- Memberikan rekomendasi untuk modifikasi produk atau strategi penargetan untuk meminimalkan risiko klaim dan meningkatkan kepuasan pelanggan.

### Analytic Approach
Pendekeatan analisis yang akan dilakukan dalam penelitian ini yaitu untuk menemukan suatu pola yang dapat membedakan pemegang polis yang akan melakukan klaim asuransi dan yang tidak, kemudian setelah didapatkan polanya, kita akan membangun model klasifikasi yang akan membantu perusahaan pemegang asuransi untuk dapat memprediksi kemungkinan pemegang polis akan melakukan klaim asuransi atau tidak

###  Conclusion
- Logistic Regression adalah model terbaik untuk dataset ini karena memiliki recall tertinggi untuk kelas klaim (0.70) dan macro average recall tertinggi (0.75). Meskipun akurasi keseluruhan lebih rendah, kemampuannya untuk mendeteksi klaim yang benar lebih baik daripada model lainnya, yang sangat penting dalam konteks asuransi.

- Model Logistic Regression ini menunjukkan performa yang cukup stabil dan baik pada dataset yang besar. Penurunan skor pelatihan yang stabil dan skor validasi yang konstan menunjukkan bahwa model ini mampu menangani peningkatan kompleksitas tanpa mengalami overfitting yang signifikan pada Learning Curve.

- Hasil ROC AUC

   - **Train score sebelum tuning**: 75.66%
   - **Test score sebelum tuning**: 74.70%
   - **Train score setelah tuning**: 75.91%
   - **Test score setelah tuning**: 75.28%

   Peningkatan skor setelah tuning menunjukkan bahwa model menjadi lebih baik dalam membedakan antara klaim dan tidak klaim.

   Parameter terbaik yang ditemukan melalui tuning adalah:
   - "model__C": 0.01,
   - "model__solver": "sag"

   Setelah tuning, model menunjukkan peningkatan dalam recall, precision, dan accuracy. Ini menunjukkan bahwa tuning membantu model menjadi lebih baik dalam mengidentifikasi klaim yang benar sambil mengurangi kesalahan dalam prediksi klaim.

- Berdasarkan feature importance didapati bahwa seseorang akan klaim atau tidak klaim dapat dipengaruhi dimana pemegang polis tersebut membeli asuransi perjalanan dari suatu agen asuransi.

###  Recommendation
- Untuk mendapatkan hasil performa yang mungkin lebih baik lagi, penggunaan hyperparameter tuning yang lebih luas akan membantu 
- Feature Engineering yang lebih dalam mungkin akan menghasilkan performa yang lebih baik lagi
- Penggunaan metriks lain dengan penyesuaian problem statement mungkin akan mendapatkan hasil yang lebih baik
- Mencoba menggunakan resampler lain mungkin akan menghasilkan performa yang berbeda dan mungkin lebih baik, seperti RandomOverSampling, SMOTENC, SMOTE-ENN karena pada dataset ini target tingkat imbalancenya sangat tinggi

- Akurasi yang Lebih Tinggi

    Penggunaan machine learning dalam memprediksi klaim asuransi perjalanan telah terbukti meningkatkan akurasi prediksi. Model Logistic Regression, yang dipilih untuk tugas ini, menunjukkan peningkatan skor ROC AUC setelah tuning, dari 74.70% menjadi 75.28% untuk data pengujian. Ini berarti perusahaan dapat lebih tepat dalam mendeteksi klaim yang sah dan penipuan, yang berdampak langsung pada pengurangan kerugian finansial dan peningkatan profitabilitas.

- Kecepatan Pemrosesan yang Lebih Tinggi

    Dengan mengotomatiskan proses prediksi klaim menggunakan machine learning, waktu pemrosesan klaim dapat dikurangi secara signifikan. Ini tidak hanya meningkatkan efisiensi operasional tetapi juga meningkatkan kepuasan pelanggan karena klaim dapat diselesaikan lebih cepat. Pelanggan yang puas lebih cenderung untuk tetap setia dan merekomendasikan layanan kepada orang lain, yang berpotensi meningkatkan pangsa pasar.

- Penghematan Biaya

    Dengan mengurangi ketergantungan pada tenaga kerja manusia untuk pemrosesan klaim, perusahaan dapat menghemat biaya operasional secara signifikan. Biaya yang dihemat dapat dialokasikan untuk investasi dalam teknologi lebih lanjut atau untuk mengembangkan produk asuransi baru yang inovatif. Selain itu, dengan meningkatkan akurasi prediksi klaim, perusahaan dapat mengurangi pembayaran klaim yang tidak sah, yang berdampak positif pada margin keuntungan.

- Keputusan yang Lebih Tepat

    Model machine learning mampu mengidentifikasi pola dan wawasan dari data yang mungkin terlewatkan oleh analis manusia. Informasi ini dapat digunakan untuk membuat keputusan yang lebih tepat mengenai penetapan harga premi, strategi pemasaran, dan pengelolaan risiko. Keputusan yang lebih baik mengarah pada pengelolaan bisnis yang lebih efisien dan peningkatan profitabilitas.

- Peningkatan Kepuasan Pelanggan

    Dengan kemampuan untuk memberikan layanan yang lebih cepat dan akurat, perusahaan dapat meningkatkan pengalaman pelanggan secara keseluruhan. Pelanggan yang mendapatkan layanan yang cepat dan akurat lebih mungkin untuk merasa puas dan loyal kepada perusahaan. Kepuasan pelanggan yang tinggi dapat diterjemahkan menjadi retensi pelanggan yang lebih baik dan peningkatan pendapatan jangka panjang.

 
