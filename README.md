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
