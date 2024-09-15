#B1 #go #ytrack #ymmersion #optional 
### Instructions

Write a function that prints an `int` in a `string` base passed as parameters.

If the base is not valid, the function prints `NV` (Not Valid):

Validity rules for a base :

- A base must contain at least 2 characters.
- Each character of a base must be unique.
- A base should not contain `+` or `-` characters.

The function has to manage negative numbers. (as shown in the example)

### Expected function

```go
func PrintNbrBase(nbr int, base string) {

}
```

### Usage

Here is a possible program to test your function :

```go
package main

import (
	"github.com/01-edu/z01"

	"piscine"
)

func main() {
	piscine.PrintNbrBase(125, "0123456789")
	z01.PrintRune('\n')
	piscine.PrintNbrBase(-125, "01")
	z01.PrintRune('\n')
	piscine.PrintNbrBase(125, "0123456789ABCDEF")
	z01.PrintRune('\n')
	piscine.PrintNbrBase(-125, "choumi")
	z01.PrintRune('\n')
	piscine.PrintNbrBase(125, "aa")
	z01.PrintRune('\n')
}
```

And its output :

```console
$ go run .
125
-1111101
7D
-uoi
NV
$
```

### Solution

```go
package piscine

/** Ici j'ai d'abord initalisé le resultat en un string vide. Et comme c'est chiant, on vas faire étape par étape.
D'abord j'ai regardé si il y avait une base valide c'est-à-dire : si la base est plus petite que 2 ou non unique ça ne fonctionne pas. Du coup ça renvoit NV
Après j'ai du faire un isNegative, mais avec un retour boolean.
Si il le détectait j'ai forcé le nombre au négatif.
En suite,j'ai gérer la integer limit (car Ytrack la tappait de plein fouet).
PUis enfin ça, donc comme Printnbr, je récupère les unités avec un modulo par la base. et je divise par la base.

Si la string est encore vide, c'est juste le premier charactère de la base.
Et si c'est négatif, j'ajoute à la fin "-" au résultat. Puis je print
**/

func PrintNbrBase(nbr int, base string) {
	result := ""
	baseLen := len(base)

	if !isValidBase2(base) {
		PrintStr("NV")
		return
	}

	isNegativeAsBool := nbr < 0
	if isNegativeAsBool {
		nbr = -nbr
	}
	if nbr < -9223372036854775807 {
		PrintStr("-9223372036854775808")
		return
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

	PrintStr(result)
}

func isValidBase2(base string) bool {
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