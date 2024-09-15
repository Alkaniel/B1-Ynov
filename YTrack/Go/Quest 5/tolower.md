### Instructions

Write a function that lower cases for each letter in a `string`.

### Expected function

```go
func ToLower(s string) string {

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
	fmt.Println(piscine.ToLower("Hello! How are you?"))
}
```

And its output :

```console
$ go run .
hello! how are you?
$
```

### Solution

```go
package piscine

/** Ici je ne sais pas ce que j'ai fait, j'ai du boire je pense. En vrai, il a juste à faire +32 au lieu de -32 dès qu'il voit une majuscule. */

func ToLower(s string) string {
	var str string
	for _, r := range s {
		if r >= 'A' && r <= 'Z' {
			str = str + string(r+32)
		} else {
			str = str + string(r)
		}
	}
	return str
}
```
