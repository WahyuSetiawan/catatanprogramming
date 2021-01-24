# Untuk Mengatur Dependencies Dengan Golang Modules

Golang sendiri telah menyertakan sutau dependencies yang dapat kamu gunakan untuk mengatur dependencies yang kamu butuhkan di pengembangan aplikasi dari golang ini. 

## Init Go

untuk menetapkan go modules kamu dapat menggunakan namanya `go mod init [nama pakcage]` perintah tersebut berguna untuk kamu yang tidak ingin terkait dengan `go src` dan ingin membuat dan mengembangkan dengan folder yang flexible sehingga kamu dapat mengatur file file yang terdapat di dalam project mu. 

## Untuk menambahkan package ke dalam golang

Untuk menambahkan suatu package kedalam suatu golang kamu dapat menggunakan perintah `go get [nama package]`, perintah ini akan mengeksekusi pendownloadan data dari server repository ke dalam go src.

## Import Compability Rule

 "If an old package and a new package have the same import path, the new package must be backwards compatible with the old package." 

## Go SUM

Bila telah mengimport suatu package golang akan membuat file go.sum yang ditujukan untuk auntentication terhadap suatu package yang akan di import. terkadang terdapat suatu application yang membuatuhkan suatu public key untuk mengunduhnya untuk mengunduh suatu private repository tersebut dapat menambahkan public key di 

```
GOSUMDB="sum.golang.org"
GOSUMDB="sum.golang.org+<publickey>"
GOSUMDB="sum.golang.org+<publickey> https://sum.golang.org"
```

## Go Private

golang otomatis mendownload modules dari public yangterdapta di proxy.golang.org, dan hal itu membaut validasi, pengecekan suatu modules dari go secara default berdasarkan dengan sum.golang.org. Untuk mendapatkan suatu modules yang terdapat di private kamu dapta menggunakan GOPRIVATE environment untuk mengontrol modules menjadi private contoh

```
GOPRIVATE=*.corp.example.com
GOPROXY=proxy.example.com
GONOPROXY=none
```

## Go Action 
