# Channel

Channels merupakan suatu jalur yang dapat digunakan untuk menkomunikasikan antar thread jadi setiap thread yang berjalan, mereka memiliki suatu lingkungan mereka sendiri yang membuat tidak dapat berkomunikasinya antara thread satu dengan thread yang lain. untuk menkomunikasikan antara thread satu dengan thread yang lain maka di butuhkan suatu metode yang dinamakan channel di bahasa pemrograman golang ini.

```
package main

import "main"

func main(){
    messages := make(chan string)

    go runc(){
        messages <- "ping"
    }()

    msg := <-messages
    fmt.Println(msg)
}
```

membuat suatu channel dengan cara mendeklarasikan suatu channel dengan new channel  `messages := make(chan string)`. Setelah itu goroutine akan memberikan suatu nilai terhadap channel tersebut `go func(){ messages <- "ping"}()`. 
Maka setiap channel akan mengeluarkan nilai yang sesuai dengan apa yang dimasukan di dalam channe messages. Nilai itu akan di simpan di dalam suatu variable dengan perintah `msg := <- messages` dan ditampilan dengan `fmt.Println(msg)`

## Buffer Channel

secara defaul channels di golang di set secaran unbuffered, dengan arti mereka hanya dapat menerima message dengan simbol `chan <-` dan  menerima dengan `<- chan`. Dengan channel buffered dapat membatasi nilai yang dapat dikirim dari channel agar tidak mengirim suatu nilai yang berlebih.

```
package main 

import "fmt"

func main(){
    messages := make(chan string, 2)

    messages <- "buffered"
    messages <- "channel"

    fmt.Println(<-messages)
    fmt.Println(<-messages)
}
```

contoh koding diatas merupakan suatu limitasi dari golang yang melimit suatu pengiriman hanya dengan 2 values saja

## Buffered Synchronization

Dengan cara ini channel dapat di buat menunggu untuk dieksekusi, hal ini bisa terjadi bilamana terdapat suatu perintah yang harus dikerjakan dulu maka Channel Synchronization ini berjalan. 

```
package main 

import (
    "fmt"
    "time"
)

func worker(done chan bool) {
    fmt.Println("working....")
    time.Sleep(time.Second)
    fmt.Println("done")

    done <- true
}

func main(){
    done := make(chan bool, 1)

    go worker(done)

    <- done
}
```

Dengan perintah seperti diatas kamu dapat memberikan suatu perintah bila mana terdapat suatu perintah yang telah terjadi maka proses selanjutnya akan dapat dijalankan terjadi di peringah `<- done`.

## Channel Direction

Parameter dari function dapat kamu tetapkan sebagai penerima dari suatu channel, hal ini bisa disebut sebagai channel directions. Untuk menetapkan suatu parameter dari function menjadi suatu penerima saja untuk channels kamu dapat menggunakan perintah `pings <- chan string` untuk menerima segala nilai yang melalui suatu channels, dan untuk mendapatkan nilai mengirim suatu niali melalui channel menggunakan `pongs chan <- string`.

```
package main

import "fmt"

func ping (pings chan <- string, msg string){
    pings <- msg // msg akan di lempar ke channel pings
}

func pongs(pings <- chan string, pongs chan <- string){
    msg := <- pings
    pongs <- msg
}

func main() {
    pings := make(chan string, 1)
    pongs := make(chan string , 1)
    ping(pings, "passed messages")
    pong(pings, pongs)
    fmt.Println(<- pongs)
}
```

## Closing Channels

untuk menutup channels yang telah mengirim maka channel sudah tidak dibutuhkan lagi dapat kamu tutup dengan perintah `close(nama_channel)`

```
package main

import "fmt"

func main(){
    jobs := make(chan int, 5)
    done := make(chan bool)

    go runc() {
        for {
            j, more := <- jobs
            if more {
                fmt.Println("received jobs", j)
            }   else{
                fmt.Println("received all jobs")
                done <- true
                return 
            }
        }
    }()

    for j := 1; j <= 3; j++{
        jobs <- j
        fmt.Println("sent job", j)
    }

    close(jobs)
    fmt.Println("sent all jobs")

    <- done
}
```

dengan contoh diatas close jobs akan menutup channel dari jobs karena telah dilakukan dengan mengirimkan didalam perulangan yang mengirimkan nilai kedalam goroutine. didalamm gourotine sendiri juga terdapat perulangan yang digunakan untuk menerima setiap masukan yang dikirim melalui jobs, tapi disaat jobs telah di tutup maka jobs juga mengirimkan suatu nilai tapi nilai itu kosong, dan memiliki nilai false di more. perintah gourotine menjalankan perintah tampilan `received all jobs` dan mengirim signal true ke dalam channel done.

