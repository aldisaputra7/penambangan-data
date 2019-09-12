- Rata-rata
  rata-rata adalah suatu bilangan yang mewakili sekumpulan data

  Rumus Rata-rata:
  

  $$
  \begin{align*}\bar{X}=\frac{\sum X}{N}\end{align*}
  $$
  
- Median
  Median atau nilai tengah adalah salah satu ukuran pemusatan data, yaitu, jika segugus data diurutkan dari yang terkecil sampai yang terbesar atau yang terbesar sampai yang terkecil, nilai pengamatan yang tepat di tengah-tengah bila jumlah datanya ganjil, atau rata-rata kedua pengamatan yang di tengah bila banyaknya pengamatan genap.

  Rumus Median:
  

  $$
  \begin{align*}\left \{ \frac{n+1}{2} \right \}\end{align*}
  $$
  
- Modus
  Modus adalah data yang paling sering muncul, atau data yang mempunyai frekuensi terbesar.

  Rumus: Nilai yang paling banyak muncul

- Standard deviasi

  Standar deviasi adalah nilai statistik yang digunakan untuk menentukan bagaimana sebaran data dalam sampel, dan seberapa dekat titik data individu ke mean – atau rata-rata – nilai sampel.

  Rumus:

  
  $$
  \begin{align*}\sigma = \sqrt{\frac{1}{N}\sum_{i=1}^{N}}\left ( x_{i} -\mu \right )^{2}\end{align*}
  $$

- Varian
  varian adalah ukuran seberapa jauh sebuah kumpulan bilangan tersebar. Varians nol mengindikasikan bahwa semua nilai sama. Varians selalu bernilai non-negatif: varians yang rendah mengindikasikan bahwa titik data condong sangat dekat dengan nilai rerata (nilai ekspektasi) dan antara satu sama lainnya, sementara varians yang tinggi mengindikasikan bahwa titik data sangat tersebar disekitar rerata dan dari satu sama lainnya.

  rumus: 
  
  
  $$
  \begin{align*}s^{2}\frac{n\sum_{n}^{i=1}x_{i}^{2}-\left ( \sum_{i=1}^{n}x_{1} \right )^{2}}{n\left ( n-1 \right )}\end{align*}
  $$
  





**Di aplikasikan pada python** 

Kita membutuhkan Jupyter notebook ,library python , dan untuk menentukan datanya kita menggunakan excel 

ini adalah contoh untuk menampilkan tabel yang berisi data ,dengan mengambil data yang sudah kita buat di microsoft excel.

```python
import pandas as pd
from scipy import stats
import numpy as np
import seaborn as sns 
data = pd.read_csv("data.csv")
cm = sns.light_palette("white", as_cmap=True)
data.style.background_gradient(cmap=cm)
```

**Hasilnya** 

![](D:\pendat\pendata\docs\gambar1.PNG)



**Selanjutnya kita melakukan cara berikutnya ,** **seperti dibawah ini** 

```
colum = data.columns.tolist()
for x in colum:
    ds=[x for x in data[x]]
    desc= data[x].describe()
    array= [x for x in desc]
    print("Detail kolom ",x)
    print("rata-rata: ",array[1])
    print("Median: ",np.median(np.array(ds)))
    print("Modus: ", stats.mode(ds))
    print("Standard deviasi: ",np.std(ds))
    print("varian: ", stats.variation(ds))
    print("Skewness: ",stats.skew(ds))
    print("Quartil 1: ",array[4])
    print("Quartil 2: ",array[5])
    print("Quartil 3: ",array[6])
    
    print("\n")
```


​    **Dan Hasilnya sebagai berikut :** 

```
Detail kolom  KOPI
rata-rata:  105.416
Median:  106.0
Modus:  ModeResult(mode=array([64]), count=array([11]))
Standard deviasi:  27.12111620121856
varian:  0.25727703765290433
Skewness:  -0.02099108069384586
Quartil 1:  80.0
Quartil 2:  106.0
Quartil 3:  130.0


Detail kolom  ES TEH
rata-rata:  106.532
Median:  108.0
Modus:  ModeResult(mode=array([145]), count=array([13]))
Standard deviasi:  26.43280113798006
varian:  0.24812076313201725
Skewness:  -0.10272439817862315
Quartil 1:  84.0
Quartil 2:  108.0
Quartil 3:  129.0


Detail kolom  ES DEGAN
rata-rata:  102.992
Median:  102.0
Modus:  ModeResult(mode=array([66]), count=array([11]))
Standard deviasi:  26.35048265212613
varian:  0.25584980049058303
Skewness:  0.059224774215851296
Quartil 1:  78.75
Quartil 2:  102.0
Quartil 3:  125.0


Detail kolom  ES KOPYOR
rata-rata:  105.204
Median:  106.0
Modus:  ModeResult(mode=array([131]), count=array([11]))
Standard deviasi:  26.679325028943293
varian:  0.2535961087881002
Skewness:  0.003599489956518007
Quartil 1:  81.75
Quartil 2:  106.0
Quartil 3:  130.0
```



