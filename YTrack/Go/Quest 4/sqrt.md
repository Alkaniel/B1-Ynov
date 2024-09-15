#B1 #ytrack #ymmersion #go

### Instructions

Write a function that returns the square root of the `int` passed as parameter, if that square root is a whole number. Otherwise it returns `0`.

### Expected function

```go
func Sqrt(nb int) int {

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
	fmt.Println(piscine.Sqrt(4))
	fmt.Println(piscine.Sqrt(3))
}
```

And its output :

```console
$ go run .
2
0
$
```

### Solution

```go
package piscine
/** Le but d'exo c'est de retrouver la racine carré d'un nombre donc on regarde juste si i multiplié par lui-même est égale au nombre entré en constructeur alors il retournera i car c'est la racine carée*/

func Sqrt(n int) int {
	for i := 1; i <= n; i++ {
		if i*i == n {
			return i
		}
	}
	return 0
}
```