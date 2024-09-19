#B1 #go #ytrack #ymmersion #required

### Instructions
Write a program that prints the arguments received in the command line in reverse order.

Example of output :

```console
$ go run . choumi is the best cat
cat
best
the
is
choumi
$
```

### Solution 

```go
/** J'ai vraiment besoin d'expliquer ?
J'ai fait commencé mon index au nombre d'arguments - 1 (pour éviter le OutOfList)
Puis une boucle tant que mon index n'a pas atteint 0, qui incremente une autre boucle qui
print mon denier paramètre rune par rune.
La première boucle fait ensuite index-- et passe à la ligne.*/


package main
import (
	"os"

	"github.com/01-edu/z01"
)

func main() {
	args := os.Args[1:]
	argsIndex := len(args) - 1
	for argsIndex >= 0 {
		for _, char := range args[argsIndex] {
			z01.PrintRune(char)
		}
		argsIndex--
		z01.PrintRune('\n')
	}
}
```
