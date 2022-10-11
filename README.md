# Superstore Sales Dataset
#### Predict Sales using Time Series

##### Objective statement
* Get business insiht sales per month
* Get business insiht which popular consumer procudct 

#### Methodology :
* Descriptive analysyis
* Graph Analysis
* Segment Analysis

#### Business benefit :
* Helping Business developmnet Team to how to prevent lost in the future based on sales prediction


## Data Understanding
data dari 2015-01-02 sampai 2018-12-30

data didownload di kaggle ; https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting

data dictionary :

 1. Order ID : Id order 
 2. Order date : Tanggal pemesanan barang
 3. Ship Date : Tanggal pengiriman barang yang telah dipesan
 4. Ship Mode : Jenis pengiriman
 5. Customer ID : Id pelanggan
 6. Customer Name : Nama pelanggan
 7. Segment : Jenis pelanggan
 8. Country : Negara pelanggan
 9. City : Kota Pelanggan
 10. State : kota bagian pelanggan
 11. Region : Wilayah pelanggan
 12. Product ID : Id barang
 13. Category : Kategori barang
 14. Sub-Category : sub kategori barang
 15. Product Name : Nama produk/barang
 16. Sales : Penjualan dalam $


### Data Preparation :
* Python 3.10
* packages : pandas,numpy,Mathplotlib, seaborn, sklearn, XGBoost

### Data Cleansing :
* terdapat missing value pada `Postal Code` sebanyak 11%, namun hal itu disebabkan karna pada `State` Vermont tidak memiliki postal code. Dapat di handle

### EDA
1. Montly Sales


![1](https://user-images.githubusercontent.com/97732456/195076592-eec22234-e48e-4946-9e87-ee4f3d986447.png)

![image](https://user-images.githubusercontent.com/97732456/195078438-d612de55-67de-49b1-9b72-9be78d52ea5d.png)


Terlihat pada grafik, trend sales mengalamin kenaikan dari tahun ke tahun. Namun Pada tahun pertengahan 2015 hingga awal 2016 mengalami penurunan penjualanan pada semua sektor seperti segment kustomer dan kategori barang

2. top 10 kota dan state penjualan terbanyak


![1](https://user-images.githubusercontent.com/97732456/195077588-e2fb613d-1fa1-45d5-856c-6392dbb401a3.png)

![1](https://user-images.githubusercontent.com/97732456/195078053-b0360e06-76f1-4de7-89dd-75e491317318.png)


Pembelian pada kota New York paling tinggi dalam segi jumlah dan penjualanan .Namun kota bagian California yang paling tinggi dalam segi jumlah dan penjualanan

3. top 10 product 


![image](https://user-images.githubusercontent.com/97732456/195078246-cc027d62-472a-418b-9ee5-fa08007fa7a2.png)


Produk staple dan staple envelop menjadi barang paling laris

## Modelling
### Prepared data set
* Karena data menunjukkan tren yang meningkat dari waktu ke waktu,  perlu membuat data ini stasioner untuk meningkatkan fase pelatihan model.
Kita membuat kolom diff yaitu perbedaan pada kolom 'Sales' untuk membuat data stasioner
* Gunakan data pada 12 bulan sebelumnya sebagai input dan data penjualan bulan ke-13 digunakan sebagai output untuk model

### Reprocessing
* split data than using min max scaller
* Dalam DataFrame , kolom pertama sesuai dengan output dan kolom yang tersisa bertindak sebagai fitur input:
* Membuat kerangka data prediksi untuk menggabungkan harga jual yang diprediksi dari semua train algoritm 
* Extract data bulan ke 13  yang menjadi test data. Nilai-nilai ini nantinya akan digunakan untuk mencari prediksi harga jual dari hasil prediksi selisih penjualan melalui model yang dilatih

### Forecast Sales using Linear Regression
* fit model
* train model
* Model Evaluation
Interpretation with predict data:
1. On Average our prediction deviates the true `Sales` by 12610.952
2. Moreover, this 12610.952 is equivalent to 21% deviation relative to the true `Sales`. which is still good (threshold 30%)
* Visualisasi nilai prediksi


![image](https://user-images.githubusercontent.com/97732456/195079838-696949c1-175b-4093-9bc4-41cd49a61f62.png)


### Forecast Sales using Random Forest Regressor
* fit model
* train model
* Model Evaluation
Interpretation with predict data:
1. On Average our prediction deviates the true `Sales` 14614.438
2. Moreover, this 12610.952 is equivalent to 23% deviation relative to the true `Sales`. which is still good (threshold 30%)
* Visualisasi nilai prediksi


![image](https://user-images.githubusercontent.com/97732456/195080165-47335ded-06f5-477c-8058-ebc1e4281ce1.png)



### Forecast Sales using XGBoost Regressor
* fit model
* train model
* Model Evaluation
Interpretation with predict data:
1. On Average our prediction deviates the true `Sales` 15665.56
2. Moreover, this 12610.952 is equivalent to 24% deviation relative to the true `Sales`. which is still good (threshold 30%)
* Visualisasi nilai prediksi


![image](https://user-images.githubusercontent.com/97732456/195080288-64993a26-10cf-4069-af3e-0ade79946483.png)


### Comparing Forecast Sales using Machine Learning Algorithms
Train model Regresi Linier, RF, XG Boost untuk memperkirakan jumlah barang yang terjual per bulan berturut-turut setelah memasukkan data penjualan 12 bulan sebelumnya. Model yang dilatih dievaluasi menggunakan Root Mean Squared Error, Mean Absolute Error,Mean Absolute Percentage Error, dan R2 Score antara nilai penjualan yang diprediksi dan nilai penjualan aktual dalam kumpulan data pengujian.



![image](https://user-images.githubusercontent.com/97732456/195083274-bb8516e6-d7d7-4b9b-b51c-29a43aa42fea.png)



Semua model mampu memprediksi penjualan pelanggan dengan rata-rata root mean squared error sekitar 16677, mean absolute error sekitar 13667, dan skor R2 sekitar 0,35. 

### Coclusion
