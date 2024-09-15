#B1 #go #ytrack #ymmersion #required 

### Instructions

Write a function that returns the concatenation of all the `string`s of a slice of `string`s **separated** by the separator passed as the argument `sep`.

### Expected function

```go
func Join(strs []string, sep string) string {

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
	toConcat := []string{"Hello!", " How", " are", " you?"}
	fmt.Println(piscine.Join(toConcat, ":"))
}
```

And its output :

```console
$ go run .
Hello!: How: are: you?
$
```

### Solution

```go
package piscine

//** Ici, c'est un basicjoin où l'on ajoute le sépératateur donc j'ai juste ajouter l'index et j'ai fait une condition ou si l'index n'est pas 0, il ajoute le séparateur. */

func Join(strs []string, sep string) string {
	var result string
	for i, s := range strs {
		if i != 0 {
			result += sep
		}
		result += s
	}
	return result
}
```