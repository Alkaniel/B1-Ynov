#B1 #go #ytrack #ymmersion #required 
### Instructions

Write a function which prints the digits of an `int` passed in parameter in ascending order. All possible values of type `int` have to go through, excluding negative numbers. Conversion to `int64` is not allowed.

### Expected function

```go
func PrintNbrInOrder(n int) {

}
```

### Usage

Here is a possible program to test your function :

```go
package main

import "piscine"

func main() {
	piscine.PrintNbrInOrder(321)
	piscine.PrintNbrInOrder(0)
	piscine.PrintNbrInOrder(321)
}
```

And its output :

```console
$ go run . | cat -e
1230123$
$
```

### Solution

```go
package piscine

/** Ici on gère d'abord 0. Après je fait les nombres à 2 chiffres.
Après je trie tout en regardant dans une double boucle lequel de i & i+1 est le plus grand puis les switch de position.
En suite dans une dernière boucle j'appelle ma première fonction PrintNbr car c'est possible sur Ytrack apparement. */

func PrintNbrInOrder(n int) {
	var arr []int
	if n == 0 {
		arr = append(arr, 0)
	}
	for n > 0 {
		arr = append(arr, n%10)
		n = n / 10
	}
	for i := 0; i < len(arr); i++ {
		for j := i + 1; j < len(arr); j++ {
			if arr[i] > arr[j] {
				arr[i], arr[j] = arr[j], arr[i]
			}
		}
	}
	for i := 0; i < len(arr); i++ {
		PrintNbr(arr[i])
	}
}
```