# 🧠 Penjelasan Object
<p align="justify">
Object adalah struktur data yang menyimpan pasangan key dan value. Object bisa berisi property (data) dan method (fungsi), sehingga dapat merepresentasikan sesuatu yang kompleks seperti mobil, pengguna, atau produk.
</p>

---

### 📌 Cara membuat object secara umum ada 6 yaitu:

- **Object Literal** 📎
  <p align="justify">
    Digunakan untuk data sederhana & statis.
  </p>
  
  ```js
  const mobil = {
    brand: "Toyota",
    model: "Supra",
    tahun: 2024,
    warna: "Merah"
  };
  
  console.log(mobil.brand); // Toyota
  console.log(mobil["tahun"]); // Supra

- **Keyword New Object()** 📎
  <p align="justify">
      Digunakan untuk gaya lama dan library / framework jadul.
  </p>
  
  ```js
  // bikin object kosong dulu
  const person = new Object();
  
  // tambahin property manual
  person.nama = "Dani";
  person.umur = 25;
  person.kota = "Jakarta";
  
  console.log(person);
  // { nama: 'Dani', umur: 25, kota: 'Jakarta' }

- **Constructor Function** 📎
  <p align="justify">
      Digunakan untuk buat banyak object dengan struktur sama.
  </p>
  
  ```js
  // Constructor Function
  function Mahasiswa(nama, jurusan) {
    this.nama = nama;
    this.jurusan = jurusan;
    this.sapa = function() {
      return `Halo, saya ${this.nama} dari jurusan ${this.jurusan}`;
    };
  }
  
  // bikin object baru dari constructor
  const mhs1 = new Mahasiswa("Dani", "Informatika");
  const mhs2 = new Mahasiswa("Dina", "Desain");
  
  console.log(mhs1.sapa()); // Halo, saya Dani dari jurusan Informatika
  console.log(mhs2.sapa()); // Halo, saya Dina dari jurusan Desain

- **Class (ES6)** 📎
  <p align="justify">
      Digunakan untuk buat banyak object dengan pola sama dan lebih modern.
  </p>
  
  ```js
  // Definisi Class
  class Mahasiswa {
    constructor(nama, jurusan) {
      this.nama = nama;
      this.jurusan = jurusan;
    }
  
    // Method di dalam class
    sapa() {
      return `Halo, saya ${this.nama} dari jurusan ${this.jurusan}`;
    }
  }
  
  // Membuat object dari class
  const mhs1 = new Mahasiswa("Dani", "Informatika");
  const mhs2 = new Mahasiswa("Dina", "Desain");
  
  console.log(mhs1.sapa()); // Halo, saya Dani dari jurusan Informatika
  console.log(mhs2.sapa()); // Halo, saya Dina dari jurusan Desain
  
- **Object.create()** 📎
  <p align="justify">
      Digunakan untuk buat object dengan prototype custom tanpa class.
  </p>
  
  ```js
  const hewan = {
    bisaBergerak: true,
    makan() {
      return "Hewan sedang makan";
    }
  };
  
  // bikin object baru dengan prototype dari hewan
  const kucing = Object.create(hewan);
  kucing.nama = "Kitty";
  
  console.log(kucing.nama);          // Kitty
  console.log(kucing.bisaBergerak);  // true (warisan dari hewan)
  console.log(kucing.makan());       // Hewan sedang makan

- **Factory Function** 📎
  <p align="justify">
      Digunakan untuk buat object tanpa ribet pakai new.
  </p>
  
  ```js
  // Factory Function
  function buatMahasiswa(nama, jurusan) {
    return {
      nama: nama,
      jurusan: jurusan,
      sapa() {
        return `Halo, saya ${this.nama} dari jurusan ${this.jurusan}`;
      }
    };
  }
  
  // bikin object baru dari factory function
  const mhs1 = buatMahasiswa("Dani", "Informatika");
  const mhs2 = buatMahasiswa("Dina", "Desain");
  
  console.log(mhs1.sapa()); // Halo, saya Dani dari jurusan Informatika
  console.log(mhs2.sapa()); // Halo, saya Dina dari jurusan Desain
