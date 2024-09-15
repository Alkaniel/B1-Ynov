#B1 #go #ytrack #ymmersion #required 

### Instructions

- Write a function that prints one by one the characters of a `string` on the screen.

### Expected function

```go
func PrintStr(s string) {

}
```

### Hints

Here is a possible program to test your function :

```go
package main

import "piscine"

func main() {
	piscine.PrintStr("Hello World!")
}
```

And its output :

```console
go run . | cat -e
Hello World!
```

### Solution 

```go
package piscine

import "github.com/01-edu/z01"

func PrintStr(s string) {
	swain := len(s) //longueur de s
	S := []rune(s) //array qui est hello world
	for i := 0; i < swain; i++ {
		z01.PrintRune((S[i])) //boucle qui imprime les rune in par un
	}
}
```
