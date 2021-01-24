# Interface

untuk mendeklarasikan interface

```
type People interface {
    shortName() string
    age() string
}
```

untuk mengimplementasikan interface

```
package main

import "fmt"

type People interface {
    shortName() string
}

type Employer struct {
    firstName string
    lastName string
    age int
}

func (e Employer) shortName() string{
    return e.firstName;
}

func main(){
    var  p People

    p = Employer{firstName: "wahyu", lastName: "Setiawan", age: 28}

    fmt.Println(p.shortName());
}
```
