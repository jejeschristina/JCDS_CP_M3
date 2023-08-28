## **Context**

*Bike Sharing* adalah generasi baru persewaan sepeda di mana seluruh proses mulai dari pendaftaran pengguna, persewaan, serta pengembalian telah dilakukan secara teknologi otomatisasi. Melalui sistem ini, pengguna dapat dengan mudah menyewa sepeda dari suatu lokasi dan mengembalikannya ke lokasi lain sesuai kebutuhan. Banyak kota metropolitan yang berupaya mengurangi kemacetan dan polusi dengan mengurangi jumlah mobil di jalan-jalan dalam kota dengan meningkatkan infrastruktur bersepeda dan meluncurkan program *Bike Sharing*. Menurut data yang di rilis pada situs [Statista.com](https://www.statista.com/chart/14542/bike-sharing-programs-worldwide/), hingga pertengahan tahun 2018, ada lebih dari 1600 program *Bike Sharing* yang beroperasi di seluruh dunia dan menyediakan lebih dari 18 juta sepeda untuk keperluan umum.

Berbeda dengan alat transportasi umum lainnya, *Bike Sharing* biasanya berkapasitas perorangan dan digunakan untuk menempuh perjalanan yang dekat sehingga menyebabkan tingkat *turnover* sepeda yang tinggi. Hal ini menjadi tantangan bagi penyedia *Bike Sharing* untuk mengakomodir seluruh permintaan pengguna. Jumlah permintaan penyewaan sepeda tentu dapat berbeda bila dihadapkan pada waktu dan kondisi yang berbeda pula. Misalnya, pada jam pergi-pulang sekolah atau kantor, menggunakan *bike sharing* bisa menjadi salah satu pilihan transportasi bagi sebagian masyarakat sehingga dapat menyebabkan permintaan penggunaan *bike sharing* menjadi tinggi. Namun permintaan penggunaan *bike sharing* mungkin tidak akan terlalu banyak apabila cuaca sedang tidak mendukung, karena berkendara dengan sepeda saat cuaca buruk dapat sangat membahayakan.

## **Problem Statement**

Hingga saat ini, *bike sharing* mulai banyak digunakan pada perkotaan sebagai bentuk peningkatan mobilitas yang cenderung nyaman dan fleksible. Dengan meningkatnya permintaan penggunaan *bike sharing*, ketersediaan sepeda yang stabil di setiap lokasi menjadi penting. Bila ketersediaan sepeda pada lokasi tidak mencukupi permintaan pengguna, maka pengguna cenderung harus menunggu atau malah mencari alternatif transportasi yang lain sehingga mengurangi potensi pendapatan yang dapat diterima penyedia. Di lain hal, ketersediaan sepeda yang berlebihan pada suatu lokasi mencerminkan ketidakefektifan penyedia. **Oleh karena itu, peningkatan permintaan penggunaan *bike sharing* tentunya harus diimbangi dengan tingkat ketersediaan sepeda pada waktu dan kondisi tertentu sehingga penyedia dapat menyediakan kapasitas yang cukup kepada pengguna saat membutuhkan, mengurangi *waiting time* pengguna serta mengurangi tingkat *idle* sepeda karena tidak digunakan**.

## **Goals**

Berdasarkan permasalahan tersebut, penyedia *Bike Sharing* perlu memiliki *prediction 'tool'* untuk dapat **memprediksi jumlah permintaan penggunaan *bike sharing* pada waktu dan kondisi tertentu** seperti kondisi cuaca, hari libur, periode musim, dan lainnya. Prediction 'tool' ini berpotensi membantu manajemen dalam mengambil keputusan yang tepat guna mengoptimalkan ketersediaan sepeda, strategi pemasaran, dan alokasi sumber daya.

Bagi penyedia, prediksi jumlah permintaan penggunaan *bike sharing* yang semakin akurat dapat meningkatkan potensi pendapatan perusahaan serta peningkatan kepuasan pengguna karena waktu tunggu yang minimal.

## **Analytic Approach**

Jadi, yang perlu dilakukan adalah menganalisis data untuk menemukan pola dari fitur-fitur yang ada, yang membedakan pada kondisi dan waktu tertentu.

Selanjutnya, kita akan membangun suatu model untuk memprediksi suatu nilai numerik atau biasa disebut dengan model regresi, model ini dapat digunakan sebagai 'tool' yang membantu penyedia *Bike Sharing* ini untuk memprediksi banyaknya penyewa berdasarkan kondisi dan waktu tertentu.

## **Metric Evaluation**

Evaluasi metrik pada pemodelan ini akan difokuskan pada RMSLE, namun metrik RMSE, MAE, dan MAPE akan digunakan juga sebagai pembanding.

- [RMSLE](https://medium.com/analytics-vidhya/root-mean-square-log-error-rmse-vs-rmlse-935c6cc1802a) adalah nilai rataan akar kuadrat dari error yang digunakan khusus jika fitur target ditransformasikan menggunakan perhitungan logaritma. Nilai dari metrik ini dapat mereduksi error yang ditimbulkan oleh outliers atau perbedaan nilai yang terlalu jauh. Metrik ini juga memberikan bobot yang lebih besar pada nilai prediksi yang lebih kecil dari nilai aktual atau biasa dsebut dengan *underestimation*. Sedangkan untuk prediksi yang *overestimation*, metrik ini akan memberikan bobot yang lebih kecil. Metrik ini cocok dengan kasus bisnis di mana prediksi yang underestimation lebih tidak dapat diterima daripada prediksi yang overestimation. Pada kasus ini, karena tujuan kita meningkatkan potensi pendapatan perusahaan dan mengurangi waktu tunggu dari pengguna, maka metrik ini cocok digunakan.
- RMSE merupakan nilai rataan akar kuadrat dari error, metrik ini dapat digunakan untuk mengukur seberapa jauh nilai prediksi yang dihasilkan berdasarkan rataannya.
- MAE adalah rataan nilai absolut dari error
- MAPE adalah rataan persentase error yang dihasilkan oleh model regresi, dengan nilai keakuratan berdasarkan buku dari [Lewis's (1982)](https://www.nrpa.org/globalassets/journals/jlr/2003/volume-35/jlr-volume-35-number-4-pp-441-454.pdf) mengatakan bahwa jika nilai MAPE sebesar 0.10 atau 10% merupakan prediksi yang sangat akurat, 11-20% merupakan prediksi yang baik, 21-50% merupakan prediksi yang masuk akal, dan 51% dan lebih banyak lagi adalah prediksi yang tidak akurat, adapun jika lebih dari 100% merupakan prediksi yang sangat tidak akurat.

Semakin kecil nilai RMSLE, RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi banyaknya permintaan *bike sharing* dengan limitasi fitur yang digunakan.
