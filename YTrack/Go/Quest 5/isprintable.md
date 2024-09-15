#B1 #go #ytrack #ymmersion #required 

### Instructions

Write a function that returns `true` if the `string` passed as a parameter contains only printable characters, otherwise, returns `false`.

### Expected function

```go
func IsPrintable(s string) bool {

}
```

### Usage

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	fmt.Println(piscine.IsPrintable("Hello"))
	fmt.Println(piscine.IsPrintable("Hello\n"))

}
```

And its output :

```console
$ go run .
true
false
$
```

### Solution 

```go
package piscine

/** Ici, même que isupper sauf que l'on regarde la table ASCII, tout ce qui est en dessous de 32 n'est pas un charactère à proprement parler donc il n'est pas imprimable */

func IsPrintable(str string) bool {
	for _, r := range str {
		if r < 32 {
			return false
		}
	}
	return true
}
```