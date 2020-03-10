# DERET MACLAURIN

Deret MacLaurin merupakan suatu fungsi f(x) yang memiliki turunan f'(x), f”(x), f”'(x), dan seterusnya yang kontinyu dalam interval I dan a, x I maka untuk x disekitar a yaitu |x – a| < , f(x) dapat diekspansi kedalam Deret Taylor. Dalam matematika, deret Taylor adalah representasi fungsi matematika sebagai jumlahan tak hingga dari suku-suku yang nilainya dihitung dari turunan fungsi tersebut di suatu titik. Deret ini dapat dianggap sebagai limit polinomial Taylor. Deret Taylor mendapat nama dari matematikawan Inggris yaitu Brook Taylor. Bila deret tersebut terpusat di titik nol, deret tersebut dinamakan sebagai deret Maclaurin, dari nama matematikawan Skotlandia Colin Maclaurin. Sebuah fungsi f(x) yang mempunyai turunan f^1(x), f^2(x), f^3(x), dan seterusnya yang continue dalam interval I dan a, x I maka dapat diekspansi kedalam deret Taylor, yaitu sebagai berikut :
$$
f(x) \approx f(a) + \frac{f^{1}(a)(x-a)}{1!} + \frac{f^{2}(a)(x-a)^{2}}{2!}+ \frac{f^{3}(a)(x-a)^{3}}{3!} + ... \frac{f^{n}(a)(x-a)^{n}}{n!}
$$
Atau bisa dinyatakan :
$$
f(x) = \sum_{ n = 0 } ^ {infinite} \frac{f^n(a)}{n!} (x-a)^n
$$


Deret Maclaurin hampir sama dengan deret Taylor tetapi dalam deret maclaurin nilai a = 0, sehingga persamaannya yaitu :
$$
f(x) = f(0) + \frac {f'(0)}{1!}x + \frac {f''(0)}{2!}x^2 + \frac {f'''(0)}{3!}x^3 + \frac {f''''(0)}{4!}x^4 + .......
$$
Dalam deret Maclaurin yaitu menjumlahkan tiap-tiap suku sampai batas yang ditentukan, sehingga akan menghasilkan nilai yang mendekati nilai sebenarnya. Deret maclaurin ini berguna untuk menghitung atau menghampiri nilai fungsi yang dihitung secara manual. Dalam kasus ini akan dihitung nilai e^x secara manual dengan x=4, dan juga diterapkannya dalam bahasa python untuk menghitung e^2x dengan ekspansi sampai error.



### Perhitungan nilai e^x dengan x=4[¶](https://mdandikuswanto.github.io/Komputasi-Numerik/#perhitungan-nilai-ex-dengan-x4)

Perhitungan nilai e^x memiliki fungsi yaitu f(x) = e^x dengan turunan berpola seperti berikut :
$$
f(x) = e^x
$$

$$
f^1(x) = e^x
$$

$$
f^2(x) = e^x
$$

$$
f^n(x) = e^x
$$

Sehingga ketika e^2x maka pola turunannya yaitu :
$$
f(x) = e^{2x}
$$

$$
f^1(x) = 2e^{2x}
$$

$$
f^2(x) = 4e^{2x}
$$

$$
f^2(x) = 8e^{2x}
$$

$$
f^2(x) = 16e^{2x}
$$

$$
.
.
.
$$

Oleh karena itu, dapat disimpulkan bahwa turunannya adalah koefisien dipangkat turunan ke-i, kemudian kita dapat menghitung dengan deret Maclauren, yaitu sebagai berikut :
$$
f(x)= f(0)+ \frac{f^1(0)x}{1!} + \frac{f^2(0)x^2}{2!} + \frac{f^3(0)x^3}{3!}+\frac{f^4(0)x^4}{4!}...
$$

$$
f(x)= f(0)+\frac{2}{1!}x + \frac{4}{2!}x^2 + \frac{8}{3!}x^3 + \frac{16}{4!}x^4 +...
$$

$$
f(4) = 1 + 8 + 32 + 85,33 + 170,66 + ...
$$

Catatan : fungsi di atas disubstitusikan nilai x = 4 hingga menghasilkan nilai e < 0,001



#### Implementasi Deret Maclaurin

Code program python

```python
import math

x = 4
check = 1
a = 0
b = 1

while check > 0.001 :
    f_x = 0
    f_y = 0
    for i in range(a):
        f_x += (2**i)*x**i/math.factorial(i)

    for j in range(b):
        f_y += (2**j)*x**j/math.factorial(j)

    check = f_y - f_x
    a+=1
    b+=1

    print('\niterasi ke-',a,'error =',check)
    print('hasil perhitungannya',f_y)

```

Hasil run program python

```python
iterasi ke- 1 error = 1.0
hasil perhitungannya 1.0

iterasi ke- 2 error = 8.0
hasil perhitungannya 9.0

iterasi ke- 3 error = 32.0
hasil perhitungannya 41.0

iterasi ke- 4 error = 85.33333333333333
hasil perhitungannya 126.33333333333333

iterasi ke- 5 error = 170.66666666666669
hasil perhitungannya 297.0

iterasi ke- 6 error = 273.0666666666666
hasil perhitungannya 570.0666666666666

iterasi ke- 7 error = 364.08888888888896
hasil perhitungannya 934.1555555555556

iterasi ke- 8 error = 416.1015873015872
hasil perhitungannya 1350.2571428571428

iterasi ke- 9 error = 416.1015873015872
hasil perhitungannya 1766.35873015873

iterasi ke- 10 error = 369.8680776014112
hasil perhitungannya 2136.226807760141

iterasi ke- 11 error = 295.89446208112895
hasil perhitungannya 2432.12126984127

iterasi ke- 12 error = 215.195972422639
hasil perhitungannya 2647.317242263909

iterasi ke- 13 error = 143.46398161509296
hasil perhitungannya 2790.781223879002

iterasi ke- 14 error = 88.28552714774924
hasil perhitungannya 2879.0667510267513

iterasi ke- 15 error = 50.448872655856576
hasil perhitungannya 2929.515623682608

iterasi ke- 16 error = 26.90606541645684
hasil perhitungannya 2956.4216890990647

iterasi ke- 17 error = 13.45303270822842
hasil perhitungannya 2969.874721807293

iterasi ke- 18 error = 6.330838921519444
hasil perhitungannya 2976.2055607288125

iterasi ke- 19 error = 2.8137061873417224
hasil perhitungannya 2979.0192669161543

iterasi ke- 20 error = 1.184718394670199
hasil perhitungannya 2980.2039853108245

iterasi ke- 21 error = 0.47388735786807956
hasil perhitungannya 2980.6778726686925

iterasi ke- 22 error = 0.18052851728316455
hasil perhitungannya 2980.8584011859757

iterasi ke- 23 error = 0.06564673355751438
hasil perhitungannya 2980.924047919533

iterasi ke- 24 error = 0.022833646454728296
hasil perhitungannya 2980.946881565988

iterasi ke- 25 error = 0.0076112154847578495
hasil perhitungannya 2980.9544927814727

iterasi ke- 26 error = 0.0024355889549951826
hasil perhitungannya 2980.9569283704277

iterasi ke- 27 error = 0.0007494119863622473
hasil perhitungannya 2980.957677782414
```

Proses *looping* berhenti pada iterasi ke-27 karena error < 0,001. Kesimpulannya yaitu e^2x dengan x=4 dan ekspansi error < 0,001 berhenti pada iterasi ke-27 dengan nilai 0,0007494119863622473.



# Metode Newton Raphson

Metode Newton Raphson merupakan suatu metode pencarian akar suatu fungsi f(x) dengan pendekatan satu titik, dimana fungsi f(x) mempunyai turunan. Metode Newton Raphson ini menggunakan pendekatan satu titik sebagai titik awal. Semakin dekat titik awal yang dipilih dengan akar sebenarnya, maka akan semakin cepat pula konvergen ke akarnya. Metode Newton Raphson sering konvergen dengan cepat, terutama bila iterasi dimulai cukup dekat dengan akar yang diinginkan. Namun bila iterasi dimulai jauh dari akar yang dicari, metode ini dapat meleset tanpa peringatan. Implementasi metode ini biasanya mendeteksi dan mengatasi kegagalan konvergensi. Jika diketahui fungsi ƒ(x) dan turunannya ƒ'(x), maka rumus dari Newton Rapshon yaitu :
$$
x_{n + 1} = x_n - \frac {f(x_{n})}{f^{1}(x_{n})}
$$

#### Pencarian akar

Langkah-langkah dalam mencari akar dengan menggunakan Metode Newton Raphson adalah sebagai berikut :

1. Memilih X0 / Xn untuk tebakan akar awal
2. Selanjutnya cek F(X0). Jika hasilnya 0 maka proses berhenti, dan jika hasilnya belum 0 maka mencari akar baru lagi. Cara mencari akar baru yaitu dengan :

$$
x_{n + 1} = x_n - \frac {f(x_{n})}{f^{1}(x_{n})}
$$

​      Sedangkan untuk menghitung galat, dengan :
$$
E = \left | \frac{X_{n+1}-X_n}{X_{n+1}} \right |
$$

3. Untuk iterasi kedua gunakan akar baru sebagai akar X0 = Xn+1. Lakukan penghitungan secara terus menerus hingga hasil F(X0) = 0



#### Implementasi Metode Newton Raphson

Code program python

```python
import math
e = 2.71828

def fungsi(x):
    x = float((e**x) - (4*x))
    return x

def fungsiturunan(x):
    x = float((e**x) - (4))
    return x

x = float(input('Masukkan nilai awal = '))
error = float(input('Masukkan nilai error = '))
perulangan = int(input('Masukkan maksimal pengulangan = '))

iterasi = 0
selisih = error+1
while iterasi <= perulangan  and selisih>error :
    iterasi += 1
    f_2 = x - (fungsi(x)/fungsiturunan(x))
    selisih = math.fabs(f_2 - x)
    x = f_2
    print("Iterasi ke = ",iterasi,", x = ",f_2, ", f(",f_2,") = ",fungsi(f_2),", selisih = ",error)
    if iterasi <= perulangan:
        print("Perulangan Mencapai Batas Maksimal dengan hasil = ", f_2)
    else :
        print("Toleransi tidak terpenuhi")
```

Hasil run program python

```python
Masukkan nilai awal = 2
Masukkan nilai error = 0.001
Masukkan maksimal pengulangan = 30
Iterasi ke =  1 , x =  2.180273095450679 , f( 2.180273095450679 ) =  0.1276171155949779 , selisih =  0.001
Perulangan Mencapai Batas Maksimal dengan hasil =  2.180273095450679
Iterasi ke =  2 , x =  2.1539532848570624 , f( 2.1539532848570624 ) =  0.0030383334624808356 , selisih =  0.001
Perulangan Mencapai Batas Maksimal dengan hasil =  2.1539532848570624
Iterasi ke =  3 , x =  2.153295473390226 , f( 2.153295473390226 ) =  1.8681594777802957e-06 , selisih =  0.001
Perulangan Mencapai Batas Maksimal dengan hasil =  2.153295473390226
```

