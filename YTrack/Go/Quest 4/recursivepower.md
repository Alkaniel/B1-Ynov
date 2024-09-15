#go #B1 #ytrack #ymmersion 

### Instructions

Write a **recursive** function that returns the value of `nb` to the power of `power`.

Negative powers will return `0`. Overflows do **not** have to be dealt with.

`for` is **forbidden** for this exercise.

### Expected function

```go
func RecursivePower(nb int, power int) int {

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
	fmt.Println(piscine.RecursivePower(4, 3))
}
```

### Solution

```go
package piscine

func RecursivePower(nb int, power int) int {
	if power < 0 { // info
		return 0
	}
	if power == 0 { // math
		return 1
	}
	if power == 1 { // x exposant 1 ça fait le nomb
		return nb
	}
	return nb * RecursivePower(nb, power-1)
	// Ca vas faire un boucle juqu'à arriver à 1
}

```