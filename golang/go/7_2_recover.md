# Recover

ketika terdapat pesan dari suatu kesalahan dengan menggunakan recover kita mendapatkan pesan dari kesalahan dan apa yang harus dilakukan dengan bila hal itu terjadi 

```
package main

import "fmt"

func recovery() {
    if r := recover(); r != nil {
        fmt.Println("recovered:", r)
    }
}

func sum(a int, b int){
    defer recovery()
    fmt.Printf("%d + %d = %d\n", a, b, a+b)
    done := make(chan bool)
    go devide(a, b, done)
    <- done
}

func divide(a int, b int, done chan bool) {
    fmt.Printf("%d / %d = %d", a, b, a/b)
    done <- true
}

func main() {
    sum(5, 0)
    fmt.Pringln("normaly returned from main")
}
```