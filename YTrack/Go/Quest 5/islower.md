#B1 #go #ytrack #ymmersion #required 

### Instructions

Write a function that returns `true` if the `string` passed as the parameter contains only lowercase characters, otherwise, returns `false`.

### Expected function

```go
func IsLower(s string) bool {

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
	fmt.Println(piscine.IsLower("hello"))
	fmt.Println(piscine.IsLower("hello!"))

}
```

And its output :

```console
$ go run .
true
false
$
```

### Solution : 

```go
package piscine

/** Même que isupper, sauf que là on détecte les minuscules */

func IsLower(str string) bool {
	for _, r := range str {
		if r < 'a' || r > 'z' {
			return false
		}
	}
	return true
}
```

