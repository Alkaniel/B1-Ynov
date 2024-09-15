#B1 #go #ytrack #ymmersion 

### Instructions

Write a function that returns `true` if the `int` passed as parameter is a prime number. Otherwise it returns `false`.

The function must be optimized in order to avoid time-outs with the tester.

(We consider that only positive numbers can be prime numbers)

(We also consider that 1 is **not** a prime number)

### Expected function

```go
func IsPrime(nb int) bool {

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
	fmt.Println(piscine.IsPrime(5))
	fmt.Println(piscine.IsPrime(4))
}
```

And its output :

```console
$ go run .
true
false
$
```

### Solution

```go
package piscine

/**Il faut trouver ici les nombres premier.

1 n'est jamais premier donc on le passe et on initalise i à 2.
Si il n'as pas de modulo c'est que le nombre n'est pas premier car il n'est pas divisible que par 1 ou par lui-même. */

func IsPrime(nb int) bool {
	if nb <= 1 {
		return false
	}
	for i := 2; i < nb; i++ {
		if nb%i == 0 {
			return false
		}
	}
	return true
}
```