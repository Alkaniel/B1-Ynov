#B1 #go #ytrack #ymmersion #required

### Instructions
Write a program that prints the arguments received in the command line in ASCII order.

Example of output :
```console
$ go run . 1 a 2 A 3 b 4 C
1
2
3
4
A
C
a
b
$
```

### Solution

```go
/** Ici j'ai retiré d'abord le nom au main.
Puis j'ai fait une fonction appart pour les trier pour que cela soit plus propre.
Cette fonction, c'est une fonction très basique, qui parcours en double boucle, l'index
et l'index + 1, si le premier index est plus grand que le second, il les switchs.
Ensuite je print la belle liste bien trié comme le printparams. */

package main

import (
	"os"

	"github.com/01-edu/z01"
)

func SortParams(params []string) {
	for i := 0; i < len(params)-1; i++ {
		for j := i + 1; j < len(params); j++ {
			if params[i] > params[j] {
				params[i], params[j] = params[j], params[i]
			}
		}
	}
}

func main() {
	args := os.Args[1:]
	SortParams(args)
	for _, params := range args {
		for _, char := range params {
			z01.PrintRune(char)
		}
		z01.PrintRune('\n')
	}
}

```
