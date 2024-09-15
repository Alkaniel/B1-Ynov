#B1 #go #ytrack #ymmersion #required 
### Instructions

- Write a function that takes two **pointers to an `int`** (`*int`) and swaps their contents.

### Expected function

```go
func Swap(a *int, b *int) {

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
	a := 0
	b := 1
	piscine.Swap(&a, &b)
	fmt.Println(a)
	fmt.Println(b)
}
```

And its output :

```console
$ go run .
1
0
$
```

### Solution

```go
package piscine

func Swap(a *int, b *int) {
	c := *a //variable temporaire pour stocker l'original de a
	*a = *b
	*b = c
}
```