#B1 #go #ytrack #ymmersion #optional

### Instructions

Write a program that checks the arguments for vowels.

If the arguments contain vowels (for this exercise y is not considered a vowel) the program has to "mirror" the position of the vowels in the arguments (see the examples).
If the number of arguments is less than 1, the program displays a new line ("\n").
If the arguments do not have any vowels, the program just prints the arguments.
Example of output :

```console
$ go run . "Hello World" | cat -e
Hollo Werld$
$ go run . "HEllO World" "problem solved"
Hello Werld problom sOlvEd
$ go run . "str" "shh" "psst"
str shh psst
$ go run . "happy thoughts" "good luck"
huppy thooghts guod lack
$ go run . "aEi" "Ou"
uOi Ea
$ go run .

$
```

### Solution

```go
/** Donc ici, je retire le nom du programme, j'initalise un counter de voyelles, un array, un boolean isFinal à true et un string de print.
Je fait une boucle sur mes parametres, qui a une autre boucle qui compte mes voyelles et les appends dans mon array. Tant ce n'est pas mon dernier parametre, il inclue le pametre string.
Ensuite j'initialise un index i à 0, puis une boucle sur mon string, si la rune est une voyelles (check via fonction), elle vas print celle d'avant (donc si la première, ça devient la dernière)
Et je print les autres runes si ce n'est pas une rune */

package main

import (
	"os"

	"github.com/01-edu/z01"
)

func main() {
	args := os.Args[1:]
	vCounter := 0
	vArray := []rune{}
	isFinal := true
	toPrint := ""

	for _, param := range args {
		for _, char := range param {
			if isVowel(char) {
				vArray = append(vArray, char)
				vCounter++
			}
		}
		if isFinal {
			toPrint = param
			isFinal = false
			continue
		}
		toPrint = toPrint + " " + param
	}
	i := 0
	for _, char := range toPrint {
		if isVowel(char) {
			z01.PrintRune(vArray[vCounter-i-1])
			i++
		} else {
			z01.PrintRune(char)
		}
	}
	z01.PrintRune('\n')
}

func isVowel(char rune) bool {
	if char == 'a' || char == 'A' || char == 'e' || char == 'E' || char == 'i' || char == 'I' || char == 'o' || char == 'O' || char == 'u' || char == 'U' {
		return true
	}
	return false
}
```

