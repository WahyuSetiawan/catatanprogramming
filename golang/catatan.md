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

Untuk variables di go sendiri terdapat beberapa variables yang seperti Deklarasi variabel di golang dapat menggunakan cara seperti dibawah ini :

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

### Constants

Digunakan untuk mencegah terjadinya perubahan data karena data dalam variable ini tidak boleh dirubah sembarangan

```
package main

import "fmt"

func main(){
    const x = "Hello"
}
```

### Types

Type di golang sendiri terdiri dari

| Type       | Nilai          | Initial                                              |
| ---------- | -------------- | ---------------------------------------------------- |
| Booleans   | true dan false | bool                                                 |
| Floats     | 0.0            | float64, float32                                     |
| complex128 | 1.0i           | complex128                                           |
| Integers   | 1,2,3          | int, uint, int8, uint8, int16, uint16, int32, uint32 |
| chars      | 'a'            | char                                                 |
| string     | "string"       | string                                               |

### Function

untuk function sendiri dari golang dapat mengikuti bentuk seperti dibawah ini

```
func Function(){
    echo "hello world";
}
```

untuk dengan parameter dapat mengikuti perintah seperti pada

```
func Function(a int, b int){
    c := a + b;

    fmt.println(c)
}
```

untuk memberikan suatu return terhadap suatu function dapat mengikuti langkah seperti

```
func Function(a int, b int) int {
    return a + b;
}
```

return suatu nilai dengan metode name dengan return yang dapat di deklarasikan dengan nama

```
func Function(a int, b int) (hasil int){
    hasil = a + b
    return
}
```

return dengan multiple values

```
func Function(a int, b int) (dari int, jadi int){
    dari  = a
    jadi = a + b
    return
}
```

function dengan anonymouse function

```
var (
    tambah = func (a int, b int) int {
        return a + b
    }
)

func main () {
    fmt.println(tambah(1, 2));
}
```

atau

```
func main(){
    func(l int, b int)  int {
        return l + b
    }(10, 20)
}
```

function yang tertutup merupakan suatu spesial untuk memberikan suatu kemudahan function mengakses nilai yang berada di luar dari function tersebut

```
func main() {
    for i := 10; i > 1; i-- {
        tambah1 := func() int {
            i + 1
        }

        fmt.println(tambah1)
    }
}
```

returning data function arguments

```
package main

import "fmt"

func tambah(a int, b int) int {
    return a + b
}

func partialTambah(x int) func(int) int {
    return func(y int) int {
        return tambah(x, y)
    }
}

func main(){
    partial := partialTambah(3)
    fmt.Println(partial(7))
}
```

### Packages

package untku memberrikan suatu lockais ynag dapat menjadi tempat pemanggilant terhadap suatu file dari golang. penempatan package terdapat di awal dari file seperti pada terlihat di file main dibawah ini

```
package main

import "fmt"

fun main(){
    fmt.Println("hello world");
}
```

package terdapat di dalam area main. untuk import dari package yang lain dapat dilakukan dengan `import "fmt"` yang menandakan untuk mengimport dari package fmt. agar dapat dijalankan didalan function main. Dari package yang di importkan untuk menjalankannya dapat mengikuti perintah seperti `fmt.Pringln("Hello world")`

Untuk mengimport multiple package dari goleng dapat mengikuti package seperti pada gambar

```
import (
    "fmt"
    "math"
)
```

### Array and Slices

mendeclarasikan array di golang

```
var buffer [256]byte
```


Slices 