#B1 #go #ytrack #ymmersion #required

### Instructions

This program should :

* Insert the string given to the --insert (or -i), into the argument string, if given.
* If the flag --order (or -o) is given, order the string argument (in ASCII order).
* If there are no arguments or if the flag --help (or -h) is given, the options should be printed as in the example.
  * The short flag will have two spaces before the (-).
  * The explanation of the flag will have a tab followed by a space before the beginning of the sentence (This flag...).
 
Example of output :
 
```console
$ go run . --insert=4321 --order asdad
1234aadds
$ go run . --insert=4321 asdad
asdad4321
$ go run . asdad
asdad
$ go run . --order 43a21
1234a
$ go run .
--insert
  -i
         This flag inserts the string into the string passed as argument.
--order
  -o
         This flag will behave like a boolean, if it is called it will order the argument.
$ go run . -h
--insert
  -i
         This flag inserts the string into the string passed as argument.
--order
  -o
         This flag will behave like a boolean, if it is called it will order the argument.
$ go run . --help
--insert
  -i
         This flag inserts the string into the string passed as argument.
--order
  -o
         This flag will behave like a boolean, if it is called it will order the argument.
```

### Solution

```go
/** J'ai commencé par directement créer une fonction de printhelp pour me simplifier la vie qui me print le truc
help.
Puis bien sûr je retire le nom du programmes de mes arguments.
Parse Flags() c'est simplement une lsite flags où j'ai dégagé --help ou -help.
J'ai ensuite fait un string à print et set un boolean de tri à false pour le moment.
Ensuite je parcours mes flags, grace à ma fonction d'index, si il détecte -i parmis mes flags, met le truc à inserer dans le string de print.
Si l'index découvre "-o", il active mon boolean de tri.

Ensuite je met tous mes args dans mon string de print.
Si mon boolean n'est pas actif, il le print
Sinon je le tris le tout et je print. */

package main

import (
	"fmt" 
	"os"
)

func Index(s string, toFind string) int {
	if len(toFind) == 0 {
		return 0
	}
	if len(s) == 0 {
		return -1
	}
	for i := 0; i < len(s); i++ {
		if s[i] == toFind[0] {
			if len(toFind) == 1 {
				return i
			}
			if len(s[i:]) >= len(toFind) {
				if s[i:i+len(toFind)] == toFind {
					return i
				}
			}
		}
	}
	return -1
}

func printHelp() {
	fmt.Printf("--insert\n  -i\n\t This flag inserts the string into the string passed as argument.\n--order\n  -o\n\t This flag will behave like a boolean, if it is called it will order the argument.\n")
	os.Exit(0)
}

func parseFlags(args []string) []string {
	var flags []string
	for i, arg := range args {
		if arg == "--help" || arg == "-h" {
			printHelp()
		}
		if len(arg) != 0 {
			if arg[0] == '-' {
				flags = append(flags, arg)
				args = append(args[:i], args[i:]...)
			}
		}
	}
	return flags
}

func main() {
	if len(os.Args) < 2 {
		printHelp()
	}
	args := os.Args[1:]
	flags := parseFlags(args)
	var print_s string
	var sort bool = false
	for _, flag := range flags {
		if Index(flag, "-i") != -1 {
			print_s += flag[Index(flag, "=")+1:]
		}
		if Index(flag, "-o") != -1 {
			sort = true
		}
	}
	print_s = args[len(args)-1] + print_s
	if !sort {
		fmt.Println(print_s)
	} else {
		var runes []rune
		for _, r := range print_s {
			runes = append(runes, r)
		}
		for i := 0; i < len(runes)-1; i++ {
			for j := i + 1; j < len(runes); j++ {
				if runes[i] > runes[j] {
					runes[i], runes[j] = runes[j], runes[i]
				}
			}
		}
		fmt.Println(string(runes))
	}
}

```
