💻 Kelompok 13 Machine Learning

### DETEKSI ANOMALI PADA JARINGAN INTERNET OF THINGS (IoT)

### Menggunakan Algoritma Random Forest dengan Dataset RT-IoT2022

Proyek ini bertujuan untuk membangun dan mengevaluasi model *Machine Learning* **Random Forest** untuk mendeteksi anomali (serangan siber) pada trafik jaringan *Internet of Things* (IoT) secara akurat dan efisien. Penelitian ini berfokus pada penggunaan **Dataset RT-IoT2022** yang merepresentasikan trafik nyata perangkat IoT untuk mengembangkan *Intrusion Detection System* (IDS) berbasis *supervised learning*.

📂 Struktur Proyek

Berikut adalah struktur direktori utama proyek yang berfungsi sebagai kerangka navigasi dan dokumentasi:

```
[nama-folder-proyek]/
├── PaperJournal/        # Naskah akhir proyek dan/atau jurnal (misalnya, .docx dan .pdf)
├── Proposal/            # Dokumen proposal penelitian
├── SourceCode/          # File kode sumber (misalnya, Jupyter Notebooks untuk Preprocessing dan Modeling)
├── Dataset/             # File dataset mentah yang digunakan (RT-IoT2022)
└── README.md            # Dokumentasi lengkap proyek
```

📝 Penjelasan Konsep Utama

🌳 Random Forest

Random Forest adalah metode *ensemble* berbasis pohon keputusan yang dipilih karena kemampuannya dalam menangani data berdimensi besar, ketahanan terhadap *overfitting*, serta memberikan performa tinggi pada kasus klasifikasi. Algoritma ini juga mampu memberikan estimasi kontribusi masing-masing fitur terhadap proses klasifikasi melalui **Feature Importance**.

🌐 Dataset RT-IoT2022

Dataset ini bersumber dari UCI Machine Learning Repository dan berisi data trafik jaringan dari berbagai perangkat IoT nyata seperti sensor suhu, lampu pintar, dan asisten suara. Kategori targetnya adalah trafik **Normal** dan **Serangan (Attack)**. Serangan yang dicakup antara lain Distributed Denial of Service (DDoS), Port Scanning, SSH Brute, dan Force. Dataset awal memiliki $123.117$ baris, yang kemudian dibersihkan dengan menghapus duplikasi ($99.278$ baris dihapus) sehingga tersisa **$23.839$ baris data unik** untuk pemodelan.

⚙️ Metodologi Penelitian

  * **Preprocessing Data**:
      * **Pembersihan:** Penghapusan duplikasi ($99.278$ baris dihapus) dan penanganan nilai hilang (NaN = 0).
      * **Encoding:** **One-Hot Encoding** digunakan untuk mengubah fitur kategorikal menjadi numerik, menghasilkan $91$ fitur.
      * **Normalisasi:** Menggunakan **StandardScaler** (mean $=0$ dan standard deviation $=1$).
      * **Pembagian Data:** Dataset dibagi **80% untuk *Training*** ($19.071$ sampel) dan **20% untuk *Testing*** ($4.768$ sampel).
  * **Modeling (Random Forest)**:
      * **Algoritma:** Random Forest Classifier.
      * **Parameter Kunci:** *n\_estimators* $=100$, *max\_depth* $=20$, *random\_state* $=42$.
      * **Waktu Pelatihan:** Model terlatih dalam $5.37$ detik.
  * **Evaluasi:** Menggunakan metrik **Akurasi, Presisi, Recall, F1-score**, dan **Confusion Matrix**.

🎯 Hasil dan Temuan Utama

  * **Kinerja Klasifikasi:** Model Random Forest menunjukkan performa yang sangat baik dan efektif dalam membedakan trafik normal dan anomali pada lingkungan IoT.
      * **Akurasi:** $98,74\%$.
      * **Presisi:** $98,73\%$.
      * **Recall:** $98,74\%$.
      * **F1-score:** $98,73\%$.
  * **Fitur Paling Berpengaruh (Feature Importance):** Fitur-fitur yang paling signifikan dalam klasifikasi adalah yang terkait waktu antar-paket (*inter-arrival time*), *flag* paket *forward/backward*, dan ukuran *payload*.
    1.  `flow_iat.min` ($0.052290$).
    2.  `fwd_PSH_flag_count` ($0.038006$).
    3.  `fwd_pkts_payload.avg` ($0.037318$).

💡 Rekomendasi Penelitian Lanjutan

  * **Eksplorasi Model Alternatif:** Pengujian model lain seperti **Gradient Boosting**, **XGBoost**, atau metode berbasis **Deep Learning** untuk meningkatkan performa lebih lanjut.
  * **Generalisasi:** Menguji model pada dataset IoT yang lebih beragam untuk menguji konsistensi dan kemampuan generalisasi model.

👤 Identitas Penulis

  * **Penulis:** Aisyah (241572010003) dan Prameswari Kirana Jingga (241572010021).
  * **Institusi:** STMIK Tazkia (Program Studi Sistem Informasi).
  * **Dosen Pengampu:** Hendri Kharisma, S.Kom., M.T..
  * **GitHub Proyek:** `https://github.com/kirana999/Kelompok-13-Machine-Learning`
