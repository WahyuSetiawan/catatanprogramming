# Gorotine

gorotine merupakan suatu cara untuk menjalankan suatu function dijalankan di thread yang berbeda dengan main

```

package main

import {
    "fmt"
    "time"
}


func f (from string){
    for i := 0; i <3; i++{
        fmt.Println(from, ":", i)
    }
}

func main(){
    f("direct")

    go f("goroutine")

    go func(msg string){
        fmt.Println(msg)
    }("going")

    time.Sleep(time.Second)
    fmt.Println("done")
}

```

karena setiap proses dijalankan secara synchronous, untuk menjalankan dengan goroutine maka function akan dijalankan secaran ansyncronous dengan menggunakan perintah `go`.


