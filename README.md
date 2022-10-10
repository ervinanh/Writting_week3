# **Writing Test - Week 3**

## Array & Array Multidimensional

### Nama : Ervina Nurfa Hidayah
### Learning track : back-end


## Definisi Array

Array adalah tipe data list order atau tipe variabel yang dapat menampung berbagai jenis data dengan tipe yang bermacam-macam, dengan jumlah yang tidak terbatas. Array di JavaScript memiliki ciri khas yaitu data yang ditampung dibungkus dengan sepasang kurung siku [ ]. Atau juga dapat di sebut dnegan Mengorganisasi data dan menyimpan data adalah core concept dari programming.

Array pada JavaScript dapat menyimpan fungsi, objek, dan array lainnya. Array memiliki berbagai metode dan properti yang berguna. Berikut syntax array :

```h
let namaArray = [ nilai1, nilai2, nilai3, ...];
```

Contoh penggunaan array :
```h
// Menyimpan data di variabel satu-per-satu
let mahasiswa1 = 'Nurul';
let mahasiswa2 = 'Ervina';
let mahasiswa3 = 'Puput';

// Menyimpan lebih dari satu data dalam satu array
let mahasiswa = ['Nurul', 'Ervina', 'Puput'];
```


### Mendeklarasikan Array

- #### MenggunakanKata Kunci `new`
    ```h
    let namaArray = new Array(element1, element2, element3);
    ```

    Contoh :
    ```h
    let hewan = new animal('Anjing', 'Semut', 'Belalang');

    let data = new datas("Barang", 30000, true); // Tipe data di array boleh berbeda
    ```
    > Note: Namun penulisan ini tidak direkomendasikan


### Nomor Index dan Jumlah Data Array

Setiap data di array memiliki nomor index. Nomor index berguna untuk mengakses data suatu array di posisi tertentu. Nomor index di array selalu dimulai dari angka nol (0). Setiap array pasti memiliki jumlah data yang ditampungnya, atau disebut dengan Array Length dengan syntax `array.length`.

Gambar di bawah ini adalah ilustrasi nomor index di array:

![array](img/array-index.png)


### Mengakses Data/Element di Dalam Array

- #### Mengakses Element Tunggal
    Syntax yang digunakan :
    ```h
    namaArray[nomorIndex]
    ```

    Contoh :
    ```h
    let namaHewan = ["kucing", "kelinci", "burung", "anjing"];

    console.log(namaHewan[0]); // Output: kucing
    console.log(namaHewan[1]); // Output: kelinci
    console.log(namaHewan[2]); // Output: burung
    console.log(namaHewan[3]); // Output: anjing
    ```
- #### Mengakses Seluruh Element Array
    Jika kita ingin mengakses seluruh data yang berada di dalam suatu array, maka kita cukup panggil nama dari array tersebut.
    ```h
    let olahraga = ["Berenang", "Lari", "Bela Diri"];

    console.log(olahraga); // Output: ["Berenang", "Lari", "Bela Diri"]
    ```

### Mengubah Data/Element pada Array

Data/element dari suatu array bisa kita ubah dengan syntax seperti ini:
```h
namaArray[nomorIndex] = nilaiBaru;
```

Contoh :
```h
let namaBuah = ["Mangga", "Apel", "Jeruk"];

namaBuah[1] = "Semangka";

console.log(namaBuah); // Output: ["Mangga", "Semangka", "Jeruk"]
```

### Const in array

Jika menggunakan let, kita dapat mengubah array  dengan array baru dan konten nilai yang ada di dalam array dengan nilai lain.

Const tidak bisa melakukan update data. Namun pada Array kita dapat melakukan update konten nilai di dalam array (mutable).

Yang tidak bisa adalah mengubah array dengan array yang baru jika menggunakan const.

Contoh :
```h
const cars = ["tesla", "honda", "toyota", "BMW"]
cars = ["nissan"]
console.log(cars);
// Output: Error. Tidak bisa update array baru
```
```h
const cars = ["tesla", "honda", "toyota", "BMW"]
cars[2] = ["nissan"]
console.log(cars);
// Output: ["tesla", "honda", "nissan", "BMW"]
```


### Array Properties

**array.length** adalah salah satu property dari array. Array memiliki 5 properti yang sering digunakan yaitu `constructor`, `length`, `index`, `input`, dan `prototype`.

**Properties** adalah fitur yang sudah disediakan oleh Javascript untuk memudahkan developer.
- `.length` akan mengembalikan nilai dari jumlah panjang data suatu array.
    ```h
    const cars = ["tesla", "honda", "toyota", "BMW"]
    console.log(cars.length);
    // Output: 4
    ``` 


### Array Method

Array memiliki method atau biasa disebut built-in methods. Artinya Javascript sudah memudahkan kita dengan menyediakan function/method umum yang bisa kita gunakan.


### Contoh Array Built-in Methods

- Method `.push()`, menambahkan data/value ke dalam array di index terakhir.
    ```h
    let buah = ["jeruk", "anggur", "durian", "mangga"]
    buah.push("pisang")
    console.log(buah);
    // Output: ["jeruk", "anggur", "durian", "mangga", "pisang"]
    ```
- Method `.unshift()`, menambahkan data/value ke dalam array di index pertama.

- Method `.pop()`, menghapus data/value array di index terakhir.

- Method `.shift()`, menghapus data/value array di index pertama.

- Method `.splice()`, digunakan untuk menambah, menghapus dan mengganti data array yang diinginkan.
    
    Syntax :
    > `.splice(start, deleteCount, item1)`
    
    - start, dimulai pada index keberapa perubahan data array yg akan dilakukan.
    - deleteCount (optional), berapa data/value yang akan dihapus.
    - item1,...,item2(optional), akan diganti/disisipkan dengan data/value apa dalam index tersebut.
  
    ```h
    let buah = ["jeruk", "anggur", "durian", "mangga"]
    buah.splice(2, 0, "semangka")
    console.log(buah); 
    // Output: ["jeruk", "anggur", "semangka", "durian", "mangga"]
    ```
- Method `.sort()`, adalah method untuk mengurutkan secara Ascending atau Descending Alphanumeric

### Looping pada Array

Array memiliki built in methods untuk melakukan looping yaitu **map()** dan **forEach()**

- `.forEach()`, adalah method untuk melakukan looping pada setiap elemen array. Penulisannya menggunakan callback `.forEach((item) => {})`
    ```h
    let zodiak = ["taurus", "aquarius", "leo", "virgo"]

    zodiak.forEach((item ) => {
    console.log(item);
    })
    ```
- `.map()`, melakukan perulangan/looping dengan membuat array baru.

Perbedaannya dari keduanya adalah `.forEach` tidak dapat membuat Array baru dari hasil operasi yang ada dalam looping.

Jadi, gunakan `.forEach()` jika hanya memerlukan looping untuk menampilkan saja atau menyimpan ke database. Gunakan `.map()` jika akan melakukan operasi pada array seperti yang dapat mengubah nilai array sebelumnya.


### Array Multidimensional

Multidimensional Array bisa dianalogikan dengan array of array, yaitu terdapat array didalam array.

Sama seperti array satu dimensi, multidimensional array juga dapat menggunakan Property dan Method built-in Array. Cara memanggilnya menggunakan baris dan kolom.

Contoh dan hasil :
```h
let arrMulti = [
    ["nama", "suri"],
    ["umur", 25],
    ["kelas", "JS"]
]
console.log(arrMulti);
console.log(arrMulti[0][1]);
console.log(arrMulti[2][1]);
```

## Javascript Object


### Definisi

Dalam kehidupan nyata, kita sebenarnya sudah sering menjumpai object. Entah itu benda mati atau benda hidup. Semuanya adalah object. 

Object didunia nyata dapat kita modelkan didalam programming. Jadi pada programming, object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method).

Properti adalah data lengkap dari sebuah object. Method adalah action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.

Tipe data yang sudah kita pelajari:

- number
- string
- boolean
- null
- undefined
- array
- object

### Membuat/Mendeklarasikan Sebuah Object

Sama seperti tipe data sebelumnya. Object dapat diassign kedalam sebuah variabel. Dan sama seperti array, didalam object kita dapat menyimpan properti dengan tipe data apapun.

- Menggunakan Object Literal
    
    Syntax :
    ```h
    let nama_obj = {
        key1: "value",
        key2: "value2",
    }
    ```

    Contoh dan hasil :
    ```h
    let mahasiswa = {
        nama: "Nurul",
        umur: 21,
        hobi: "Makan",
        "nomor handphone": 0888888 
    }

    console.log(mahasiswa);
    ```

- Menggunakan Kata Kunci `new`

    Syntax :
    ```h
    let namaObjek = new Object();

    namaObjek.namaProperti1 = nilai1;
    namaObjek.namaProperti2 = nilai2;
    ```

    Contoh :
    ```
    let orang = new Object();

    orang.nama = 'aceng';
    orang.umur = 24;
    orang.hobi = 'renang'; 
    ```

### Mengakses Object dan Property Object

Jika kita ingin menggunakan nilai yang terdapat di dalam properti suatu objek, maka kita harus mengakses properti objek tersebut.

Ada 2 cara untuk mengaksesnya :

1. Dot Notation

    Syntax :
    ```h
    let objek = {
    namaProperti: nilaiProperti
    };

    // Dot Notation
    objek.namaProperti // Output: nilaiProperti
    ```

    Contoh dan hasil :
    ```h
    let mahasiswa = {
        nama: "Nurul",
        umur: 21,
        hobi: "Makan",
        "nomor handphone": 0888888 
    }

    console.log(mahasiswa) // Menampilkan isi keseluruhan object
    console.log(mahasiswa.nama); // Menampilkan salah satu property dari object
    console.log(mahasiswa.umur); // Menampilkan salah satu property dari object
    console.log(mahasiswa.hobi); // Menampilkan salah satu property dari object
    ```

2. Bracket Notation

    Syntax :
    ```h
    let objek = {
        namaProperti: nilaiProperti
    };

    // Bracket Notation
    objek["namaProperti"] // Output: nilaiProperti

    // bisa juga menggunakan single quote
    objek['namaProperti'] // Output: nilaiProperti
    ```

    console.log(siswa1); // Menampilkan isi keseluruhan object
    console.log(siswa1["nama"]); // Menampilkan salah satu property dari object
    console.log(siswa1["hobi"]); // Menampilkan salah satu property dari object
    console.log(siswa1["nomor handphone"]); // Menampilkan salah satu property dari object
    ```

3. Tambahan, Menggunakan Variabel

### Update Object

Kita dapat melakukan update pada variabel dengan tipe data Object. Object dapat mengupdate value dari key yang sudah tersedia. Object dapat menambahkan key dan value baru.

- Menambah Property Baru

- Mengganti Value Property

  - Menggunakan Dot Notation

  - Menggunakan Bracket Notation

  - Mengganti Value Dalam Const

    Kita bisa mengganti/mengubah value object const selama tidak mengubah keseluruhan object tersebut.

    Syntax yang tidak bisa dilakukan dalam variabel const :
  
  > Jadi jika membutuhkan untuk update seluruh data object gunakan ‘let’ pada saat deklarasi variabel.


### Delete Object Property

Kita dapat menghapus properti dari object menggunakan delete operator.

Contoh dan hasil :
```h
let hewan = {
    nama: "ayam",
    kaki: 2,
    warna: "hitam"
    suara: "kokok"
}
console.log(hewan);

delete hewan.kaki
delete hewan.warna
console.log(hewan);
```

### Method

Jika value yang kita masukkan pada property berupa function. Maka itu disebut method.

Contoh dan hasil :
```h
const greeting = {
    welcome: function() {
        return "Halo, selamat datang di indomaret selamat berbelanja"
    },
    afterPay: function() {
        return "Terimakasih sudah membeli produk kami!"
    }
}
console.log(greeting.welcome());
console.log(greeting.afterPay());
```

- Build-in Method Object 
  
  Contoh dan hasil :
  ```h
  let s,mahaiswa = {
    nama: "Nurul",
    umur: 21,
    hobi: "Makan"
  }
  console.log(mahasiswa);

  // Merubah object menjadi array
  console.log(Object.keys(mahasiswa));

  // Memanggil dari value
  console.log(Object.values(mahasiswa));
  ```

### Nested Object

Pada real application nanti kalian pasti menemukan data object yang kompleks. Object yang berasal dari turunan object lainnya.

Contoh dan hasil :
```h
let buku = {
    judul: "Self Healing",
    tahun: 2021,
    penulis: {
        penulis1: {
            nama: "Uwi",
            umur: 20,
            kota: "kabupaten bandung"
        },
        penulis2: {
            nama: "Fika",
            umur: 21,
            kota: "Bandung"
        }
    }
}
console.log(buku);

// Memanggil property
console.log(buku.penulis.penulis1.nama);
console.log(buku.penulis.penulis1.kota);
console.log(buku.penulis.penulis2.nama);
console.log(buku.penulis.penulis2.kota);
```

### Looping Object

Jika kita ingin menampilkan seluruh object properti. Kita bisa menggunakan looping dan tidak perlu mengakses secara manual memanggil setiap propertinya.

Looping yang digunakan adalah `for..in`.
```h
let mahasiswa = {
    nama: "Dinda",
    umur: 25,
    kota: "Medan"
}
console.log(mahasiswa);

for(let key in mahasiswa) {
    console.log(mahasiswa[key]); 
}
```
Contoh case lain menggunakan nested loop :
```h
let buku = {
    judul: "Self Healing",
    tahun: 2021,
    penulis: {
        penulis1: {
            nama: "Uwi",
            umur: 20,
            kota: "kabupaten bandung"
        },
        penulis2: {
            nama: "Fika",
            umur: 21,
            kota: "Bandung"
        }
    }
}
console.log(buku);

for(let key in buku.penulis.penulis1){
    console.log(buku.penulis.penulis1[key], "(ini dari nested)");
}
```

### Array of Object

Apakah object hanya menyimpan 1 data? Tidak. Object sama seperti Array yang bisa menyimpan banyak data. Kita dapat menggunakan `array of object` untuk data yang lebih dari satu.

Contoh dan hasil :
```h
let users = [
    {
        nama: "nurul",
        umur: 21,
        alamat: "banjaran"
    },
    {
        nama: "sazkiya",
        umur: 21,
        alamat: "arjasari"
    },
    {
        nama: "davina",
        umur: 21,
        alamat: "kopo"
    }
]
console.log(users);

// cara memanggil / mengaksesnya
let data = users.map((el) => {
    console.log(el.nama);
    
// Menambahkan property baru kedalam array tersebut
    el.status = "aktif"
    return el
})
console.log(data);

// jika ingin mengambil salah satu data
console.log(users[0].nama);
```

## Javascript Modules


### Definisi

Modules adalah **reusable code**  yang dapat di **export** dari suatu file javascript dan di **import** ke file javascript yang lain. **Resusable code** disini adalah data yang dapat digunakan berulang kali. 

Atau pengertian lainnnya adalah cara untuk memisahkan code ke file yang berbeda. 

Kita bisa melakukan **export** data apapun seperti :
- string
- number
- array
- object
- class
- function/method.


### Mengapa menggunakan module?

1. Maintainability
   - Module yang dirancang dengan baik bisa mengurangi ketergantungan pada bagian tertentu pada kode kita. Merubah satu module lebih mudah ketika module dipisahkan dari potongan kode lainnya daripada merubah dalam satu file yang terdiri dari ratusan ribu kode.

   - Mempermudah jika kita ingin menambahkan, menghapus, dan merubah kode kita karena tidak mempengaruhi keseluruhan aplikasi kita.

2. Penggunaan Nama Variabel
   - Module memudahkan kita untuk memberikan alias nama variabel yang di-import. Sehingga kita tidak mengalami kesulitan untuk mengganti nama variabel jika nama variabel yang kita import sama dengan nama variabel dalam file yang menggunakan module tersebut.

3. Reusable Code 
   - Kita sangat sering menggunakan kode yang sama baik itu variabel atau function dari satu file ke file yang lain. Padahal jika kita ingin menjadi programmer yang baik, kita harus menggunakan prinsip DRY (Don't Repeat Yourself) pada kode kita. Untuk itu sebaiknya jika kita akan membuat kode yang nantinya akan dapat digunakan pada file yang lain, maka kita perlu membuat sebagai module.

### Membuat Modules

Menggunakan syntax dari versi JavaScript ES6 seperti pada kelas JavaScript Dasar. Cukup menambahkan **attribute type** pada tag **cript** kemudian isi nilainya dengan **module**. Sehingga menjadi seperti ini :
```h
<script type="module" src="index.js"></script>
```

Saat menjalankan module, kita `tidak bisa` menggunakan url local komputer kita di browser. Harus menggunakan `static-server`. Kita bisa menggunakan extensions `Live Server` pada `Visual Studio Code`.

### Export & Import

Module pada file JavaScript membutuhkan penghubung antar satu file dengan file yang lain. Untuk bisa menghubungkan file antar JavaScript kita bisa menggunakan export dan import sehingga memungkinkan untuk saling menggunakan kode antar module.

- #### Export

    _Export_ digunakan untuk meng-_export_ variabel pada file JavaScript. Variabel yang di _export_ dapat berisi data seperti _string, object, array_, hingga _function_. Hal ini dilakukan agar file JavaScript tersebut dapat dijadikan sebuah module, sehingga variabel yang telah di-_export_ dapat digunakan pada file JavaScript lain dengan menggunakan _import_.

    Penggunaan _export_ diawali dengan kata kunci **export**kemudian diikuti oleh nama variabel yang ingin di-_export_ atau bisa digunakan di akhir kode kita, dengan nama variabel yang ingin di _export_.

    Kita tidak bisa langsung meng-_export_ data tanpa disimpan ke dalam variabel terlebih dahulu.

    Contoh :
    ```h
    // export string
    export let name = "Nurul"

    // export array
    export let motor = [
        "suzuki",
        "yamaha", 
        "honda"
        ]

    // export function
    export function sayHello() {
        console.log("hallooo");
    }
    ```

    ```h
    let name = "Deva"
    let motor = ["suzuki", "yamaha", "honda"]
    let smartPhone = ["samsung", "oppo", "iphone", "nokia"]

    function sayHello() {
        console.log("hallooo");
    }

    // Mengexport sekaligus 
    export { name, motor, samrtPhone, sayHello }
    ```

- #### Import
  
    _Import_ diibaratkan sebagai pasangan dari _export_. Jadi _import_ digunakan untuk menggunakan variabel yang sudah di-_export_ dari module lainnya.

    Contoh :
    ```h
    import { name, motor, smartPhone, sayHello } from "./uwi.js"
    ```

- #### Export Import As
  
    Saat melakukan _export_ & _import_, kita bisa memberikan alias pada nama variabel, function dan data lainnya menggunakan keyword `"as"`.
    ```h
    // export
    export { smartPhone as smartPhoneJepang }

    // import
    import { motor as motorUwi } from "./uwi.js"
    ```

- #### Export default

  **export default** digunakan apabila, kode yang kita _export_ akan bersifat lebih spesial pada module tersebut. Karena spesial, berarti dalam satu module hanya boleh terdapat satu **export default**.

    Biasanya `export default` digunakan untuk membuat salah satu variabel menjadi data utama yang akan di-_export_ pada sebuah module. `export default` juga bisa digunakan jika hanya ada satu variabel pada suatu module.

    Penggunaannya sama seperti _export_ biasa, kamu cukup menambahkan kata kunci `default` setelah `export`.
    ```h
## Javascript Recursive

### Definisi dan Ciri

_Recursive/rekursif_ adalah suatu teknik pemrograman yang menggunakan **function** atau **fungsi**. Sederhananya adalah **fungsi** yang memanggil **fungsi** tersebut atau dirinya sendiri, seolah-olah terjadi suatu perulangan. Proses pemanggilan inilah yang disebut sebagai _recursion (rekursi)_ dan akan terus dilakukan sampai pada kondisi yang sudah ditentukan.

Ciri dari _recursive/rekursif_ :
- Fungsi _rekursif_ selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti, yang berarti algoritma kita tidak benar.
- Fungsi _rekursif_ selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. Hal ini penting diingat, karena tujuan utama dari _rekursif_ ialah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.

### Penggunaan Recursive/Rekursif

_Rekursif_ sangat cocok untuk menyelesaikan permasalahan pada matematika, fisika, kimia, dan yang berhubungan dengan operasi perhitungan lainnya.

Dengan menggunakan _rekursif_, memungkinkan kamu untuk dapat merancang suatu logika penyelesaian menjadi lebih baik dan mudah dibaca. Namun dari kelebihannya itu, _rekursif_ menggunakan banyak memori sehingga membuat aplikasi menjadi lambat jika data yang diuji sangat banyak.

Ada 3 hal yang perlu diperhatikan untuk memutuskan kapan menggunakan _rekursif_ dan kapan menggunakan _iteratif_:

1. Jika fokus kamu adalah kecepatan pada aplikasi dan menghemat memori, kamu harus menggunakan _iteratif_.
2. Jika data yang diuji tidak banyak, kamu dapat menggunakan _rekursif_.
3. Beberapa algoritma secara natural lebih cocok menggunakan _rekursif_.

Fokus dari teknik ini adalah memudahkan kamu memecahkan suatu permasalahan besar menjadi bagian-bagian kecil.

### Membuat Recursive/Rekursif

_Rekursif_ adalah pemanggilan fungsi yang berulang. Function yang menerapkan cara _rekursif_ disebut juga dengan recursive function. Jika _recursive function_ tersebut memanggil dirinya sendiri, akan terjadi _infinity recursion_ (rekursi tak hingga). Maka dari itu ada beberapa hal yang harus diperhatikan dalam membuat _recursive function_.

Algoritma _rekursif_ mempunyai 2 komponen utama, yaitu:

1. *Base Case* (titik paling kecil/berhenti)
    
    Kasus dasar untuk menyelesaikan permasalahan. Base case akan dikunjungi jika rekursi berakhir (kondisi untuk berhenti terpenuhi), serta mengembalikan nilai tanpa melakukan rekursi kembali.

2. *Recursion Call* (titik dia memanggil diri dia sendiri)

    Permasalahan yang ada tentunya akan diperkecil dengan melakukan pemanggilan function itu sendiri (recursion call). Permasalahan dapat diperkecil dengan mengurangi atau memecahkan data input pada setiap pemanggilannya hingga mencapai base case.

Syntax :
```h
function namaFuncRekursif() {
  if (condition) {
    // Base case
  } else {
    // Recursion call
    namaFuncRekursif();
  }
}
```

## Javascript Asynchronous 

**single-thread language_ atau _synchronous** yang artinya hanya dapat mengeksekusi satu perintah pada satu waktu dan harus menunggu satu perintah tersebut selesai sebelum melanjutkan perintah selanjutnya.

Untuk bisa mengeksekusi urutan perintah dari kode yang kita tulis ada 2 istilah yang digunakan pada JavaScript yaitu _synchronous_ dan _asynchronous_.

### Syncrhonous

**Synchronous** adalah saat kita mengeksekusi perintah satu persatu dan berurutan. Analoginya seperti kita sedang mengantri di kasir atau loket. Ketika ada 1 perintah masuk maka dia akan dieksekusi terlebih dahulu. Jika perintah belum selesai dan sudah ada perintah baru maka perintah kedua (yang baru) akan mengantri sampai perintah 1 selesai. Proses seperti ini disebut _**blocking**_ dan membuat perintah kita tereksekusi dengan lambat.

Kode di atas bersifat _synchronous_ yaitu kode dijalankan baris per baris. Maka output kode di atas tereksekusi sesuai urutan perintahnya.

Salah satu konsep lain di pemrograman adalah kebalikan dari synchronous yaitu _asynchronous_.

### Asyncrhonous

_Asynchronous_ yang biasa dikenal juga dengan sebutan **non-blocking** mengizinkan komputer kita untuk memproses perintah lain sambil menunggu suatu proses lain yang sedang berlangsung. Ini artinya kita bisa melakukan lebih dari 1 proses sekaligus (_multi-thread_). Eksekusi perintah dengan _asynchronous_ tidak akan melakukan **blocking** atau menunggu perintah sebelumnya selesai. Jadi sambil menunggu kita bisa mengeksekusi perintah lain.

Dalam proses _asynchronous_ terdapat 3 kunci utama :
1. Callback
2. Promise
3. async-await

### Menjalankan Asynchronous pada JavaScript

Jika JavaScript secara default bersifat **synchronous**, maka bagaimana jika ingin menerapkan proses **asynchronous** ? Ada beberapa cara untuk membuat proses **asynchronous**. Contohnya seperti 2 cara ini :

1. `setTimeout(function, milliseconds)` digunakan untuk simulasi pemanggilan kembali proses asynchronous yang sedang/sudah selesai dijalankan. Pemanggilan hanya dilakukan 1 kali.
2. `setInterval(function, milliseconds)` digunakan untuk simulasi pemanggilan proses asynchronous yang sedang/sudah dijalankan dalam interval waktu tertentu. Pemanggilan dilakukan berkali-kali sesuai interval waktu yang ditentukan.

### Callback

**Callback** adalah sebuah _function_, namun bedanya dengan _function_ pada umumnya adalah pada cara eksekusinya. Jika _function_ pada umumnya dieksekusi secara langsung, sedangkan _callback_ dieksekusi di dalam _function_ lain melalui parameter.

Kita akan coba memperbaiki proses _asynchronous_ sebelumnya dengan memastikan output proses1, proses2, dan proses3 sesuai urutan dengan menggunakan _callback_.

### Promise

**Promise** sesuai dengan artinya adalah janji. Seperti ketika kita berjanji, jika apa yang kita janjikan bisa kita lakukan maka kita harus melakukannya, jika janjinya ada halangan maka kita tidak bisa melakukannya atau jika janji tersebut belum pada waktunya kita juga harus menunggunya.

Konsep _promise_ hadir untuk memecahkan masalah yang bertele-tele dengan _callback_, semakin banyak kita menggunakan _callback_ untuk proses _asynchronous_ semakin kompleks dan sulit kode kita untuk dibaca dan dipelihara. Kita juga akan sering menghadapi _callback_ di dalam _callback_ dan seterusnya. Masalah seperti ini disebut dengan _Callback Hell_.

Dalam _promise_ kita akan mengenal beberapa status dalam _promise_ :

- **Pending / tertunda** = Jika kita belum melewati batas waktu dilaksanakan dan belum mengetahui janji tersebut bisa ditepati atau tidak. Atau jika data sedang diproses.
- **Fulfilled / terpenuhi** = Jika janji berhasil dipenuhi sebelum batas waktu yang ditentukan. Atau jika data telah berhasil didapatkan.
- **Rejected / gagal** = Jika janji gagal ditepati karena suatu hal dan kita melakukan rencana lain. Atau jika data gagal didapatkan.
- _**Settled / terselesaikan**_ = Jika semua janji sudah selesai terpenuhi kita sudah bebas melakukan hal lainnya.

Kita bisa membuat sendiri apa yang akan dilakukan pada sebuah _promise_. Di dalam _promise_ ada 2 keyword yaitu `resolve()` dan `reject()`.

- **resolve()**, jika proses berhasil atau fullfilled.
- **reject()**, jika proses gagal atau rejected.

// pembuatan promise.............
let nontonPromise = new Promise((resolve, reject) => {
  if (true) {
    resolve("nonton terpenuhi") // berhasil
  } 

  reject("gagal"); // gagal
});

// eksekusi proses..............
console.log("A");

nontonPromise
  .then((result) => {
    console.log(result);
    return `${result} bareng doi`
  })
  .then((result) => {
    console.log(result)
  })
  .catch((err) => {
    console.log(err);
  });

console.log("C");
```
![js-promise](img/js-promise.png)

Contoh _pomise_ dari function :
```h
let nonton = (kondisi) => {
  return new Promise((resolve, reject) => {
    if (kondisi == "jalan") {
      resolve("nonton terpenuhi")
    }
    reject("batal nonton")
  })
}
nonton("jalan")
.then(result => {
  console.log(result)
})
.catch(err => {
  console.log(err);
})
```

> - `.then()` digunakan untuk mengantisipasi keadaan fulfilled.
> - `.catch()` digunakan untuk mengantisipasi keadaan rejected.
> - `.finally()` adalah fungsi callback yang pasti tereksekusi dalam kondisi apapun (fullfield ataupun rejected).

## Web Storage

Ada beberapa cara untuk menyimpan data pengguna seperti pencarian, artikel berita, dan lain-lain ke lokal (browser) menggunakan web storage seperti _cookies_, _local storage_, dan _session storage_. Data ini dimanfaatkan oleh situs web tersebut untuk merekam kebiasaan pengguna agar dapat memberikan rekomendasi sesuai preferensi si pengguna tersebut.

### Cookies

**Cookies** adalah data kecil yang dikirim dari situs web dan disimpan di komputer kita oleh _web browser_ saat kita menjelajah. Disebut data kecil karena maksimum data yang dapat disimpan dalam _cookies_ adalah 4096 bytes (4 KB).

Biasanya data yang disimpan di _cookies_ adalah _access token_ pengguna saat login atau data pencarian saat melakukan pencarian pada situs web tertentu. Hal ini yang biasanya dilakukan oleh situs pencarian untuk melacak pencarian kita dan menampilkan iklan yang berhubungan dengan pencarian kita sebelumnnya.

Namun ada beberapa kekurangan yang perlu kita perhatikan mengenai _cookies_ di antaranya:

- Setiap kita mengakses situs web, cookies juga kembali dikirim sehingga memperlambat aplikasi web kamu dengan mengirimkan data yang sama.
- _Cookies_ disertakan pada setiap _HTTP request_, sehingga mengirimkan data yang tidak dienkripsi melalui internet, maka saat kita ingin menyimpan data dalam _cookies_ kita harus mengenkripsinya terlebih dahulu.
- _Cookies_ hanya dapat menyimpan data sebanyak 4KB.
- Lalu _cookies_ juga memiliki tanggal kadaluarsa. Tanggal ini telah ditentukan sehingga _web browser_ bisa menghapus _cookies_ jika tanggal sudah kadaluarsa atau tidak dibutuhkan.

Kita dapat memanfaatkan jenis _web storage_ yang lain untuk mengatasi kekurangan yang dimiliki _cookies_.

Dengan memanfaatkan _local storage_ dan _session storage_, kita dapat menyimpan data lebih besar yaitu 5MB per page tanpa mempengaruhi kinerja situs web. Namun, penting untuk diketahui agar kita tidak menyimpan data sensitif seperti _password_ ke dalam _local storage_ ataupun _session storage_ untuk menghindari serangan pencurian data.

### _Local Storage_

Pada saat melakukan pencarian pada sebuah situs lalu situs tersebut menampilkan riwayat pencarian kita? Iya, data pencarian tersebut disimpan ke dalam local storage untuk diolah menjadi riwayat pencarian. Itulah salah satu contoh penerapan dari local storage pada aplikasi web.

Local storage memiliki karakteristik sebagai berikut:

1. Menyimpan data tanpa tanggal kadaluarsa.
2. Data tidak akan dihapus ketika web browser ditutup dan akan tersedia seterusnya selama kita tidak menghapus data _local storage_ pada _web browser_.
3. Dapat menyimpan data hingga 5MB.
4. Hanya dapat menyimpan data _string_.

### _Session Storage_

Berbeda dengan _local storage_, walaupun masuk ke dalam _web storage_, data yang tersimpan pada _session storage_ **akan hilang** ketika _session_ dari sebuah laman berakhir.

_Session storage_ mempunyai beberapa karakteristik, yaitu:

1. Data yang disimpan pada _session storage_ akan terus tersimpan selama _browser_ terbuka dan tidak hilang jika laman di-_reload_.
2. Membuka banyak _tab/window_ dengan URL yang sama, akan menciptakan _session storage_ yang berbeda di masing-masing _tab/window_.
3. Menutup _tab/window_ akan mengakhiri _session_ dan menghapus data yang tersimpan di _session storage_ pada _tab/window_ tersebut.
4. Data yang tersimpan dalam _session storage_ harus berbentuk _string_.
5. Hanya dapat menyimpan data sebanyak 5MB.

> Untuk menyimpan data pada _local storage_, kita menggunakan _method_ `setItem()` yang membutuhkan 2 parameter. Parameter pertama adalah _key_ yang ingin kita simpan dan parameter kedua adalah data (_value_) dari _key_ yang akan disimpan.
```h
localStorage.setItem('key', value);
```

> Untuk mengambil data yang telah tersimpan pada _local storage_, kita dapat menggunakan _method_ `getItem()` yang membutuhkan 1 parameter. Parameter tersebut adalah _key_ dari data yang kita inginkan.
```h
localStorage.getItem('key');
```

> Untuk menghapus data yang telah tersimpan pada _local storage_, kita dapat menggunakan _method_ `removeItem()` yang membutuhkan 1 parameter. Parameter tersebut adalah _key_ dari data yang ingin kita hapus.
```h
// menghapus key tertentu
localStorage.removeItem("key");

// menghapus semua key
localStorage.clear();
```