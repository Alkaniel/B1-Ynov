#B1 #go #ytrack #ymmersion #required 
### Instructions

Create the following function.

### Expected function

```go
func UltimateDivMod(a *int, b *int) {

}
```

`UltimateDivMod` should divide the dereferenced value of `a` by the dereferenced value of `b`.

- Store the result of the division in the `int` which `a` points to.
- Store the remainder of the division in the `int` which `b` points to.

### Usage

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	a := 13
	b := 2
	piscine.UltimateDivMod(&a, &b)
	fmt.Println(a)
	fmt.Println(b)
}
```

And its output :

```console
$ go run .
6
1
$
```

### Solution 

```go
package piscine

func UltimateDivMod(a *int, b *int) {
	s := *a //ici on use un  switch pour store la value a
	*a = *a / *b
	*b = s % *b //ca reste a%b
}

```