# Mengukur Efektivitas Iklan Menggunakan A/B Testing

# Ringkasan

Dengan menggunakan data [Marketing A/B Testing](https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing), dilakukan uji statistik menggunakan Z-test untuk mengukur efektivitas iklan terhadap pembelian. Data ini terbagi menjadi dua grup, yaitu grup ad yang diperlihatkan iklan, dan grup psa yang diperlihatkan Public Service Announcement (PSA). Setelah melakukan uji statistik, diketahui bahwa iklan yang ditampilkan terbukti efektif meningkatkan pembelian, sehingga penayangan iklan direkomendasikan untuk dilanjutkan. Dengan asumsi jumlah pengguna pada grup ad tetap berada pada skala serupa (~564 ribu pengguna), iklan ini berpotensi menghasilkan sekitar 4,343 pembelian tambahan.

# Pertanyaan Bisnis

1. Apakah iklan lebih efektif meningkatkan pembelian dibandingkan PSA?
2. Seberapa besar potensi tambahan pembelian yang dihasilkan oleh iklan?

# Tools yang Digunakan

## 1. Python

Digunakan sebagai tools utama pada proses analisis. Library yang digunakan pada project ini antara lain:

- Pandas: Untuk manipulasi dan pengolahan data.
- Numpy: Untuk membuat array.
- Statsmodels: Untuk melakukan Z-test.

## 2. Power BI

Digunakan untuk menyajikan hasil analisis dalam bentuk dashboard.

# Proses Analisis

## Merumuskan Hipotesis

Hipotesis dirumuskan berdasarkan pertanyaan bisnis yang ingin dijawab, yaitu apakah iklan lebih efektif meningkatkan pembelian dibandingkan PSA. Berdasarkan hal tersebut, hipotesis yang dirumuskan adalah sebagai berikut:

> H0: Conversion rate grup ad tidak lebih tinggi dari grup psa. <br>
> H1: Conversion rate grup ad lebih tinggi dari grup psa.

## Melakukan Z-Test

Proses diawali dengan memisahkan data grup ad dan psa untuk memudahkan perhitungan, kemudian dilanjutkan dengan menghitung jumlah konversi dan jumlah pengguna masing-masing grup. Setelah melakukan Z-test, diperoleh Z-score sebesar 7.37 dan p-value sebesar 8.53 × 10⁻¹⁴, jauh lebih kecil dari α (0.05). Dengan demikian, H0 ditolak, conversion rate grup ad terbukti lebih tinggi dibandingkan grup psa, dan peningkatan ini bukan karena kebetulan, melainkan murni karena iklan.

Detail perhitungan dapat dilihat pada notebook berikut: [1_Z_Test_Ad_Effectiveness](Python/1_Z_Test_Ad_Effectiveness.ipynb)

# Dashboard Overview

Bagian ini menampilkan dashboard yang dibuat menggunakan Power BI untuk menyajikan hasil analisis.

File dashboard dapat dilihat disini: [Ad_Impact_Overview](Power_BI/Ad_Impact_Overview.pbix)

### Tampilan Dashboard:

<img src="Images/Dashboard_Overview.png" width="700">

**Note**: Icon yang digunakan dalam dashboard ini bersumber dari [Magnific](https://www.magnific.com/app).

# Business Recommendation

Hasil uji statistik menunjukkan bahwa iklan yang ditampilkan terbukti efektif meningkatkan pembelian dibandingkan PSA. Oleh karena itu, penayangan iklan direkomendasikan untuk dilanjutkan, dengan tetap menyisakan sebagian kecil pengguna sebagai grup psa untuk terus memantau efektivitasnya dari waktu ke waktu. Dengan asumsi jumlah pengguna pada grup ad tetap berada pada skala serupa (~564 ribu pengguna), iklan ini berpotensi menghasilkan sekitar 4,343 pembelian tambahan.

Detail perhitungan dapat dilihat pada notebook berikut: [2_Additional_Purchase_Estimation](Python/2_Additional_Purchase_Estimation.ipynb)