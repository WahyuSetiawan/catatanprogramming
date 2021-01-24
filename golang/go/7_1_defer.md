# Defer

defer merupakan suatu cara dari golang yang digunakan untuk meneksekusi suatu perintah dari golang yang di jalankan ketika sutu function telah selesai, hal ini diperlukan bila ada function dilakukan untuk membersihkan dari suatu koding

```
package main

import (
    "fmt"
    "os"
)

func main() {
    f := createFile("/tmp/defer.txt")
    defer closeFile(f)
    writeFile(f)
}

func createFile(p string) *os.File {
    fmt.Println("creating)
    f, err := os.Create(p)
    if err != nil {
        panic(err)
    }
    return f
}

func writeFile(f *os.File){
    fmt.Println("writing")
    fmt.Fprintln(f, "data")
}

func closeFile(f *os.File){
    fmt.Println("closing")
    err := f.Close()

    if err != nil {
        fmt.Fprintf(os.Stderr, "error: %v\n", err)
        os.Exit(1)
    }
}
```
