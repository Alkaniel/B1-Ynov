#B1 #ytrack #ymmersion #go #required 

## Instructions
**Write a function that prints in ascending order and on a single line: all possible combinations of two different two-digit numbers.
These combinations are separated by a comma and a space.

## Usage 

```Go
package main

import "piscine"

func main() {
	piscine.PrintComb2()
}
```

```
$ go run . | cat -e
00 01, 00 02, 00 03, ..., 00 98, 00 99, 01 02, 01 03, ..., 97 98, 97 99, 98 99$
$
```

## Solution & Explication

```go
package piscine

import "github.com/01-edu/z01"

/** PrintComb2 est une session de boucles. Je n'ai pas pu l'expliquer autrement. En prenant combre que les 4 chiffres sont listés a-b c-d, on fait une boucle l'une dans l'autre et on imprime à la boucle d.
On oublie pas de check si la combi 98 99 est là pour ajouter ',' & ' ' et en sortie de d on met d = '0'*/

func PrintComb2() {
	for a := '0'; a <= '9'; a = a + 1 {
		for b := '0'; b <= '9'; b = b + 1 {
			d := b + 1
			for c := a; c <= '9'; c = c + 1 {
				for ; d <= '9'; d = d + 1 {
					z01.PrintRune(a)
					z01.PrintRune(b)
					z01.PrintRune(' ')
					z01.PrintRune(c)
					z01.PrintRune(d)
					if a < '9' || b < '8' || c < '9' || d < '9' {
						z01.PrintRune(',')
						z01.PrintRune(' ')
					}
				}
				d = '0'
			}
		}
	}
	z01.PrintRune('\n')
}
```

