### Instructions

Write a function that returns the nth `rune` of a `string`. If not possible, it returns `0`.

### Expected function

```go
func NRune(s string, n int) rune {

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
	z01.PrintRune(piscine.NRune("Hello!", 3))
	z01.PrintRune(piscine.NRune("Salut!", 2))
	z01.PrintRune(piscine.NRune("Bye!", -1))
	z01.PrintRune(piscine.NRune("Bye!", 5))
	z01.PrintRune(piscine.NRune("Ola!", 4))
	z01.PrintRune('\n')
}
```

And its output :

```console
$ go run .
la!
$
```


### Solution

```go
package piscine

/** Ma première condition c'est si c'est plus petit que 0 donc hors de la liste. La seconnde c'est si c'est plus grand que ma liste donc pas possible. Après je retourne n-1 car on commence à 0 et pas à 1 */

func NRune(s string, n int) rune {
	runes := []rune(s)
	if n <= 0 {
		return 0
	}
	if n > len(runes) {
		return 0
	}
	return runes[n-1]
}
```