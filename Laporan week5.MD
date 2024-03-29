# Laporan Praktikum WEEK 5

NAMA : JEIN ANANDA

NIM : 10221031 

## Soal

1. (**10 poin**) Ceritakan dalam 200 kata tentang hal yang telah kalian 
   pelajari di sesi praktikum ini.

2. (**90 poin**) Dari contoh di bagian perulangan, buatlah program JavaScript
   untuk mencetak gambar kartu berikut:
   
   - Kartu wajik dengan ukuran 1
   ```
   #---#
   | * |
   #---#
   ```

   - Kartu wajik dengan ukuran 2
   ```
   #-----#
   |  *  |
   | *** |
   |  *  |
   #-----#
   ```

   - Kartu wajik dengan ukuran 3
   ```
   #-------#
   |   *   |
   |  ***  |
   | ***** |
   |  ***  |
   |   *   |
   #-------#
   ```

   - Kartu wajik dengan ukuran 4 
   ```
   #---------#
   |    *    |
   |   ***   |
   |  *****  |
   | ******* |
   |  *****  |
   |   ***   |
   |    *    |
   #---------#
   ```

   Petunjuk: 
   - Gunakan *package* `prompt-sync` sehingga *user* dapat memberikan input 
     ukuran kartu yang ingin ia tampilkan (batasi sampai ukuran 6).
   - Program tidak perlu terlalu rumit, cukup menggunakan pemahaman yang telah
     kalian dapatkan selama minggu ke-01 hingga minggu ke-05.


### Jawaban

 1. Pernyataan atau statement dalam JavaScript adalah suatu kalimat atau perintah untuk berkomunikasi dengan JavaScript yang dipisahkan oleh tanda titik koma. Ada dua jenis statement dalam JavaScript, yaitu expression statement dan declaration statement. Expression statement merupakan ekspresi yang dapat dijalankan tanpa tambahan ekspresi lain dan memiliki side-effect, seperti assignment, pemanggilan fungsi, dan compound operator. Sementara declaration statement meliputi deklarasi variabel baru dan definisi fungsi baru.

Program JavaScript hanyalah kumpulan berbagai statements yang dijalankan dengan urutan tertentu. Urutan ini dapat dikendalikan dengan statement khusus yang disebut control structures. Control structures ini merupakan dasar dari pemrograman terstruktur dan memberikan struktur penyusunan statements sehingga membentuk struktur program yang jelas, ringkas, dan efisien.

Pada kategori di atas, control structures bisa diikutsertakan apabila dianggap sebagai statements khusus. Contohnya adalah pengkondisian (conditional) yang terdiri dari if, if-else, dan else-if. Ada pula statement block, yaitu pengelompokan beberapa expression statements menjadi satu kesatuan. Ada pula empty statement yang hanya terdiri dari satu karakter titik koma, salah satu penggunaannya adalah dalam kasus perulangan.


2. 
```js
const ps = require("prompt-sync");
const prompt = ps();

function printDiamond(n) {
    n = n + (n-1)
    let diamond = "";
    for (let i = 1; i <= n; i += 2) {
      let spaces = " ".repeat((n - i) / 2);
      diamond += `|${spaces}${"*".repeat(i)}${spaces}|\n`;
    }
    for (let i = n - 2; i >= 1; i -= 2) {
      let spaces = " ".repeat((n - i) / 2);
      diamond += `|${spaces}${"*".repeat(i)}${spaces}|\n`;
    }
  
    const border = `#${"-".repeat(n)}#`;
  
    console.log(border);
    console.log(diamond.trim());
    console.log(border);
  }
  
  while (true) {
    const input = prompt('Masukkan lebar diamond 1-6: ');
    const num = parseInt(input);
  
    if (isNaN(num) || num < 1 || num > 6) {
      console.error('Invalid input. Tolong masukkan angka antara 1-6');
      continue;
    }
    
    printDiamond(num);
    //break;
  }
  ```