#B1 #go #ytrack #ymmersion #required 
### Instructions

Write a function that behaves like the `Index` function.

### Expected function

```go
func Index(s string, toFind string) int {

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
	fmt.Println(piscine.Index("Hello!", "l"))
	fmt.Println(piscine.Index("Salut!", "alu"))
	fmt.Println(piscine.Index("Ola!", "hOl"))
}
```

And its output :

```console
$ go run .
2
1
-1
$
```

### Solution

```go
package piscine

/** Pour celui ci, on vas parcourir la liste en retirant ce que l'on vas chercher.
Tout en parcourant de la longeur de ce que l'on cherche à chque fois. Si c'est égal à la ce que je cherche ça retourne son Index. Sinon ça retourne -1

func Index(s string, toFind string) int {
	for i := 0; i <= len(s)-len(toFind); i++ {
		if s[i:i+len(toFind)] == toFind {
			return i
		}
	}
	return -1
}
```

