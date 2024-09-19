#B1 #go #ytrack #ymmersion #required

### Instructions

Write a function that receives a string slice and prints each element of the slice in a seperate line.

### Expected function

```go
func PrintWordsTables(a []string) {

}
```

### Usage 

Here is a possible program to test your function :

```go
package main

import "piscine"

func main() {
	a := piscine.SplitWhiteSpaces("Hello how are you?")
	piscine.PrintWordsTables(a)
}
```

And its output:

```console
$ go run .
Hello
how
are
you?
$
```
### Solution

```go
/** Ici une simple double boucle, la première cherche mes strings dans la liste,
l'autre print mes strings rune par rune */

package piscine

import "github.com/01-edu/z01"

func PrintWordsTables(a []string) {
	for _, str := range a {
		for _, char := range str {
			z01.PrintRune(char)
		}
		z01.PrintRune('\n')
	}
}
```
