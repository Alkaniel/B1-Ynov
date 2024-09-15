#B1 #go #ytrack #ymmersion #required 
### Instructions

Write an **iterative** function that returns the factorial of the `int` passed as parameter.

Errors (non possible values or overflows) will return `0`.

### Expected function

```go
func IterativeFactorial(nb int) int {

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
	arg := 4
	fmt.Println(piscine.IterativeFactorial(arg))
}
```

And its output :

```console
$ go run .
24
$
```

### Solution & Explication

```go
package piscine

func IterativeFactorial(nb int) int {
	if nb == 0 { // C'est des maths
		return 1
	}
	if nb < 0 || nb > 20 { // C'est pour débug l'interger limit
		return 0
	}
	result := 1
	for i := 1; i <= nb; i++ { // Iterative = multiplier par le nombre d'avant.#
		result *= i
	}
	return result
}
```