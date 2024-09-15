#B1 #go #ytrack #ymmersion #required 

### Instructions

Write a function that returns the last `rune` of a `string`.

### Expected function

```go
func LastRune(s string) rune {

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
	z01.PrintRune(piscine.LastRune("Hello!"))
	z01.PrintRune(piscine.LastRune("Salut!"))
	z01.PrintRune(piscine.LastRune("Ola!"))
	z01.PrintRune('\n')
}
```

And its output :

```console
$ go run .
!!!
$
```

### Solution

```go
package piscine

/** Même chose que FirstRune, sauf que là je demande la taille de ma liste - 1 car la taille de la liste dans une liste ça fait un "OutOfIndexException" */

func LastRune(s string) rune {
	runes := []rune(s)
	return runes[len(runes)-1]
}
```