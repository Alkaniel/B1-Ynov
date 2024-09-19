#B1 #go #ytrack #ymmersion #required

### Instructions
Write a function that separates the words of a string and puts them in a string slice.

The separators are spaces, tabs and newlines.

### Expected function

```go
func SplitWhiteSpaces(s string) []string {

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
	fmt.Printf("%#v\n", piscine.SplitWhiteSpaces("Hello how are you?"))
}
```
And its output :

```console
$ go run .
[]string{"Hello", "how", "are", "you?"}
$
```

### Solution

```go
/** Je commence par initaliser une liste de string et un string.
Je parcour mon string, tant qu'il ne détecte pas un espace, il print le string dans l'autre string.
Sinon il check si le mot n'est pas vide dans ce cas, il append le mot dans anwser.
En suite j'append le dernier mot dans answer et je return. */

package piscine

func SplitWhiteSpaces(s string) []string {
    var answer []string
    var mot string
    for _, r := range s {
        if r != ' ' {
            mot += string(r)
        } else {
            if mot != "" {
                answer = append(answer, mot)
                mot = ""
            }
        }
    }
    if mot != "" {
        answer = append(answer, mot)
    }

    return answer
}
```
