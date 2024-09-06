#B1 #go #ytrack #ymmersion #required 
### Instructions

- Write a function that reverses a `string`.
    
- This function will **return** the reversed `string`.
    

### Expected function

```go
func StrRev(s string) string {

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
	s := "Hello World!"
	s = piscine.StrRev(s)
	fmt.Println(s)
}
```

And its output :

```console
$ go run .
!dlroW olleH
$
```

### Solution

```go
package piscine

func StrRev(s string) string {
	l := len(s) //longueur de s
	var p string //variable temp
 	for i := 0; i < l; i++ {
		p = string(s[i]) + p //ex p = l => p = a + p (anciennement) l donc al
	}
	s = string(p)
	return s
}
```