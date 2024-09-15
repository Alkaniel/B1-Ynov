### Instructions

Write a function that capitalizes the first letter of each word **and** lowercases the rest.

A word is a sequence of **alphanumeric** characters.

### Expected function

```go
func Capitalize(s string) string {

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
	fmt.Println(piscine.Capitalize("Hello! How are you? How+are+things+4you?"))
}
```

And its output :

```console
$ go run .
Hello! How Are You? How+Are+Things+4you?
$
```

### Solution

```go
package piscine

/** Ici j'ai du traiter en premier la première lettre pour ne pas m'embêter et j'ai ensuite fait une boucle.
A chaque fois, ça check si la rune d'avant est alphanumerique, dans ce cas si ce n'est pas une majuscule, dans le cas contraire ou le premier if n'est pas respecté et que c'est une majuscule, ça devient une minuscule si c'est une majuscule. 
J'ai aussi découvert que l'on peut appeller les ancienne fonctions faites sur YTrack comme isAlpha, (sans que YTrack pête un plomb car sinon je ne savais déjà de base), mais je n'ai pas pu l'utiliser car mes fonctions utilisent des strings et non des runes. */

func Capitalize(s string) string {
	runeArray := []rune(s)
	if runeArray[0] >= 'a' && runeArray[0] <= 'z' {
		runeArray[0] -= 32
	}
	for i := 1; i < len(runeArray); i++ {
		if !isAlphaWithRune(runeArray[i-1]) {
			if runeArray[i] >= 'a' && runeArray[i] <= 'z' {
				runeArray[i] -= 32
			}
		} else {
			if runeArray[i] >= 'A' && runeArray[i] <= 'Z' {
				runeArray[i] += 32
			}
		}
	}
	return string(runeArray)
}

func isAlphaWithRune(r rune) bool {
	return (r >= 'a' && r <= 'z') || (r >= 'A' && r <= 'Z') || (r >= '0' && r <= '9')
}
```