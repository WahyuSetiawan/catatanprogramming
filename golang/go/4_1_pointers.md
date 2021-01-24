# Pointers

pointers merupakan untuk mendpatkan alamat dari value itu tersimpan. untuk menambil suatu nilai penyimpan dari variable kamu dapat manambahkan `&` di awal dari variable untuk memunculkan alamat dari. Apabila pendeklarasian dari menggunakan pointer ini juga akan membuat variable tersebut hanya dapat di isi alamat penyimpanan variable

```
var p *int
```

untuk mengisi nilai dari p maka dibutuhkan alamat dari suatu nilai lain seperti

```
var i = 1

var j *int

j = &i

```

dari penyimpanan nilai j untuk mendapatkan nilai dari j, menambahkan suatu `*` untuk menampilkan nilai yang akan di tampilkan

```
fmt.Println(*j)
```
