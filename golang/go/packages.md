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
