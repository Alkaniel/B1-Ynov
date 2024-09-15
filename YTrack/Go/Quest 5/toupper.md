### Instructions

Write a function that capitalizes each letter in a `string`.

### Expected function

```go
func ToUpper(s string) string {

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
	fmt.Println(piscine.ToUpper("Hello! How are you?"))
}
```

And its output :

```console
$ go run .
HELLO! HOW ARE YOU?
$
```

### Solution

```go
package piscine

/** Il y a une différence de 32 entre une minuscule et son équivalent en majuscule en ASCII, donc dès qu'il détecte une minuscule il fait -32 sur cette minuscule. */ 

func ToUpper(s string) string {
	s1 := []rune(s)
	for i := range s1 {
		if s1[i] >= 'a' && s1[i] <= 'z' {
			s1[i] = s1[i] - 32
		}
	}
	return string(s1)
}
```