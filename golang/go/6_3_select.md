# Select

Select dapat digunakan untuk mengatur channel operastions dengan mengabungkan antara gourotines dan channels. seperti

```

package main

import (
    "fmt"
    "time"
)

func main(){
    c1 := make(chan string)
    c2 := make(chan string)

    go func(){
        time.Sleep(1 * time.Seconds)
        c1 <- "one"
    }()

    go func(){
        time.Sleep(2 * time.Seconds)
        c2 <- "two"
    }

    for i := 0; i < 2; i++{
        select {
            case msg1 := <-c1:
                fmt.Println("received", msg1)
            case msg2 := <-c2:
                fmt.Println("received", msg2)
        }
    }
}
```

dari perintah diatas menujukan bahwa dari for akan melakukan perulangan bilamana select dari c1 dan c2 telah di kerjakan hal ini di ketahui dari perintah `case msg1 := <-c1` dan `case msg2 := <-c2`.

## Non Blocking channel Operation

```
package main

import "fmt"

func main(){
    messages := make(chan string)
    signals := make(chan bool)

    select{
        case msg:= <- messages:
            fmt.Println("received messages", msg)
        default:
            fmt.Println("no messages received")
    }

    msg := "hi"
    select {
        case messages <- msg:
            fmt.Println("sent messages", msg)
        case default:
            fmt.Println("no message sent")
    }

    select {
        case msg := <- messages:
            fmt.Println("received message", msg)
        case sig := <- signals:
            fmt.Println("received signal", sig)
        default:
            fmt.Println("no activity")
    }
}
```
