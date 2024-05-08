# Technical Exercise Result (Machine Learning 2)

### Project name: Submission Membuat Model Machine Learning dengan Data Time Series

## Project Summary

- Kamu bisa menggunakan helper function windowed_dataset untuk preprocessing data seperti pada [Latihan Time Series dengan LSTM](https://www.dicoding.com/academies/185/tutorials/10174), selain itu kamu juga dapat mempelajari penggunaan [TimeSeriesGenerator](https://machinelearningmastery.com/how-to-use-the-timeseriesgenerator-for-time-series-forecasting-in-keras/) untuk mempersiapkan data time series agar dapat diterima oleh model
- Kamu juga dapat menggunakan fungsi [TimeSeriesSplit](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.TimeSeriesSplit.html) untuk membagi dataset
- Dataset timeseries tidak boleh di-shuffle karena memiliki urutan waktu yang terus berurutan. Jika dataset time series di-shuffle, maka urutan waktu dari data tersebut akan hilang dan tidak dapat digunakan untuk analisis.
- Kamu dapat memberikan insight terhadap dataset dengan melakukan visualisasi data timeseries [time series data visualizations](https://towardsdatascience.com/8-visualizations-with-python-to-handle-multiple-time-series-data-19b5b2e66dd0)
- Untuk menurunkan MAE, kamu dapat [Mengatur Hyperparameter LSTM pada Time Series](https://machinelearningmastery.com/tune-lstm-hyperparameters-keras-time-series-forecasting/) dan [Menggunakan Bidirectional LSTM](https://stackoverflow.com/questions/43035827/whats-the-difference-between-a-bidirectional-lstm-and-an-lstm)
- Kamu dapat download dataset dari Kaggle dengan menggunakan [Kaggle API](https://github.com/Kaggle/kaggle-api) dan [download datasets from Kaggle to Google Colab](https://medium.com/geekculture/how-to-download-datasets-from-kaggle-to-google-colab-7bb3c5a44c51) dan [cara menghubungkan drive ke colab](https://medium.com/@dede.brahma2/cara-menggunakan-google-colaboratory-5f5e4393ac2f#:~:text=Menggunakan%20Colab&text=Masuk%20kedalam%20google%20drive%20kemudian,colab%E2%80%9D%20setelah%20muncul%20klik%20connect.&text=Setelah%20berhasil%20instalasi%2C%20buat%20folder,kemudian%20masuk%20kedalam%20folder%20tersebut.)
- Kamu juga dapat mempelajari model yang kamu buat apakah sudah good fit atau belum [Perbedaan Goodfit, Overfit dan Underfit](https://machinelearningmastery.com/learning-curves-for-diagnosing-machine-learning-model-performance/)
- Kamu bisa mempelajari beberapa hal berikut untuk memperluas pengetahuan tentang machine learning:
    - [Menerapkan Custom Callback](https://keras.io/api/callbacks/)
    - [Memahami Impact Learning Rate](https://machinelearningmastery.com/understand-the-dynamics-of-learning-rate-on-deep-learning-neural-netw)
- Kamu bisa mencoba menerapkan optimizer selain Adam berikut referensi yang dapat kamu baca [Tensorflow Optimizers](https://www.tensorflow.org/api_docs/python/tf/keras/optimizers).
- Kamu bisa menghapus **text cell**, **code cell**, atau **komentar kode** yang tidak digunakan di dalam notebook agar penulisan kode dan text lebih rapi atau kamu dapat menggunakan fitur markdown/text cell untuk menjelaskan bagian **code cell** yang telah kamu buat pada interactive python notebook. Sehingga, notebook kamu lebih informatif.
- Setelah proses training selesai, kamu bisa menambahkan plot MAE untuk mempermudah evaluasi model secara grafik dengan menggunakan:
    1. [Matplotlib](https://matplotlib.org/stable/tutorials/introductory/pyplot.html)
    2. [Tensorboard](https://www.tensorflow.org/tensorboard/tensorboard_in_notebooks)
- Google Collaboratory memiliki fitur untuk menggunakan GPU. Kamu dapat memanfaatkan GPU gratis pada google Collaboratory agar proses training yang dilakukan lebih cepat.

## Code Review

![Screenshot 2024-05-08 113541.png](Technical%20Exercise%20Result%20(Machine%20Learning%202)%2047d02901c67c40708f82e509f48b4285/Screenshot_2024-05-08_113541.png)

> Sebaiknya data.head() dipisah pemanggilannya ke dalam cell baru agar dapat meningkatkan keterbacaan hasil kode setelah dijalankan
>