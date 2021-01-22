
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

