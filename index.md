# KOMPUTASI NUMERIK

Nama  : Febri Noorman Lazuardi

NIM     : 180411100117

Prodi   : Teknik Informatika

Makul  : Komputasi Numerik A (Mula'ab S.Si., M.Kom.)





## TUGAS 1 (Deret Maclaurin)

##### Pengertian

Deret MacLaurin merupakan suatu fungsi f(x) yang memiliki turunan f'(x), f”(x), f”'(x), dan seterusnya yang kontinyu dalam interval I dan a, x I maka untuk x disekitar a yaitu |x – a| < , f(x) dapat diekspansi kedalam Deret Taylor. Dalam matematika, deret Taylor adalah representasi fungsi matematika sebagai jumlahan tak hingga dari suku-suku yang nilainya dihitung dari turunan fungsi tersebut di suatu titik. Deret ini dapat dianggap sebagai limit polinomial Taylor. Deret Taylor mendapat nama dari matematikawan Inggris yaitu Brook Taylor. Bila deret tersebut terpusat di titik nol, deret tersebut dinamakan sebagai deret Maclaurin, dari nama matematikawan Skotlandia Colin Maclaurin. Sebuah fungsi f(x) yang mempunyai turunan f^1(x), f^2(x), f^3(x), dan seterusnya yang continue dalam interval I dan a, x I maka dapat diekspansi kedalam deret Taylor, yaitu sebagai berikut :
$$
f(x) \approx f(a) + \frac{f^{1}(a)(x-a)}{1!} + \frac{f^{2}(a)(x-a)^{2}}{2!}+ \frac{f^{3}(a)(x-a)^{3}}{3!} + ... \frac{f^{n}(a)(x-a)^{n}}{n!}
$$
Atau bisa dinyatakan :
$$
f(x) = \sum_{ n = 0 } ^ {infinite} \frac{f^n(a)}{n!} (x-a)^n
$$


Deret Maclauren hampir sama dengan deret Taylor tetapi dalam deret maclauren nilai a = 0, sehingga persamaannya yaitu :
$$
f(x) = f(0) + \frac {f'(0)}{1!}x + \frac {f''(0)}{2!}x^2 + \frac {f'''(0)}{3!}x^3 + \frac {f''''(0)}{4!}x^4 + .......
$$
Dalam deret Maclauren yaitu menjumlahkan tiap-tiap suku sampai batas yang ditentukan, sehingga akan menghasilkan nilai yang mendekati nilai sebenarnya. Deret maclauren ini berguna untuk menghitung atau menghampiri nilai fungsi yang dihitung secara manual. Dalam kasus ini akan dihitung nilai e^x secara manual dengan x=4, dan juga diterapkannya dalam bahasa python untuk menghitung e^2x dengan ekspansi sampai error.



##### Perhitungan nilai e^x dengan x=4[¶](https://mdandikuswanto.github.io/Komputasi-Numerik/#perhitungan-nilai-ex-dengan-x4)

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



##### Implementasi Deret Maclaurin

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





## TUGAS 2 (Metode Newton Raphson)

##### Pengertian

Metode Newton Raphson merupakan suatu metode pencarian akar suatu fungsi f(x) dengan pendekatan satu titik, dimana fungsi f(x) mempunyai turunan. Metode Newton Raphson ini menggunakan pendekatan satu titik sebagai titik awal. Semakin dekat titik awal yang dipilih dengan akar sebenarnya, maka akan semakin cepat pula konvergen ke akarnya. Metode Newton Raphson sering konvergen dengan cepat, terutama bila iterasi dimulai cukup dekat dengan akar yang diinginkan. Namun bila iterasi dimulai jauh dari akar yang dicari, metode ini dapat meleset tanpa peringatan. Implementasi metode ini biasanya mendeteksi dan mengatasi kegagalan konvergensi. Jika diketahui fungsi ƒ(x) dan turunannya ƒ'(x), maka rumus dari Newton Rapshon yaitu :
$$
x_{n + 1} = x_n - \frac {f(x_{n})}{f^{1}(x_{n})}
$$



##### Pencarian akar

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



##### Implementasi Metode Newton Raphson

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





## TUGAS 3 (Metode Eliminasi Gauss Jordan, Gauss Jacobi, Dan Gauss Seidel)

### Metode Eliminasi Gauss Jordan

##### Pengertian

Meode Eliminasi Gauss-Jordan adalah pengembangan dari eliminasi Gauss yang hasilnya lebih sederhana lagi. Metode ini merupakan sebuah prosedur untuk pemecahan sistem persamaan linear dengan mengubahnya menjadi bentuk matriks eselon baris tereduksi dengan Operasi Baris Elementer. Caranya adalah dengan meneruskan operasi baris dari eliminasi Gauss sehingga menghasilkan matriks yang Eselon-baris. Ini juga dapat digunakan sebagai salah satu metode penyelesaian persamaan linear dengan menggunakan matriks, yaitu dengan mengubah persamaan linear tersebut ke dalam matriks teraugmentasi dan mengoperasikannya. Setelah menjadi matriks baris, langkah selanjutnya yaitu melakukan substitusi balik untuk mendapatkan nilai dari variabel-variabel tersebut. Metode ini digunakan untuk mencari invers dari sebuah matriks.



##### Code Program (Python)

```python
import numpy as np

#Definisi Matriks
A=[]
B=[]

n=int(input("Masukkan ukuran matriks:"))
for i in range(n):
    baris=[]
    for i in range(n):
        a=int(input("Masukkan nilai:"))
        baris.append(a)
    A.append(baris)
for i in range(n):
    h = int(input("Masukkan hasil:"))
    B.append(h)

Matriks=np.array(A,float)
Hasil=np.array(B,float)

n=len(Matriks)

#Eliminasi Gauss
for k in range(0,n-1):
    for i in range(k+1,n):
        if Matriks[i,k]!=0 :
            lam=Matriks[i,k]/Matriks[k,k]
            Matriks[i,k:n]=Matriks[i,k:n]-(Matriks[k,k:n]*lam)
            Hasil[i]=Hasil[i]-(Hasil[k]*lam)

print("Matriks A : ",'\n',Matriks)

#Subtitution
x=np.zeros(n,float)
for m in range(n-1,-1,-1):
    x[m]=(Hasil[m]-np.dot(Matriks[m, m+1:n], x[m+1:n]))/Matriks[m,m]
    print('Nilai X ',m+1, '=',x[m])
```



##### Hasil Run

```python
Masukkan ukuran matriks:3
Masukkan nilai:2
Masukkan nilai:-2
Masukkan nilai:5
Masukkan nilai:1
Masukkan nilai:5
Masukkan nilai:2
Masukkan nilai:4
Masukkan nilai:5
Masukkan nilai:2
Masukkan hasil:12
Masukkan hasil:3
Masukkan hasil:-4
Matriks A :  
 [[ 2.   -2.    5.  ]
 [ 0.    6.   -0.5 ]
 [ 0.    0.   -7.25]]
Nilai X  3 = 3.2413793103448274
Nilai X  2 = -0.2298850574712644
Nilai X  1 = -2.333333333333332
>>> 
```

Ukuran pada matriks tersebut yaitu 3 variabel, penjelasannya adalah :

|2 -2 5|=|12|

|1 5 2|=| 3 |

|4 5 2| |-4|

Jadi, kesimpulannya adalah pivot yang dibentuk adalah a1.1, a2.2, dan a3.3. Sehingga semua angka yang ada dibawah pivot akan dikonversikan menjadi nol sesuai hasil program dan hasil dari persamaan diatas, menghasilkan x1 = -2.333333333, x2 = -0.22988505 dan x3 = 3.2413793.



### Metode Eliminasi Gauss Jacobi

##### Pengertian

Metode Eliminasi Gauss Jacobi, merupakan sebuah metode tak langsung atau bisa disebut dengan metode iteratif yang melakukan pembaharuan nilai x yang diperoleh tiap iterasi (mirip metode substitusi berurutan). Metode ini hampir sama dengan metode Gauss Seidel, namun perbedaannya adalah tidak melibatkan perhitungan implisit. Metode ini merupakan suatu teknik penyelesaian SPL berukuran n x n, AX = b, secara iteratif. Proses penyelesaian dimulai dengan suatu hampiran awal terhadap penyelesaian, X0, kemudian membentuk suatu serangkaian vector X1, X2, … yang konvergen ke X. Untuk menyelesaikan sistem persamaan linier *AX = b* dengan *A* adalah matriks koefisien *n x n, b* vektor konstan *n x 1*, dan *X* vektor *n x 1* yang perlu dicari adalah :

1. Input : *n*, *A*, *b*, dan Himpunan awal Y = (y1 y2 y3…yn)T, batas toleransi T, dan maksimum iterasi *N.*
2. Output : X = (x1 x2 x3 ..xn)T, atau pesan “ gagal “.



##### Code Program (Python)

```python
from pprint import pprint
from numpy import array, zeros, diag, diagflat, dot
import numpy as np

def jacobi(A,b,N=25,x=None):
    #Membuat iniial guess                                                                                                                                                         
    if x is None:
        x=zeros(len(A[0]))

    #Membuat vektor dari elemen matriks A                                                                                                                                                                                                                                                                                                                 
    D=diag(A)
    R=A-diagflat(D)

    #Iterasi                                                                                                                                                                        
    for i in range(N):
        x=(b-dot(R,x))/D
    return x

Mat1=[]
Mat2=[]

n=int(input("Masukkan ukuran matriks:"))
for i in range(n):
    baris=[]
    for i in range(n):
        a=int(input("Masukkan nilai:"))
        baris.append(a)
    Mat1.append(baris)
for i in range(n):
    h=int(input("Masukkan hasil:"))
    Mat2.append(h)

A=array(Mat1,float)
b=array(Mat2,float)
x=len(Mat1)
guess=np.zeros(x,float)

sol=jacobi(A,b,N=25,x=guess)

print("A:")
pprint(A)

print("b:")
pprint(b)

print("x:")
pprint(sol)
```



##### Hasil run

```python
Masukkan ukuran matriks:3
Masukkan nilai:3
Masukkan nilai:1
Masukkan nilai:-1
Masukkan nilai:4
Masukkan nilai:7
Masukkan nilai:-3
Masukkan nilai:2
Masukkan nilai:-2
Masukkan nilai:5
Masukkan hasil:5
Masukkan hasil:20
Masukkan hasil:10
A:
array([[ 3.,  1., -1.],
       [ 4.,  7., -3.],
       [ 2., -2.,  5.]])
b:
array([ 5., 20., 10.])
x:
array([1.50602413, 3.13253016, 2.6506024 ])
>>> 
```



### Metode Eliminasi Gauss Seidel

##### Pengertian

Metode iterasi Gauss-Seidel merupakan suatu metode yang menggunakan proses iterasi hingga diperoleh nilai-nilai yang berubah-ubah. Metode iterasi Gauss-Seidel dikembangkan dari gagasan metode iterasi pada solusi persamaan tak linier. Metode ini mempunyai kelebihan yaitu digunakan untuk menyelesaikan Sistem Persamaan Linier (SPL) yang berukuran kecil karena metode ini lebih efisien. Dengan metode iterasi Gauss-Seidel, toleransi pembulatan dapat diperkecil karena iterasi dapat diteruskan sampai seteliti mungkin sesuai dengan batas toleransi yang diinginkan. Akan tetapi, metode ini juga mempunyai kekurangan yaitu masalah pivot (titik tengah) yang harus benar–benar diperhatikan, karena penyusunan yang salah akan menyebabkan iterasi menjadi divergen dan tidak diperoleh hasil yang benar. Rumus dari metode eliminasi Gauss-Seidel adalah sebagai berikut :
$$
x_i^{(k)} = 1 b_i - \sum a_{jj} x_{j}^{k} - \sum a_{jj} x_{j}^{k-1}, i=1,2,3,4,....n
$$


##### Code Program (Python)

```python
def seidel(a,x,b): 
    #Mencari panjang matriks  
    n=len(a)               
    for j in range(0,n):        
        d=b[j]                 
        #Menghitung xi, yi, dan zi 
        for i in range(0,n):    
            if(j!=i): 
                d-=a[j][i]*x[i]        
        x[j]=d/a[j][j] #Solusi   
    return x     

m=int(input("Masukkan panjang matriks:"))
a=[]
b=[]
for k in range(m):
    mat1=[]
    for i in range(m):
        l=float(input("Masukkan a"+str(k+1)+","+str(i+1)+":"))
        mat1.append(l)
    h=float(input("Masukkan hasil:"))
    b.append(h)
    a.append(mat1)

n=3                           
x=[0,0,0]                        
print(x) 

for i in range(0,100):          
    x=seidel(a,x,b)
    print(x)
```



##### Hasil Run

```python
Masukkan panjang matriks:3
Masukkan a1,1:4
Masukkan a1,2:-1
Masukkan a1,3:1
Masukkan hasil:7
Masukkan a2,1:4
Masukkan a2,2:-8
Masukkan a2,3:1
Masukkan hasil:-21
Masukkan a3,1:-2
Masukkan a3,2:1
Masukkan a3,3:5
Masukkan hasil:15
[0, 0, 0]
[1.75, 3.5, 3.0]
[1.875, 3.9375, 2.9625]
[1.99375, 3.9921875, 2.9990625]
[1.99828125, 3.9990234375, 2.9995078125]
[1.99987890625, 3.9998779296875, 2.9999759765625003]
[1.99997548828125, 3.9999847412109375, 2.999993247070312]
[1.9999978735351562, 3.9999980926513667, 2.999999530883789]
[1.9999996404418945, 3.9999997615814205, 2.9999999038604734]
[1.9999999644302369, 3.9999999701976776, 2.9999999917325595]
[1.9999999946162794, 3.9999999962747097, 2.99999999859157]
[1.9999999994207849, 3.9999999995343387, 2.9999999998614464]
[1.9999999999182232, 3.999999999941793, 2.999999999978931]
[1.9999999999907154, 3.999999999992724, 2.9999999999977414]
[1.9999999999987457, 3.9999999999990905, 2.9999999999996803]
[1.9999999999998526, 3.9999999999998863, 2.9999999999999636]
[1.9999999999999807, 3.999999999999986, 2.999999999999995]
[1.9999999999999978, 3.9999999999999987, 2.9999999999999996]
[1.9999999999999996, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
[2.0, 4.0, 3.0]
>>> 
```

Dari soal di atas, persamaan yang dipilih adalah 4x - y + z = 7, 4x - 8y + z = - 21, dan -2x + y + 5z = 15. Iterasi yang digunakan sebanyak 100 iterasi sehingga dapat menghasilkan x = 2, y = 4, dan z = 3.





## TUGAS 4 (Metode Recursive Trapezoid)

##### Pengertian

Metode Recursive Trapezoid atau bisa disebut dengan Metode Trapesium/Pengintegralan merupakan sebuah metode integrasi numerik yang didasarkan pada penjumlahan segmen-segmen berbentuk trapesium. Di dalam Kalkulus, integral tentu didefinisikan sebagai sebuah limit jumlah Riemann. Selanjutnya menurut Teorema Dasar Kalkulus integral tersebut dapat dihitung dengan rumus :
$$
\int_{a}^{b} f(x) dx = F(b) - F(a)
$$
Banyak integral tentu yang dapat dihitung dengan rumus tesebut, namun demikian tidak sedikit integral tentu yang tidak dapat dihitung dengan rumus di atas, hal itu dikarenakan integral f(x) tidak mempunyai antiderivatif yang dapat dinyatakan dalam fungsi-fungsi elementer. Dalam hal ini perhitungan yang dapat dilakukan adalah secara numerik. Integrasi numerik merupakan suatu alat utama yang digunakan untuk mendapatkan nilai-nilai hampiran untuk integral tentu yang tidak dapat diselesaikan secara analitik. Dalam mendapatkan nilai-nilai hampiran integral tentu, digunakan banyak metode yakni salah satu metode yang dapat digunakan adalah Aturan Trapesium Rekursif atau *recursive trapezoid*.



##### Aturan Trapesium Rekursif

Permisalan f merupakan suatu fungsi yang terdefinisi pada [a, b] dan h = (b - a). Untuk n = 1, 2, 4, 8,... atau n = 2^0, 2^1, 2^2, 2^3 didefinisikan barisan aturan trapesium
$$
T_0, T_1, T_2, T_3,...,T_K,...
$$
dengan
$$
T_0 = T_1 (f,h) = \frac{h}{2} (f(a)+f(b))
$$
dan
$$
T_k = T_{2{^k}} (f,\frac{h}{2^k}), k = 1,2,3,...
$$
Barisan aturan trapesium tersebut memenuhi hubungan
$$
T_{k+1} = \frac{T_k}{2} + \frac{h}{2^{k+1}} \sum^{2^k}_{j=1} f_{2j-1},
$$


##### Langkah Aturan Trapesium Rekursif

Dalam menghitung hampiran
$$
\int_{a}^{b} f(x) dx
$$
dengan aturan trapesium rekursif, dapat dilakukan dengan langkah-langkah berikut ini :
$$
h = b - a
$$

$$
T_0 = \frac{h}{2} (f(a)+f(b))
$$

$$
T_i = \frac{T_0}{2} + \frac{h}{2}f_1
$$

$$
T_2 = \frac{T_1}{2} + \frac{h}{4}(f_1 + f_3)
$$

$$
T_3 = \frac{T_2}{3} + \frac{h}{8}(f_1 + f_3 + f_5)...dst
$$



##### Code Program (Python)

```python
#definisi fungsi
def fungsi (x):
    y=1/(1+x)
    return y

print("Fungsi yang dipergunakan adalah sebagai berikut:")
print("")
print("\t\t","f(x)=1/(1+x)")
print("")

a=float(input("masukkan batas bawah integral:"))
b=float(input("masukkan batas atas integral:"))
c=int(input("masukkan n:"))
eror=[]
print("")
print("********************Hasil Integrasi********************")
print("iterasi","\t","n","\t\t","Trapezoid")

for iterasi in range (0,c):
    n=2**iterasi
    h=(b-a)/n

    xi=a
    y=0
    for i in range (1,n):
        xi=xi+h
        y += fungsi(xi)
    trap=((h)*(fungsi(a)+(2*y)+fungsi(b)))/2
    eror.append(trap)
    print(iterasi+1,"\t\t",n,"\t\t",trap)
print(eror[iterasi-1])
print(eror[iterasi])
hasil=(eror[iterasi-1]-eror[iterasi])
print(hasil)
print("estimasi error:"+str(hasil))
```



##### Hasil Run

```python
Fungsi yang dipergunakan adalah sebagai berikut:

		 f(x)=1/(1+x)

masukkan batas bawah integral:0
masukkan batas atas integral:1
masukkan n:16

********************Hasil Integrasi********************
iterasi 	 n 		 Trapezoid
1 		 1 		 0.75
2 		 2 		 0.7083333333333333
3 		 4 		 0.6970238095238095
4 		 8 		 0.6941218503718504
5 		 16 		 0.6933912022075267
6 		 32 		 0.6932082082692488
7 		 64 		 0.6931624388834033
8 		 128 		 0.6931509952281075
9 		 256 		 0.6931481342324433
10 		 512 		 0.6931474189784099
11 		 1024 		 0.6931472401645831
12 		 2048 		 0.6931471954611083
13 		 4096 		 0.6931471842852348
14 		 8192 		 0.69314718149127
15 		 16384 		 0.6931471807927745
16 		 32768 		 0.6931471806181497
0.6931471807927745
0.6931471806181497
1.7462475909724162e-10
estimasi error:1.7462475909724162e-10
>>>
```





## TUGAS 5 (Richardson Extrapolation)

##### Pengertian

Richardson Extrapolation atau biasa disebut dengan Ekstrapolasi Richardson merupakan metode yang menggunakan dua perkiraan dari sebuah integral untuk mengkomputasi pendugaan ketiga, yang lebih akurat. Richardson Extrapolation juga bisa diartikan sebagai suatu metode percepatan urutan yang digunakan untuk meningkatkan laju konvergensi suatu urutan. Metode untuk memperoleh rumus hampiran turunan dengan orde yang lebih tinggi dari hampiran dengan orde yang lebih rendah disebut dengan ekstrapolasi. Metode tersebut dikembangkan oleh Lewis Fry Richardson di awal abad 20, sehingga metode tersebut kemudian dikenal dengan ekstrapolasi Richardson.

Richardson Extrapolation termasuk integrai Romberg, yang menerapkan richardson extrapolation pada aturan trapesium, dan algoritma Bulirsch-Stoer untuk menyelesaikan persamaan diferensial biasa. Apabila richardson extrapolation diterapkan secara terus-menerus, maka akan diperoleh nilai integrasi yang semakin lama semakin baik (galatnya semakin kecil). Beda terpusat (*Central Difference*) :
$$
f'(x) = \frac{f(x+h)-f(x-h)}{2h}+O(h^2)
$$
Selanjutnya dari rumus tersebut, maka dapat dibuat suatu formula dengan ditetapkan f(x) dan x tertentu yaitu :
$$
\phi(h)=\frac{f(x+h)-f(x-h)}{2h}
$$

$$
\phi(h)=f'(x)-a_2h^2-a_4h^4-a_6h^6-...
$$

$$
\phi(\frac{h}{2})=f'(x)-a_2(\frac{h}{2})^2-a_4(\frac{h}{2})^4-a_6(\frac{h}{2})^6-...
$$

$$
\phi(h)-4\phi(\frac{h}{2})=-3f'(x)-\frac{3}{4}a_4h^4-\frac{15}{16}a_6h^6-...
$$

Sehingga didapatkan formula yaitu :
$$
\Rightarrow f'(x)=\frac{4}{3}\phi(h/2)-\frac{1}{3}\phi(h) + \omicron (h^4)
$$



##### Pertanyaan

Buatlah program untuk Richardson Extrapolatioin, dengan fungsi :
$$
f(x) = -0.1x^4 - 0.15 x^3 - 0.5x^2 - 0.25x + 1.2
$$
mulai dengan h1 = 0.5 dan h2 = 0.25, hitung estimasi dengan f'(0.5) menggunakan Richardson Extrapolation!



##### Code Program (Python)

```python
from math import *
def nol(n,m):
    Z = []
    for i in range(n):
        Z.append([0]*m)
    return Z
def D(fungsi,a,h):
    return (fungsi(a+h)-fungsi(a-h))/(2*h)
def ekstrapolasiRichardson(fung,a):
    k = 9
    L = nol(k,k)
    for I in range(k):
        L[I][0] = D(fung,a,1/(2**(I+1)))
    for j in range(1,k):
        for i in range(k-j):
            L[i][j] = ((4**(j))*L[i+1][j-1]-L[i][j-1])/(4**(j)-1)
    return L[0][k-1]

print('Diferensiasi numerik fungsi -0.1*x**4 - 0.15*x**3 - 0.5*x**2 - 0.25*x + 1.2 at x = 0.5')
print('Hasil estimasinya yaitu','%04.20f'%ekstrapolasiRichardson(lambda x: -0.1*x**4-0.15*x**3-0.5*x**2-0.25*x+1.2 ,0.5))
```



##### Hasil Run

```python
Diferensiasi numerik fungsi -0.1*x**4 - 0.15*x**3 - 0.5*x**2 - 0.25*x + 1.2 at x = 0.5
Hasil estimasinya yaitu -0.91250000000000530687
>>> 
```





## TUGAS 6 (Persamaan Diferensial Biasa)

##### Pengertian

Persamaan diferensial biasa merupakan persamaan diferensial di mana fungsi yang tidak diketahui (variabel terikat) adalah fungsi dari variabel bebas tunggal. Dalam bentuk paling sederhana fungsi yang tidak diketahui ini adalah fungsi riil atau fungsi kompleks, tetapi secara umum bisa juga berupa fungsi vektor maupun matriks. Lebih jauh lagi, persamaan diferensial biasa digolongkan berdasarkan orde tertinggi dari turunan terhadap variabel terikat yang muncul dalam persamaan tersebut.



##### Macam Persamaan Diferensial Biasa

Ada beberapa macam persamaan diferensial biasa, diantaranya adalah sebagai berikut :

1. Metode Euler. Metode Euler merupakan salah satu dari metode satu langkah yang paling sederhana. Dibanding dengan beberapa metode lainnya, metode ini paling kurang teliti. Namun demikian, metode ini perlu dipelajari mengingat kesederhanaannya dan mudah pemahamannya sehingga memudahkan dalam mempelajari metode lain yang lebih teliti. Metode euler atau disebut juga metode orde pertama karena persamaannya hanya mengambil sampai suku orde pertama saja. Formula Metode Euler :
   $$
   y_{i+1} = y_i + h f(x_i, y_i)
   $$
   Dimana i merupakan tahapan iterasi. Algoritma Metode Euler yaitu :

   a. Menentukan titik awal integrasi x0 dan y0

   b. Menentukan jumlah iterasi n dan step size h yang dipergunakan.

   c. Melakukan integrasi menggunakan persamaan di atas

   Tetapi, sumber berdasarkan pokok terjadinya penyimpangan yang relatif besar pada penerapan metode Euler adalah karena turunan fungsi pada awal interval yang diasumsikan tetap di sepanjang interval. Sehingga dilakukan modifikasi terhadap metode Euler, yaitu menggunakan metode Midpoint dan metode Heun.

2. Metode Midpoint. Metode ini menggunakan metode Euler untuk memperkirakan sebuah nilai y pada titik tengah interval Δx yang ditinjau, yaitu sebesar :
   $$
   y_{i+\frac{1}{2}} = y_i + \frac{h}{2}f(x_i, y_i)
   $$
   Pada persamaan di atas digunakan untuk memperkirakan nilai *slope* pada titik tengah interval, yaitu :
   $$
   y'_{i+\frac{1}{2}} = f(x_{i+\frac{1}{2}},y_{i+\frac{1}{2}})
   $$
   Dianggap dapat mewakili *slope* rata-rata pada keseluruhan interval ΔxΔx. Nilai *slope* pada persamaan di atas akan digunakan untuk mengekstrapolasi linier dari yi ke yi + 1
   $$
   y_{i+1} = y_i + h f(x_{i+\frac{1}{2}},y_{i+\frac{1}{2}})
   $$

3. Metode Heun's Predictor Corrector. Metode ini menyempurnakan metode Euler melalui penentuan dua nilai turuan fungsi sepanjang interval Δx, yakni di awal interval Δx dan di akhir interval Δx. Kedua nilai turunan tersebut selajutnya dirata-ratakan untuk menghasilkan perkiraan nilai *slope* pada keseluruhan interval Δx. Pada metode Euler tadi, nilai slope pada awal interval Δx :
   $$
   y_i = f(x_i,y_i)
   $$
   digunakan untuk mengekstrapolasi linier nilai yi + 1
   $$
   y^0_{i+1} = y_i + h f(x_i,y_i)
   $$
   Persamaan di atas merupakan persamaan prediksi (predictor equation\), ditandai dengan *superscript* 0 untuk membedakannya. Persamaan ini selanjutnya digunakan untuk memperkirakan besarnya *slope* pada akhir interval Δx yang ditinjau, yaitu :
   $$
   y_{i+1} = f(x_{i+1},y^0_{i+1})
   $$
   Kemudian *slope* rata-rata yang dihitung berdasarkan rumus diatas dan rumus Euler sendiri yakni :
   $$
   y' = \frac{f(x_i, y_i)+f(x_{i+1}, y^0_{i+1})}{2}
   $$
   Slope rata-rata pada persamaan diatas selanjutnya digunakan untuk mengekstrapolasi linier dari yi ke yi + 1 menggunakan metode Euler.
   $$
   y^1_{i+1}=y_i+\frac{h}{2}f(x_i,y_i)+f(x_{i+1},y^0_{i+1})
   $$
   Persamaan diatas merupakan persamaan koreksi (corrector equation\). Kesimpulannya adalah Metode Heun's menggunakan pendekatan predictor-corrector, yang secara iteratif dapat dinyatakan sebagai berikut :

   Predictor :
   $$
   y^0_{i+1} = y_i + h f(x_i,y_i)
   $$
   Corrector :
   $$
   y^1_{i+1}=y_i+\frac{h}{2}f(x_i,y_i)+f(x_{i+1},y^0_{i+1})
   $$
   

##### Pertanyaan

Buatlah program untuk menyelesaikan persamaan differensial biasa berikut dengan menggunakan metode Euler :
$$
\frac{dy}{dx} = 1 + x^2, y(1) = -4
$$
untuk menentukan y (1.01), y(1.02), dan y(1.03)



##### Code Program (Python)

```python
print("f(x,y)=1+x^2")
print("yi+1=y1+hf(xi+yi)")
x1=float(input("Masukkan x1="))
x2=float(input("Masukkan x2="))

h=1.01-x1
n=4
xi=-4
hasil=xi
y=0

for i in range(n):
    print("hasil dari y"+str(i)+"="+str(hasil))
    hasil=xi+h*(1+(x1+y)**2)
    y+=h
    xi=hasil
```

Keterangan :

1. Pada bagian awal terdapat variabel x1 adalah x awal dan x2 merupakan x akhir, karena di soal terdapat nx = 3 yaitu x0 = 1, x1 = 1,01, x2 = 1,02, dan x3 = 1,03 maka h = xn - x0/n, hasilnya h = 0.01
2. xi adalah hasil awal yang kemudian akan dimasukkan pada prosess iterasi. Karena di dalam rumus atau Metode Eurel adalah y1 = y0 +h(f(x,y), maka rumus barunya adalah y1 = y0 + h(1+x^2). Variabel y digunakan untuk penambahan nilai x agar selalu bertambah 0.01.
3. Pada baris ke-6 tertulus h=1.01-x1 karena yang dicari f(x,y) nilai x-nya=1.01
4. Pada baris ke-7 jumlah x ada 4 yaitu 1, 1.01, 1.02, dan 1.03