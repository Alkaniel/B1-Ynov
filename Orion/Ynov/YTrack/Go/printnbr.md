#B1 #ytrack #ymmersion #go #optional 

## Instructions 

**Write a function that prints an `int` passed in parameter. All possible values of type `int` have to go through. You cannot convert to `int64`.

## Usage

```go
package main

import (
	"piscine"
	"github.com/01-edu/z01"
)
func main() {
	piscine.PrintNbr(-123)
	piscine.PrintNbr(0)
	piscine.PrintNbr(123)
	z01.PrintRune('\n')
}
```

And its output :

```console
$ go run .
-1230123
$
```

## Solution & Explication

```go
package piscine

import "github.com/01-edu/z01"

func PrintNum(num int) {
	i := '0'
	if num == 0 {
		z01.PrintRune('0') // Gère '0'
		return             //Return seule met fin à l'instance/fonction
	}
	for j := 1; j <= num%10; j++ { //Qu'un seul s'active sur les deux, ici si num = 123 -> i = 3 en soit i = modulo
		i++
	}
	for j := -1; j >= num%10; j-- { // Si num = -123 -> i = -7 en soit i = modulo
		i++
	}
	if num/10 != 0 {
		PrintNum(num / 10) // Veut récuperer que la unité I think. Créer une instance de lui-même.
	}
	z01.PrintRune(i)
	return // Ecrit la dernière , puis la seconde ect.... Recursive. Return seule met fin à l'instance/fonction
}

func PrintNbr(n int) {
	if n < 0 {
		z01.PrintRune('-')
	}
	PrintNum(n)
}
```