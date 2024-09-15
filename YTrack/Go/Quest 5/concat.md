#B1 #go #ytrack #ymmersion #required 
### Instructions

Write a function that returns the concatenation of two `string` passed in arguments.

### Expected function

```go
func Concat(str1 string, str2 string) string {

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
	fmt.Println(piscine.Concat("Hello!", " How are you?"))

}
```
### Solution

```go
package piscine

/** Concatener signifie additionner deux chaines de charactères ensemble donc on retourne juste l'addition */

func Concat(a string, b string) string {
	return a + b
}
```