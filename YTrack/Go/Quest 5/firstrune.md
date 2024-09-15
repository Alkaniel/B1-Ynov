#B1 #go #ytrack #ymmersion #required 

### Instructions

Write a function that returns the first `rune` of a `string`.

### Expected function

```go
func FirstRune(s string) rune {

}
```

### Usage

Here is a possible program to test your function :

```go
package main

import (
	"github.com/01-edu/z01"

	"piscine"
)

func main() {
	z01.PrintRune(piscine.FirstRune("Hello!"))
	z01.PrintRune(piscine.FirstRune("Salut!"))
	z01.PrintRune(piscine.FirstRune("Ola!"))
	z01.PrintRune('\n')
}
```

And its output :

```console
$ go run .
HSO
$
```


### Solution

```go
package piscine

/** J'ai utilisé le concept des liste, étant donné que les index de listes commence à 0, j'ai juste transformé mon string en liste de runes et j'ai retourné la valeur de l'index 0

func FirstRune(s string) rune {
	return []rune(s)[0]
}
```
