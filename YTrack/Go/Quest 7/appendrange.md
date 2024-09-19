#B1 #go #ytrack #ymmersion #required

### Instructions
Write a function that takes an int min and an int max as parameters. The function should return a slice of ints with all the values between the min and max.

Min is included, and max is excluded.

If min is greater than or equal to max, a nil slice is returned.

make is not allowed for this exercise.

### Expected function
```go
func AppendRange(min, max int) []int {

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
	fmt.Println(piscine.AppendRange(5, 10))
	fmt.Println(piscine.AppendRange(10, 5))
}
```
And its output :

```Console
$ go run .
[5 6 7 8 9]
[]
$
```

### Solution

```go
/** Ici, j'ai initalisé une liste de int, qui sera retourné à la fin.
Si mon "minimum" en constructeur, est plus grand que mon maxi, je retourne juste le resultat (vide).
Sinon je créer une boucle ou j'append le resultat, en soit ça fait comme result = result + i append. */

package piscine

func AppendRange(min, max int) []int {
	var result []int
	if min > max {
		return result
	}
	for i := min; i < max; i++ {
		result = append(result, i)
	}
	return result
}
```
