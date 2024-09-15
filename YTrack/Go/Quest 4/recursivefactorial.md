#B1 #go  #ytrack #ymmersion #required 

### Instructions

Write a **recursive** function that returns the factorial of the `int` passed as parameter.

Errors (non possible values or overflows) will return `0`.

`for` is **forbidden** for this exercise.

### Expected function

```go
func RecursiveFactorial(nb int) int {

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
	fmt.Println(piscine.RecursiveFactorial(arg))
}
```

```console
$ go run .
24
$
```

### Solution

```go
package piscine

//Faire une fonction récursive c'est la fonction sur elle même, donc au lieu de multiplier la fonction dans la boucle for, il faut la multiplié par une instance.

func RecursiveFactorial(nb int) int {
	if nb == 1 {
		return 1
	}
	if nb < 0 || nb > 20 {
		return 0
	}
	if nb > 1 {
		return nb * RecursiveFactorial(nb-1)
	}
	return 1
}
```