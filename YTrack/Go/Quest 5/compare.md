#B1 #go #ytrack #ymmersion #required

### Instructions

Write a function that behaves like the `Compare` function.

### Expected function

```go
func Compare(a, b string) int {

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
	fmt.Println(piscine.Compare("Hello!", "Hello!"))
	fmt.Println(piscine.Compare("Salut!", "lut!"))
	fmt.Println(piscine.Compare("Ola!", "Ol"))
}
```

And its output :

```console
$ go run .
0
-1
1
$
```

```go
package piscine

/** Compare est très simple, il suffit de suivre la fonction de base. C'est binairee bientôt. Si a = b c'est 0, si a > b, c'est 1. Si a < b, c'est -1 */

func Compare(a, b string) int {
	if a == b {
		return 0
	} else if a > b {
		return 1
	} else {
		return -1
	}
}
```