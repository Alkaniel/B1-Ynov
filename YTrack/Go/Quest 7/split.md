#B1 #go #ytrack #ymmersion #required

### Instructions
Write a function that receives a string and a separator and returns a slice of strings that results of splitting the string s by the separator sep.

### Expected function

```go
func Split(s, sep string) []string {

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
	s := "HelloHAhowHAareHAyou?"
	fmt.Printf("%#v\n", piscine.Split(s, "HA"))
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
/** Je commencei ici par initaliser une size à 0.
Puis je fais une boucle pour avoir la taille du séparateur.
Ensuite je fais une autre taille que je set à la taille du string.
Ensuite encore une boucle, de taille de la size de mon string, moins celui de mon separateur.
Si je trouve le séparateur, je le replace par un espace.
Puis je retire le séparateur à l'autre size
et je retoune mon splitwhitespaces car on travaille finalement avec les espaces */

package piscine

func Split(s, sep string) []string {
	size := 0
	for i := range sep {
		size = i + 1
	}
	size2 := 0
	for i := range s {
		size2 = i + 1
	}
	for i := 0; i < size2-size; i++ {
		if s[i:i+size] == sep {
			s = s[:i] + " " + s[i+size:]
			size2 -= size
		}
	}
	return SplitWhiteSpacesImportCarYTrackEstCasseCouille(s)
}

func SplitWhiteSpacesImportCarYTrackEstCasseCouille(s string) []string {
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
