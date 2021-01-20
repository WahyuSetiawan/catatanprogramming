#Catatan Pemrograman Golang

## Go CLI

Go Cli yang perli diketahui seperti dibawah ini :

1. run
2. build
3. env
4. get
5. mod

## Go Variables, Contstants, Types, Function, Packages

### Variables

Untuk variables di go sendiri terdapat beberapa variables yang seperti di

initialisasi variable di goalng dapat menggunakan cara seperti dibawah ini :

```
package main

import "fmt"

func main(){
    var x string = "hello world"
    fmt.println()
}
```

ada pula dengan cara lain seperti bawah ini :

```
package main

import "fmt"

func main(){
    var x string
    x = "Hello World"
}
```

tapi dengan keistimewaan golang kamu dapat meninitialisasikan suatu variable dengan satu langkah yaitu dengan cara :

```
package main

import "fmt"

func main(){
    x := "Hello World"
}
```

dengan cara ini kamu dapat meninitialisasikan golang dengan cara yang lebih cepat
