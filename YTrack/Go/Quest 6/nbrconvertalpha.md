### Instructions

Write a program that prints the corresponding letter in the n position of the latin alphabet, where n is each argument received.

For example 1 matches a, 2 matches b, etc. If n does not match a valid position of the alphabet or if the argument is not an integer, the program should print a space (" ").

A flag --upper should be implemented. When used, the program prints the result in upper case. The flag will always be the first argument.

### Usage

```console
$ go run .
$ go run . 8 5 12 12 15 | cat -e
hello$
$ go run . 12 5 7 5 14 56 4 1 18 25 | cat -e
legen dary$
$ go run . 32 86 h | cat -e
   $
$ go run . --upper 8 5 25
HEY$
$
```

### Solution

```go
/** Pour cette exo, j'ai retiré le nom (Vous allez voir que je le retire très souvent).
Et j'ai créer un boolean par défaut à false pour les Majs.
Si du coup j'ai pas d'argument, on ne peux pas les prints donc je return.
Si mon premier argument, c'est "--uper", je change le boolean pour true.
Après j'entre dans une boucle sur mes parametres, si l'index est 0 et que les caps sont activés, je passe
Après je convertis mes paramètres (strings) en int via un Atoi.
Si le nombres est plus grand ou plus petit que l'alphabet (O -> 26) je print un ' '.
Sinon je regarde si c'est des caps, où je commence à la rune A.
Sinon je commence à la rune a. Et bien sur je récupère ma valeur - 1 car 1 = a ou A.
Et je print ça. */

package main

import (
	"os"

	"github.com/01-edu/z01"
)

func Atoi(s string) int {
	lenS := len(s)
	nbr := 0

	for i := 0; i < lenS; i++ {
		if lenS == 1 {
			return ElBasicAtoi2(s)
		} else if (s[0] == '-' && s[1] == '-') || (s[0] == '+' && s[1] == '+') {
			return 0
		} else if s[0] == '+' {
			return ElBasicAtoi2(s[1:])
		} else if s[0] == '-' {
			nbr = ElBasicAtoi2(s[1:])
			return -nbr
		} else {
			return ElBasicAtoi2(s)
		}
	}
	return nbr
}

func ElBasicAtoi2(s string) int {
	var nbr int
	for _, char := range s {
		if !(char >= '0' && char <= '9') {
			return 0
		}
		nbr = nbr*10 + int(char-'0')
	}
	return nbr
}

func main() {
	args := os.Args[1:]
	caps := false

	if len(args) == 0 {
		return
	}

	if args[0] == "--upper" {
		caps = true
	}

	for index, param := range args {
		if index == 0 && caps {
			continue
		}
		charAsInt := Atoi(param)
		if charAsInt == 0 || charAsInt > 26 {
			z01.PrintRune(' ')
		} else {
			if caps {
				z01.PrintRune(rune('A' + charAsInt - 1))
			} else {
				z01.PrintRune(rune('a' + charAsInt - 1))
			}
		}
	}
	z01.PrintRune('\n')
}
```
