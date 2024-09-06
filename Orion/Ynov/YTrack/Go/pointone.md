#B1 #go #ytrack #ymmersion #required 
### Instructions

- Write a function that takes a **pointer to an `int`** as argument and gives to this `int` the value of 1.

### Expected function

```go
func PointOne(n *int) {

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
	n := 0
	piscine.PointOne(&n)
	fmt.Println(n)
}
```

And its output :

```console
$ go run .
1
$
```


### Solution 

```go
package piscine

/*En fait un pointeur donne l'adresse d'une variable, mais surtout d'autres information comme sa nature (int, str, double, etc) */

func PointOne(n *int) {
	*n = *n + 1 //ça marche comme une addition classique
}
```
