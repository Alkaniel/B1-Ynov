#B1 #go #ytrack #ymmersion #required

### Instructions
Write a function that takes an int min and an int max as parameters. The function must return a slice of ints with all the values between min and max.

Min is included, and max is excluded.

If min is greater than or equal to max, a nil slice is returned.

append is not allowed for this exercise.

### Usage
Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	fmt.Println(piscine.MakeRange(5, 10))
	fmt.Println(piscine.MakeRange(10, 5))
}
```

And its output :

```console
$ go run .
[5 6 7 8 9]
[]
$
```

### Solution

```go
/** Dans makerange, j'initalise pas result dès le depart.
Je le fait juste dans mon check si min > max ou je le retourne
Puis je fait un calcul de la taille en prenant la différence entre max et min.
Et en fait make, fait une liste d'une taille donnée donc j'initalise mon resultat.
Ensuite, je parcours cette liste ou le lie chaque index à une valeur qui par de min à min ++ sans atteindre le max.
Et je retourne */

func MakeRange(min, max int) []int {
	if min > max {
		var result []int
		return result
	}
	size := max - min
	result := make([]int, size)
	for i := 0; min < max; i++ {
		result[i] = min
		min++
	}
	return result
}
```

