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