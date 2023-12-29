# **Web Model Deployment Machine Learning Using Flask - Data Tabular📖📖**

# **Overview**
Dalam Project Machine Learning ini dilakukan untuk melakukan deployment model machine learning menggunakan Flask, sebuah framework web berbasis Python. Model yang di-deploy dapat memprediksi penghasilan seseorang berdasarkan fitur-fitur tertentu.

# **About Dataset**
Dataset yang digunakan dalam proyek ini adalah dataset income dalam format CSV yang terdiri dari 43.957 data dengan 15 atribut, yaitu age, workclass, fnlwgt, education, educational-num, marital-status, occupation, relationship, race, gender, capital-gain, capital-loss, hours-per-week, native-country, dan income_>50K. Dataset ini memiliki dua kelas, di mana kelas 1 mewakili individu yang memiliki pemasukan lebih dari 50K, sedangkan kelas 0 mewakili individu yang tidak memiliki pemasukan lebih dari 50K.
<p align="center">
  <img width="910" alt="image" src="https://github.com/elisa11ramadanti/WebModelDeployment-ML/assets/78844334/2298c994-1909-4dd7-bcae-def5fd07f8f5">
</p>

<p align="center">
  <img width="910" alt="image" src="https://github.com/elisa11ramadanti/WebModelDeployment-ML/assets/78844334/75d900f5-d87f-46a0-9599-4917c83b703e">
</p>

### Link Dataset
```bash
https://drive.google.com/file/d/1w_AJE2pfCWM7R_AlVPWxzv5yVU20-AXd/view?usp=drive_link
```
## Data Preprocessing
**1. Data Cleaning:**
- Menghapus baris dengan nilai yang hilang pada kolom tertentu ('workclass', 'occupation', 'native-country').
- Menghapus baris duplikat dari dataset.

**2. Label Encoding:**
- Memanfaatkan LabelEncoder untuk mengubah kolom-kolom kategorikal ke format numerik.
- Mengevaluasi distribusi nilai pada kolom 'education' dan 'occupation'.

**3. Column Selection:**
- Memilih kolom-kolom yang relevan untuk pemodelan ('age', 'education', 'occupation', 'hours-per-week', 'native-country', 'income_>50K').

**4. Train-Test Split:**
- Memisahkan dataset menjadi set pelatihan dan pengujian menggunakan fungsi train_test_split.


## Modelling
**1. TabNet Classifier:**
- Menerapkan klasifikasi TabNet menggunakan TabNetClassifier dari perpustakaan PyTorch TabNet.
  
**2. Model Training:**
- Melatih model TabNet pada dataset pelatihan.
- Mengevaluasi model pada kedua set pelatihan dan pengujian.
  
**3.Model Prediction:**
- Melakukan prediksi pada set pengujian dan menghitung akurasi.
  
**4. Classification Report:**
- Mengubah probabilitas prediksi menjadi label biner (0 atau 1).
- Menampilkan laporan klasifikasi dengan presisi (precision), recall, dan skor F1.
  <p align="center">
     <img width="500" alt="image" src="https://github.com/elisa11ramadanti/WebModelDeployment-ML/assets/78844334/2c1aa290-58fb-4627-aa6a-4915dd0dc286">
  </p>
**5. Save Model:**
- Seperti code dibawa ini:
  ```bash
  filesaved = clf.save_model('model_tabular_h5')
  ```
# **Project Structure**
* Model Machine Learning: Model TabNet yang telah dilatih digunakan untuk memprediksi penghasilan berdasarkan data tabular.
* Aplikasi Flask: Terdapat tiga halaman, satu untuk menampilkan tentang website, lalu untuk input data (index.html) dan satu untuk menampilkan hasil prediksi (predict.html).
* Styling: Terdapat file styles.css untuk memberikan tampilan yang menarik dan responsif.

# **Step-by-step Guide**
#### 1. Save the model in .h5 format
```bash
df.to_hdf('income_.h5', key='data', mode='w')
```
#### 2. Install Dependencies

```bash
pip install -r requirements.txt
```
#### 3. Install the PyTorch TabNet library
* Perintah diatas digunakan untuk menginstal pustaka PyTorch TabNet. PyTorch TabNet adalah implementasi dari algoritma TabNet yang digunakan untuk pembelajaran mesin pada data tabular.
```bash
pip install pytorch_tabnet
```
#### 4. Run the Flask application

```bash
flask run
```
* menjalankan perintah ini akan memulai server pengembangan dan membuat aplikasi web yang dapat diakses pada alamat http://localhost:5000/.

## Code Structure
* app.py: file utama Flask yang menangani routing dan integrasi model TabNet.
* templates/first.html: Template untuk halaman tentang website.
* templates/index.html: Template untuk halaman input data.
* templates/predict.html: Template untuk halaman hasil prediksi.
* static/css/styles.css: Berkas CSS untuk styling antarmuka web.

## Input Attributes for Web Predict:
- Age: data umur
- Education: data edukasi
- Occupation: data pekerjaan
- Hours per Week: jumlah jam yang dihabiskan untuk bekerja dalam seminggu
- Native Country: asal daerah

## Requirements.txt
```bash
Flask==3.0.0
Werkzeug==3.0.1
datetime==4.3.0
Numpy==1.23.5
Pandas==1.5.3
```
## Web Display

<p align="center">
 <img width="948" alt="image" src="https://github.com/elisa11ramadanti/WebModelDeployment-ML/assets/78844334/72b88022-7f2c-4644-8320-a7aa038aff84">

</p>
<p align="center">
 <img width="948" alt="image" src="https://github.com/elisa11ramadanti/WebModelDeployment-ML/assets/78844334/59e83513-8bc9-4508-a06f-2086784c2dd3">
</p>
<p align="center">
<img width="948" alt="image" src="https://github.com/elisa11ramadanti/WebModelDeployment-ML/assets/78844334/4342e49a-b279-4978-9de7-863da22e5503">
</p>

## **Author**
#### **Elisa Ramadanti - 202010370311300**
