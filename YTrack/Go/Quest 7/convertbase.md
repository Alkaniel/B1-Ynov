#B1 #go #ytrack #ymmersion #optional

### Instructions

Write a function that receives three arguments:

* nbr: A string representing a numberic value in a base.
* baseFrom: A string representing the base nbr it's using.
* baseTo: A string representing the base nbr should be represented in the returned value.

Only valid bases will be tested.
Negative numbers will not be tested.

### Expected function
```go
func ConvertBase(nbr, baseFrom, baseTo string) string {

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
	result := piscine.ConvertBase("101011", "01", "0123456789")
	fmt.Println(result)
}
```

And its output:
```console
$ go run .
43
$
```

### Solution

```go
package piscine

/** En fait, ici il faut d'abord le convertir en décimal, donc j'ai utilisé AtoiBase qui le fait déjà.
En suite, il faut le convertir dans la base donné, j'ai utilisé pour ça une fonction déjà faite quelque peut modifié qui est à la base PrintNbrBase, que j'ai fait return.
Puis j'ai return le converted. */

func ConvertBase(nbr, baseFrom, baseTo string) string {
	toDecimal := AtoiBase(nbr, baseFrom)
	converted := ReturnNbrBase(toDecimal, baseTo)
	return converted
}

func ReturnNbrBase(nbr int, base string) string {
	result := ""
	baseLen := len(base)

	if !isValidBaseTheReturn(base) {
		return "NV"
	}

	isNegativeAsBool := nbr < 0
	if isNegativeAsBool {
		nbr = -nbr
	}
	if nbr < -9223372036854775807 {
		return "-9223372036854775808"
	}

	for nbr != 0 {
		result = string(base[nbr%baseLen]) + result
		nbr /= baseLen
	}

	if result == "" {
		result = string(base[0])
	}

	if isNegativeAsBool {
		result = "-" + result
	}

	return result
}

func isValidBaseTheReturn(base string) bool {
	if len(base) < 2 {
		return false
	}

	charMap := make(map[rune]bool)
	for _, char := range base {
		if char == '-' || char == '+' {
			return false
		}
		if charMap[char] {
			return false
		}
		charMap[char] = true
	}

	return true
}
```

