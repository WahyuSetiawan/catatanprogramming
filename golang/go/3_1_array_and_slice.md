# Array and Slices

# Array

mendeclarasikan array di golang

```
var buffer [256]byte
```

## Slices

Slices sndiri merupakan cara untuk mengatur dam menimplement collections data. cara mendeklarasikannya seperti

```
package main

import (
    "fmt"
    "reflect"
)

func main(){
    var intSlice []int
    var strSlice []Int

    // langsung melakukan deklarasi dari slice dan isinya
    var intSliceDeklarasi = []int{10, 20, 30, 40}
    var strSliceDeklarasi = []string{"India", "Indonesia", "Japan"}

    // mendeklarasikan dengan new keyword dari golang
    // bentuk dari deklarasi ini berupa new([:capacitas]int)[:dari:hingga]
    var intSlice = new([50]int)(0:10)

    fmt.Println(reflect.ValueOf(intSlice).Kind())
    fmt.Println(reflect.ValueOf(strSlice).Kind())
}
```

# cara memotong slice element

pemotongan dari slice atau suatu dari data collection dapat menggunakan bentuk seperti `[mulai:hingga]`. contoh untuk pengambilan array :

```
package main

import "fmt"

func main(){
    var countries = []string{"india", "japan", "canada", "australia"}

    fmt.Println("Countries: %v/n", countries)

    fmt.Println(":2 %v/n", countries[:2]) //menampilkan data dari awal hingga kurang dari index 2

    fmt.Println("1:3 %v/n", countries[1:3]) // menampilkan data dari index 1 hingga 3

    fmt.Println("2: %v/n", countries[2:]) // menampilkan data dari 2 hingga akhir
}

```

### make

membuat suatu slice dengan menggunakan function dari make dengan melihat berapa jumlah dari slice dan berapa jumlah dari capacitas

```
package main

import (
    "fmt"
    "reflect"
)

func main(){
    var intSlice = make([]int, 10)      // membuat panjang dari slice berupa 10 dan capacitas dari slices 10
    var strSlice = make([]int, 10, 20)  // membuat panjang dari slice 10 dan capacitas dari slices 20
}
```

### append

untuk menambahkan beberapa data kedalam suatu slices yang terlah terbentuk dapat menggunakan append untuk menggunakan append kamu dapat melihat contoh koding di bawah ini

```
package main

import "fmt"

func main(){
    a := make([]int, 2, 5)

    a[0] = 10
    a[1] = 20

    a = append(a, 30, 40, 50, 60, 70, 80)
}
```

### append ke slice yang sudah ada

```
package main

import "fmt"

func main(){
    var slice1 = []string{"india", "japan", "canada"}
    var slice2 = []string{"australia", "russia"}

    slice2 = append(slice2, slice1...)
}
```

### mengakses suatu nilai dari slices

lalu setelah kita dapat melakukan pembuattan dari slices dan menambahknya dengan append langsugn gimana cara kita untuk mendapatkan suatu data dari slices itu sendiri

```
pakcage main

import "fmt"

func  main(){
    var strSlice = []string("India", "Canada", "Japan")
    fmt.Println(strSlice)

    strSlice[2] = "Germany"
    fmt.Println(strSlice)
}
```

### cara menghapus index dari suatu Slices

untuk melakukan penghapusan terhadap slices kamu dapat menggunakan cara mengambil data dari berapa slices dan di skip ke slices selanjutnya

```
package main

import "fmt"

func main() {
    var strSlice = []string{"India", "Canada", "Japan", "Germany"}
    fmt.Println(strSlice)

    strSlice = RemoveIndex(strSlice, 3)
    fmt.Println(strSlice)
}

func RemoveIndex(s []String, index int) []string{
    return append(s[:index], s[index+1]...)
}
```

### copy

cara mengcopy dari slice ke slice selanjutnya dapat mengikuti langkah berikut

```
package main

import "fmt"

func main(){
    a := []int{5, 6, 7}

    b := make([]int, 5, 10)
    copy(b, a)
}
```

### melakukan perulangan untuk slices

untuk melakukan perulangan untuk slice kamu dapat menggunakan range

```
package main

import "fmt"

func main() {
    var strSlice = []String{"India", "Canada", "Japan", "Germany"}

    for index, element := range strSlice {
        fmt.Println(index, "--", element)
    }

    j := 0
    for range strSlice {
        fmt.Println(strSlice[j])
        j++
    }
}
```

### Mengetahui bila slice existing

```
package main

import "fmt"

func main (){
    var strSlice = []string{"India", "Canada", "Japan", "Germany", "Australia", "Rusia"}
    fmt.Println(itemExists(strSlice, "Canada"))
}

func itemExists(slice interface{}, item interface{}) bool {
    s := reflect.ValueOf(slice)

    if s.Kind() != reflect.Slice{
        panic("Invalid data-type")
    }

    for i := 0; i < s.len(); i ++ {
        if s.Index(i).Interface() == item {
            return true
        }
    }

    return false
}
```
