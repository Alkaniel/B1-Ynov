#B1 #go #ytrack #ymmersion #required

### Instructions
Write a program that prints the arguments received in the command line.

Example of output :

```console
$ go run . choumi is the best cat
choumi
is
the
best
cat
$
```

### Solution 

```go
/** Ici j'ai fait une double boucle, la première parcours tous mes arguments de commandes.
J'ai juste retiré 1 à os.Args pour ne pas comptabiliser le nom (pas demandé).
Puis dans cette boucle, j'ai une autre boucle qui parcours le parametre pour le print rune par rune. */
package main

import (
	"os"

	"github.com/01-edu/z01"
)

func main() {
	for _, params := range os.Args[1:] {
		for _, char := range params {
			z01.PrintRune(char)
		}
		z01.PrintRune('\n')
	}
}

```
