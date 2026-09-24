# <h1 align="center">Laporan Praktikum Modul 1 - Codeblocks IDE & Pengenalan Bahas C++ (Bagian Pertama)</h1>

<p align="center">Assyifa Zahra - 109082500018</p>

## Dasar Teori
C++ adalah salah satu bahasa pemrograman tingkat tinggi yang dikembangkan dari bahasa C oleh Bjarne Stroustrup. Bahasa ini mendukung pemrograman berorientasi objek (*Object-Oriented Programming*). Code::Blocks sendiri merupakan salah satu *Integrated Development Environment* (IDE) gratis yang sering digunakan untuk menulis dan mengkompilasi kode C++[1]. Dalam praktikum ini, pemahaman dasar mengenai struktur penulisan kode, tipe data, serta operator aritmatika menjadi pondasi penting sebelum mempelajari struktur data yang lebih kompleks[2].
## Unguided

### 1. Buatlah program yang menerima input-an dua buah bilangan bertipe float, kemudian memberikan output-an hasil penjumlahan, pengurangan, perkalian, dan pembagian dari dua bilangan tersebut.

```C++
#include <iostream>

using namespace std;

int main() {
    float angka1, angka2;

    cout << "Program Kalkulator Sederhana" << endl;
    cout << "Masukkan angka pertama: ";
    cin >> angka1;
    cout << "Masukkan angka kedua: ";
    cin >> angka2;

    cout << "\n--- Hasil Operasi Aritmatika ---" << endl;
    cout << "Penjumlahan (+) : " << angka1 + angka2 << endl;
    cout << "Pengurangan (-) : " << angka1 - angka2 << endl;
    cout << "Perkalian (*)   : " << angka1 * angka2 << endl;
    
    // Cek biar nggak error kalau dibagi 0
    if (angka2 != 0) {
        cout << "Pembagian (/)   : " << angka1 / angka2 << endl;
    } else {
        cout << "Pembagian (/)   : Error, tidak bisa dibagi dengan nol!" << endl;
    }

    return 0;
}
```

### Output Unguided 1 :

##### Output 1

![Screenshot Output Unguided 1_1](https://raw.githubusercontent.com/chypiez/Struktur-Data---Assyifa-Zahra---109082500196/main/Laprak%201.png)
Program tersebut menerima dua buah bilangan bertipe `float`, kemudian melakukan empat operasi aritmatika yaitu penjumlahan, pengurangan, perkalian, dan pembagian. Hasil dari setiap operasi kemudian ditampilkan menggunakan `cout`.

### 2. Buatlah sebuah program yang menerima masukan angka dan mengeluarkan output nilai angka tersebut dalam bentuk tulisan. Angka yang akan di-input-kan user adalah bilangan bulat positif mulai dari 0 s.d. 100.

Contoh:

```text
79 : tujuh puluh sembilan
```

```C++
#include <iostream>

using namespace std;

string konversiKeHuruf(int n) {
    string satuan[] = {"nol", "satu", "dua", "tiga", "empat", "lima", "enam", "tujuh", "delapan", "sembilan"};
    string belasan[] = {"sepuluh", "sebelas", "dua belas", "tiga belas", "empat belas", "lima belas", "enam belas", "tujuh belas", "delapan belas", "sembilan belas"};

    if (n == 100) {
        return "seratus";
    } else if (n >= 0 && n <= 9) {
        return satuan[n];
    } else if (n >= 10 && n <= 19) {
        return belasan[n - 10];
    } else if (n >= 20 && n <= 99) {
        int pul = n / 10;
        int sis = n % 10;
        if (sis == 0) {
            return satuan[pul] + " puluh";
        } else {
            return satuan[pul] + " puluh " + satuan[sis];
        }
    }
    return "";
}

int main() {
    int inputAngka;
    cout << "Masukkan angka (0 - 100): ";
    cin >> inputAngka;

    if (inputAngka < 0 || inputAngka > 100) {
        cout << "Maaf, angkanya harus dari 0 sampe 100 ya." << endl;
    } else {
        cout << inputAngka << " : " << konversiKeHuruf(inputAngka) << endl;
    }

    return 0;
}
```

### Output Unguided 2 :

##### Output 1

![Screenshot Output Unguided 2_1](https://raw.githubusercontent.com/chypiez/Struktur-Data---Assyifa-Zahra---109082500196/main/Laprak%202.png)
Program tersebut menerima input berupa bilangan bulat positif dari 0 sampai 100, kemudian menampilkan angka tersebut dalam bentuk tulisan bahasa Indonesia.

### 3. Buatlah program yang dapat memberikan input dan output seperti berikut.

Contoh input:

```text
3
```

Contoh output:

```text
3 2 1 * 1 2 3
  2 1 * 1 2
    1 * 1
      *
```

```C++
#include <iostream>

using namespace std;

int main() {
    int n;
    cout << "Masukkan jumlah angka: ";
    cin >> n;

    // Bagian atas sampai pola mengecil
    for (int i = n; i >= 1; i--) {
        for (int j = i; j >= 1; j--) {
            cout << j << " ";
        }
        cout << "* ";
        for (int j = 1; j <= i; j++) {
            cout << j << " ";
        }
        cout << endl;
    }

    // Bagian titik tengah/bawah
    cout << "*" << endl;

    return 0;
}
```

### Output Unguided 3 :

##### Output 1

![Screenshot Output Unguided 3_1](https://raw.githubusercontent.com/chypiez/Struktur-Data---Assyifa-Zahra---109082500196/main/Laprak%203.png)
Program tersebut menerima sebuah angka sebagai input, kemudian menghasilkan pola berbentuk cermin (_mirror_). Setiap baris menampilkan angka secara menurun dari angka input sampai `1`, kemudian tanda `*`, dan angka kembali secara menaik.

## Kesimpulan

Dari praktikum modul pertama ini, dapat disimpulkan bahwa bahasa C++ memiliki struktur dasar yang terorganisir dengan baik melalui fungsi main dan pustaka standar iostream. Penggunaan tipe data, operator, percabangan, serta perulangan sangat esensial dalam membangun logika pemrograman. Pemahaman ini menjadi fondasi awal yang penting dalam mempelajari struktur data lanjutan seperti linked list, stack, dan queue.
## Referensi

[1] Triase. (2020). Diktat Edisi Revisi : STRUKTUR DATA. Medan: UNIVERSTAS ISLAM NEGERI SUMATERA UTARA MEDAN.


[2] Indahyati, Uce., Rahmawati Yunianita. (2020). "BUKU AJAR ALGORITMA DAN PEMROGRAMAN DALAM BAHASA C++". Sidoarjo: Umsida Press. Diakses pada 10 Maret 2024 melalui https://doi.org/10.21070/2020/978-623-6833-67-4.