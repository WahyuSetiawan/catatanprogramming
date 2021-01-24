# Struct pada golang

Struct merupakan mengkelompokan data bersama untuk suatu form recoreds. misal untuk nama orang terdapat beberapa nilai seperti nama, umur, alamat, tanggal, lahir. Untuk itu dibutuhkan beberapa nilai seperti

```
type Person struct {
    name string
    age int
}
```

## mendeklarasikan suatu struct

untuk mendeklarasikan suatu struct dapat menggunakan cara seperti

```
package main

import "fmt"

type Person struct {
    name string
    age int
}

func main() {
    var person = Person{name: "wahyu", age: "27"}

    fmt.Println(person.name)
}
```

## menambahkan methods kedalam suatu struct

untuk menambahkan suatu function dalam struct golang akan menjadi seperti

```
func (p person) getName() string{
    return p.name
}
```
