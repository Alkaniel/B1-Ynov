#B1 #go #ytrack #ymmersion #required

### Instructions
Write a **program** that prints the name of the program.

Example of output :

```console
student/piscine/printprogramname$ go build main.go
student/piscine/printprogramnane$ ./main
main
student/piscine/printprogramname$ go build
student/piscine/printprogramname$ ./printprogramname | cat -e
printprogramname$
student/piscine/printprogramname$ go build -o Nessy
student/piscine/printprogramname$ ./Nessy
Nessy
student/piscine/printprogramname$
```

### Solution

```go
/** En fait os.Args marche comme une liste qui montre tous les arguments mis en commande. Le nom du programme est le premiers des argument. 
Ici comme Ytrack demande retirer le chemin et juste d'afficher le nom, j'ai simplement retiré 2 charactère au début du nom.
Puis j'ai fait une boucle pour print les charactère un par un (comme seulement printrune est autorisé) */

package main

import (
	"os"

	"github.com/01-edu/z01"
)

func main() {
	programName := os.Args[0]
	for _, r := range programName[2:] {
		z01.PrintRune(r)
	}
	z01.PrintRune('\n')
}

```
