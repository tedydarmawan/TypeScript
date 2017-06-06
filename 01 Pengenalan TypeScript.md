## Objective
- [Apa itu TypeScript?](#apa-itu-typescript)
- [Tipe Data](#tipe-data)
- [Class](#class)
- [Interface](#interface)
- [Module](#module)

## Apa itu TypeScript?
TypeScript merupakan superset dari JavaScript yang berarti pada saat proses compile TypeScript akan dicompile kembali ke JavaScript.

TypeScript menyediakan __strong typing__ yang dapat mendukung pemberian tipe data ke variabel dan anggota-anggota kelasnya (JavaScript tidak memiliki fitur ini). 
Dengan fitur ini jika ada error karena memberikan nilai dengan tipe data yang berbeda maka akan muncul notifikasi error pada TypeScript.
Oleh karena itu membuat bahasa pemrograman TypeScript menjadi lebih mudah diimplementasikan dibandingkan dengan JavaScript.

Selain itu TypeScript juga memiliki fitur lain yang tidak dimiliki oleh JavaScript yakni class, interface, generic dan module.

> Compile TypeScript melalui cmd : tsc namafile

## Tipe Data
### Boolean
``` typescript
let namaVariabel: boolean = true;

//atau

let namaVariabel = true;
```
### Number 
``` typescript
let namaVariabel: number = 6.5;
```

### String
``` typescript
let namaVariabel: string = "Merah";
```

### Array
Element Type Array
``` typescript
let namaVariabel: number[] = [1,2,3];
```

Generic Array

Generic merupakan tipe data yang dapat digunakan oleh beberapa tipe data (fleksibel).
``` typescript
let namaVariabel: Array<number> = [1,2,3];
```

### Enum
``` typescript
enum Warna {Merah, Kuning, Hijau}
let w: Warna = Warna.Merah;
```

### Any
``` typescript
let namaVariabel: any;
```

### Void
``` typescript
function namaFunction(): void {
  alert("Contoh tipe data void");
}
```

## Class
TypeScript mendukung penggunaan class seperti pada pemrograman berorientasi objek pada umumnya contohnya Java, sehingga TypeScript memiliki fitur seperti inheritance, access modifier, static property dan lainnya.
``` typescript
class Mobil{
  brand: string;
  ban: number;
  private  kecepatan: number;
  
  constructor(kecepatan: number){
    this.kecepatan = kecepatan || 0;
  }
  
  tambahKecepatan(): void{
    this.kecepatan++;
  }
  
  kurangiKecepatan(): void{
    this.kecepatan--;
  }
  
  showKecepatan(): void{
    console.log(this.kecepatan);
  }
  
  static jumlahBan(): number{
    return 4;
  }
}

// Membuat instance
let m = new Mobile(7);
m.tambahKecepatan();
m.showKecepatan();

console.log(Mobil.jumlahBan());
```

## Interface
Interface itu bagaikan suatu blueprint atau kontrak untuk kelas atau tipe data yang mengimplementasikan interface tersebut. Interface dapat digunakan untuk membuat custom type tanpa harus membuat suatu kelas.

``` typescript
interface User{
  username: string;
  password: string;
  confirmPassword?: string; // simbol ? menandakan bahwa variabel tersebut optional atau not required
}

let user: User;

user = {username: 'tedy', password: 'secret'};
```

Interface juga bisa memiliki function tanpa harus mengimplementasikan function bodynya.
``` typescript
interface Gerak{
  tambahKecepatan(kecepatan: number): void;
}

let mobil: Gerak = {
  tambahKecepatan: function(kecepatan: number){
    //...
  }
}
```

## Module
TypeScript memiliki fitur modular, sehingga kode TypeScript dapat dibuat menjadi beberapa file terpisah. Keyword export digunakan untuk mendukung fitur ini.

``` typescript
export class ExportClass{
  // export kelas
}
```
