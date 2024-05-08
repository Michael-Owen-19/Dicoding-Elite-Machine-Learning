# Technical Exercise Result (Machine Learning 1) (1)

### Project name: Submission Membuat Model Machine Learning dengan Data Time Series

## Project Summary

- Tambahkan Identitas anda pada project machine learning yang kamu kerjakan
- Selain menggunakan helper function windowed_dataset, kamu juga dapat mempelajari penggunaan [TimeSeriesGenerator](https://machinelearningmastery.com/how-to-use-the-timeseriesgenerator-for-time-series-forecasting-in-keras/) untuk mempersiapkan data time series agar dapat diterima oleh model
- Kamu juga dapat menggunakan fungsi [TimeSeriesSplit](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.TimeSeriesSplit.html) untuk membagi dataset
- Dataset timeseries tidak boleh di-shuffle karena memiliki urutan waktu yang terus berurutan. Jika dataset time series di-shuffle, maka urutan waktu dari data tersebut akan hilang dan tidak dapat digunakan untuk analisis.
- Kamu dapat memberikan insight terhadap dataset dengan melakukan visualisasi data timeseries [time series data visualizations](https://towardsdatascience.com/8-visualizations-with-python-to-handle-multiple-time-series-data-19b5b2e66dd0)
- Untuk menurunkan MAE, kamu dapat [Mengatur Hyperparameter LSTM pada Time Series](https://machinelearningmastery.com/tune-lstm-hyperparameters-keras-time-series-forecasting/) dan [Menggunakan Bidirectional LSTM](https://stackoverflow.com/questions/43035827/whats-the-difference-between-a-bidirectional-lstm-and-an-lstm)
- Kamu dapat download dataset dari Kaggle dengan menggunakan [Kaggle API](https://github.com/Kaggle/kaggle-api) dan [download datasets from Kaggle to Google Colab](https://medium.com/geekculture/how-to-download-datasets-from-kaggle-to-google-colab-7bb3c5a44c51) dan [cara menghubungkan drive ke colab](https://medium.com/@dede.brahma2/cara-menggunakan-google-colaboratory-5f5e4393ac2f#:~:text=Menggunakan%20Colab&text=Masuk%20kedalam%20google%20drive%20kemudian,colab%E2%80%9D%20setelah%20muncul%20klik%20connect.&text=Setelah%20berhasil%20instalasi%2C%20buat%20folder,kemudian%20masuk%20kedalam%20folder%20tersebut.)
- Kamu juga dapat mempelajari model yang kamu buat apakah sudah good fit atau belum [Perbedaan Goodfit, Overfit dan Underfit](https://machinelearningmastery.com/learning-curves-for-diagnosing-machine-learning-model-performance/)
- Kamu bisa mempelajari beberapa hal berikut untuk memperluas pengetahuan tentang machine learning:
    - [Menerapkan Custom Callback](https://keras.io/api/callbacks/)
    - [Memahami Impact Learning Rate](https://machinelearningmastery.com/understand-the-dynamics-of-learning-rate-on-deep-learning-neural-netw)
- Kamu bisa menghapus **text cell**, **code cell**, atau **komentar kode** yang tidak digunakan di dalam notebook agar penulisan kode dan text lebih rapi atau kamu dapat menggunakan fitur markdown/text cell untuk menjelaskan bagian **code cell** yang telah kamu buat pada interactive python notebook. Sehingga, notebook kamu lebih informatif.
- Agar penulisan kode lebih rapi pada proses debugging (preprocess data, membuat model, dan melakukan testing), kamu bisa menyimpan seluruh import pada Code Cell yang paling atas untuk meningkatkan kualitas keterbacaan kode.
- Google Collaboratory memiliki fitur untuk menggunakan GPU. Kamu dapat memanfaatkan GPU gratis pada google Collaboratory agar proses training yang dilakukan lebih cepat.
- Kamu dapat mencoba menerapkan callback MAE dengan treshold yang lebih rendah misalnya 5%

## Code Review

```python
# membuat plot akurasi
plt.plot(history.history['mae'])
plt.plot(history.history['val_mae'])
plt.title('Akurasi Model')
plt.ylabel('Accuracy')
plt.xlabel('Epoch')
plt.legend(['train', 'test'], loc='upper left')
plt.show()
```

> Sebaiknya gunakan penamaan plot yang sesuai dengan data yang ditampilkan. Penggunaan keterangan dan judul yang salah pada gambar dapat menimbulkan kesalahan pada saat menginterpretasi gambar tersebut. Pada kasus di atas data yang ditampilkan adalah MAE bukan Akurasi, sehingga sebaiknya judul plot dan label plot diubah menjadi MAE.
> 

```python
optimizer = tf.keras.optimizers.SGD(lr=1.0000e-04, momentum=0.9)
```

> parameter `lr` telah deprecated pada Keras optimizer, sebaiknya gunakan parameter `learning_rate` atau gunakan legacy optimizer misalnya tf.keras.optimizers.legacy.SGD.
>