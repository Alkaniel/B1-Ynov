#B1 #go #ytrack #ymmersion #required 

### Instructions

- Write a function that counts the `runes` of a `string` and that returns that count.

### Expected function

```go
func StrLen(s string) int {

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
	l := piscine.StrLen("Hello World!")
	fmt.Println(l)
}
```

And its output :

```console
$ go run .
12
$
```

### Solution

```go
package piscine

func StrLen(s string) int {
	i := len([]rune(s)) //recupère la longeur de s que l'on a transformé en array
	return i //retourne 
}
```