**Nama : Yoga Lafrianto**

**Project : Bank Marketing Campaign**

**Problome Statement**
  - Memprediksi Keberhasilan Kampanye Pemasaran untuk Deposito Berjangka
  - Identifikasi Faktor-Faktor yang Memengaruhi Keputusan Nasabah untuk Melakukan Deposito Berjangka
  - Optimalisasi Kampanye Pemasaran Bank untuk Meningkatkan Tingkat Deposito Berjangka
  - Analisis Peluang Peningkatan Pendapatan melalui Deposito Berjangka dari Kampanye Pemasaran

**Matric Evaluation**

  - Type 1 Error (False Positive):
  
    - Definisi: Ketika model memprediksi bahwa nasabah akan melakukan deposito (yes), padahal sebenarnya nasabah tidak melakukan deposito (no).
    - Konsekuensi:
      - Sia-sianya biaya kampanye pemasaran: Bank mengalokasikan sumber daya, waktu, dan biaya untuk menghubungi nasabah yang diprediksi akan melakukan deposito, padahal nasabah tersebut tidak tertarik. Ini mengakibatkan pemborosan biaya pemasaran dan sumber daya.
      - Estimasi kerugian: Bank bisa menghitung berapa biaya rata-rata untuk setiap kontak atau upaya pemasaran yang dilakukan pada nasabah. Jumlah nasabah yang tidak melakukan deposito (False Positive) dikalikan dengan biaya pemasaran untuk memberikan estimasi kerugian.
    - Contoh Kerugian: Jika biaya menghubungi satu nasabah adalah 10(dollar), dan ada 100 nasabah yang diprediksi akan melakukan deposito tetapi tidak (False Positive), maka kerugian total adalah 10(dollar) x 100 = 1,000(dollar).
      
- Type 2 Error (False Negative):
  - Definisi: Ketika model memprediksi bahwa nasabah tidak akan melakukan deposito (no), padahal sebenarnya nasabah tersebut bersedia untuk melakukan deposito (yes).
  - Konsekuensi:
    - Kehilangan peluang pendapatan dari nasabah potensial: Bank kehilangan kesempatan untuk mendapatkan deposito dari nasabah yang sebenarnya bersedia, tetapi terlewatkan oleh prediksi model. Ini mengakibatkan hilangnya peluang pendapatan bunga dari deposito yang gagal diperoleh.
    - Estimasi kerugian: Bank bisa menghitung rata-rata keuntungan yang diperoleh dari satu deposito, lalu mengalikan dengan jumlah nasabah yang terlewat (False Negative). Ini akan memberikan estimasi potensi pendapatan yang hilang.
  - Contoh Kerugian: Jika rata-rata keuntungan dari satu deposito adalah 200(dolar) per nasabah, dan ada 50 nasabah yang sebenarnya ingin melakukan deposito tetapi terlewatkan (False Negative), maka potensi pendapatan yang hilang adalah 200(dollar) x 50 = 10,000(dollar).

- Alasan Menggunakan Recall

  Disini kita telah menentukan bahwa kerugian yang paling besar terdapat pada false negativeoleh sebabitu disini menggunakan recall score karena kita ingin berfokus pada Type 2 Error (False Negative) sesuai dengan kondisi yang ada. Karena kita sebagai bank lebih khawatir kehilangan peluang pendapatan dari nasabah yang terlewatkan sehingga dengan menggunakan matric evaluation recall memastikan bahwa sebanyak mungkin nasabah potensial teridentifikasi dengan benar, sehingga meminimalkan jumlah False Negatives.

  **Dictionary**

  
  *Profil Nasabah*
    - age (usia): Usia nasabah.
    - job (pekerjaan): Jenis pekerjaan nasabah.
    - balance (saldo): Saldo di rekening nasabah.
    - housing (kepemilikan rumah): Apakah nasabah memiliki rumah atau tidak.
    - loan (pinjaman): Apakah nasabah memiliki pinjaman atau tidak.
 
  *Data Pemasaran*
    - contact (kontak): Jenis komunikasi kontak yang digunakan.
    - month (bulan): Bulan terakhir nasabah dihubungi dalam satu tahun.
    - campaign (kampanye): Jumlah kontak yang dilakukan selama kampanye ini untuk nasabah tersebut.
    - pdays (jumlah hari sejak kontak terakhir): Jumlah hari sejak nasabah dihubungi dari kampanye sebelumnya.
    - poutcome (hasil kampanye sebelumnya): Hasil dari kampanye pemasaran sebelumnya.
    - deposit (deposito): Apakah nasabah melakukan deposito atau tidak.
 
  **Data Spliting**
  - X = 'deposit'
  - y = age, job, balance, housing, loan, contact, month, campaign, pdays, poutcome
 
  **Model Explorasi**
  - Rule Base --> Basic tanpa menggunakan mechinelearning
  - Experiment 1: Dengan Outliers --> Base Model (LogisticRegression, DecisionTreeClassifier, KNeighborsClassifier) , voting, stacking, bagging, boosting *dan menggunakan* outliers
  - Experiment 2: Tanpa Outliers --> Base Model (LogisticRegression, DecisionTreeClassifier, KNeighborsClassifier) , voting, stacking, bagging, boosting *tanpa menggunakan* outliers
  - Experiment 3: Base Model with Feature Selection --> Model(LogisticRegression, DecisionTreeClassifier, RandomForestClassifier, GradientBoostingClassifier, XGBClassifier dengan outliers dan menggunakan feature selection RFE
