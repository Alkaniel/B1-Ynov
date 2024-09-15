#B1 #go #ytrack #ymmersion #required 

### Instructions

Write a function that returns `true` if the `string` passed as parameter contains only uppercase characters, otherwise, returns `false`.

### Expected function

```go
func IsUpper(s string) bool {

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
	fmt.Println(piscine.IsUpper("HELLO"))
	fmt.Println(piscine.IsUpper("HELLO!"))

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

/** Ici, on parcours le string, si une lettre n'est pas une Majuscule, ça retourne faux, sinon vraie **/

func IsUpper(str string) bool {
	for _, r := range str {
		if r < 'A' || r > 'Z' {
			return false
		}
	}
	return true
}
```