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
