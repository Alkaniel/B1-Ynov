#B1 #go #ytrack #ymmersion #optional 
### Instructions

- Write a function that reorders a slice of `int` in ascending order.

### Expected function

```go
func SortIntegerTable(table []int) {

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
	s := []int{5,4,3,2,1,0}
	piscine.SortIntegerTable(s)
	fmt.Println(s)
}
```

And its output :

```console
$ go run .
[0 1 2 3 4 5]
$
```

### Solution

```go
package piscine

func SortIntegerTable(table []int) {
	var temporaire int //int tem
	for i := 0; i < len(table); i++ {
		for o := 0; o < len(table)-1; o++ {
			if table[o] > table[o+1] {
				temporaire = table[o] //swap
				table[o] = table[o+1]
				table[o+1] = temporaire
			}
		}
	}
}
```