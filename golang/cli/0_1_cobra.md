# Penggunaaan Cobra Golang

Cobra erupakan suatu library yang memepermudah dalam pengembangan suatu aplikasi dengan menggunakan bahsa pemrogramman golang.

# Keunggulan

1. Mudah dalam navigasi dair cli dengan berdasarkan subcommands cli
2. Nested Subcommaneds
3. Global, local and cascading flags

# Installation

Untuk menginstall cobra golang cli di komputer kamu, kamu hanya membutuhkan untuk mengikuti langkah - langkah berikut ini :

```
go get -u github.com/spf13/cobra
```

untuk menambahkan cobra ke dalam application kamu dengan menginport seperti 

```
import "github.com/spf13/cobra"
```

# Cobra generator

Cobra juga punya suatu tool untuk mempemudah kamu dalam membuat application dengan segala command yang kamu mau. untuk menambahkan cobra command kamu dapat mengikuti perintah seperti

```
go get github.com/spf13/cobra/cobra
```

dari perintah itu akan menambahkan cobra executable kedalam `$GOPATH/bin` directory.

## cobra init

dengan cobra ini kamu mendapatkan kamudahan untuk mengenerate dari application yang ingin kamu buat. Dengan melalui cobra init generate otomatis menyertakan license yang sesuai denga application yang kamu buat. untuk menjalankan cobra generator ini kamu dapat mengikuti langkah :

```
mkdir -p newApp && cd newApp
cobra init --pkg-name github.com/spf13/newApp
```

or 

```
cobra init --pkg-name github.com/spf13/newApp path/to/newApp
```

## cobra app


## cobra flag

untuk cli biasa terdapta flag yang di berikan dibelakang dari comand yang sedang ingin dkerjakan. dalam library cobra ini kamu dapat menambahkan hal itu dengan mudah dengan beberapa perintah dibawah ini

```
rootCmd.PersistentFlags().BoolVarP(&Verbose, "verbose", "v", false, "verbose output")
```

cobra juga menyediakan flag yang akan di jalankan terhadapat command yang spesifik dengan perintah

```
rootCmd.Flags().StringVarP(&Source, "source", "s", "", "Source directory to read")
```