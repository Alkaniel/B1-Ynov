#B1 #go #ytrack #ymmersion 

### Instructions

Write an **iterative** function that returns the value of `nb` to the power of `power`.

Negative powers will return `0`. Overflows do **not** have to be dealt with.

### Expected function

```go
func IterativePower(nb int, power int) int {

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
	fmt.Println(piscine.IterativePower(4, 3))
}
```

And its output :

```console
$ go run .
64
$
```

### Solution

```go
package piscine

func IterativePower(nb int, power int) int {
	if power < 0 { //C'est de l'info
		return 0
	}
	if power == 0 { //x exposant 0 ça fait 1
		return 1
	}
	initialNb := nb
	for i := 1; i < power; i++ { //On itialise i à 1, et on a initalisé une variable initialeNb car on essaie de faire NB puissance x donc nb * nb * ...
		nb = nb * result
	}
	return nb
}
```