#B1 #go #ytrack #ymmersion #optional 

### Instructions

Write a function that takes two arguments:

- `s`: a numeric `string` in a given [base](https://simple.wikipedia.org/wiki/Base_(mathematics)).
- `base`: a `string` representing all the different digits that can represent a numeric value.

And return the integer value of `s` in the given `base`.

If the base is not valid it returns `0`.

Validity rules for a base :

- A base must contain at least 2 characters.
- Each character of a base must be unique.
- A base should not contain `+` or `-` characters.

String number must contain only elements that are in base.

Only valid `string` numbers will be tested.

The function **does not have** to manage negative numbers.

### Expected function

```go
func AtoiBase(s string, base string) int {

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
	fmt.Println(piscine.AtoiBase("125", "0123456789"))
	fmt.Println(piscine.AtoiBase("1111101", "01"))
	fmt.Println(piscine.AtoiBase("7D", "0123456789ABCDEF"))
	fmt.Println(piscine.AtoiBase("uoi", "choumi"))
	fmt.Println(piscine.AtoiBase("bbbbbab", "-ab"))
}
```

And its output :

```console
$ go run .
125
125
125
125
0
$
```

### Solution

```go
package piscine

/** Atoibase, reprends le même système pour la validation de base que printnbrbase.
Sauf que l'on retoune 0 si ce n'est pas valide.
En suite on fait une map, ou on capte les index.
Dans une boucle ensuite, on multiplie le resultat par la longueur de la base en additionnant la map faite avant. Puis on print
*/

func AtoiBase(s string, base string) int {
	if !isValidBase(base) {
		return 0
	}
	baseMap := make(map[rune]int)
	for i, c := range base {
		baseMap[c] = i
	}
	result := 0
	for _, c := range s {
		result = result*len(base) + baseMap[c]
	}
	return result
}

func isValidBase(base string) bool {
	if len(base) < 2 {
		return false
	}
	baseMap := make(map[rune]bool)
	for _, c := range base {
		if c == '+' || c == '-' {
			return false
		}
		if baseMap[c] {
			return false
		}
		baseMap[c] = true
	}
	return true
}

```