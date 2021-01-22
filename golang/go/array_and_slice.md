
### Array and Slices

mendeclarasikan array di golang

```
var buffer [256]byte
```

Slices

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

cara menghapus index dari suatu Slices




pemotongan dari array atau suatu dari data yang jamak seperti bute atau strings. untuk pemotongan array sendiri dapat menggunakan bentuk seperti `[mulai:hingga]`. contoh untuk pengambilan array :

```

```
