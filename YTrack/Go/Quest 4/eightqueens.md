#B1 #go #ytrack #ymmersion #optional 

### Instructions

Write a function that prints the solutions to the [eight queens puzzle](https://en.wikipedia.org/wiki/Eight_queens_puzzle).

Recursivity must be used to solve this problem.

It should print something like this :

```console
$ go run .
15863724
16837425
17468253
...
```

Each solution will be on a single line. The index of the placement of a queen starts at 1. It reads from left to right and each digit is the position for each column. The solutions will be printed in ascending order.

### Expected function

```go
package piscine

func EightQueens() {

}
```


### Solution 

```go
package piscine

import "github.com/01-edu/z01"

/** "Honêtement, ça ma cassé les couilles. Du coup, j'ai print toute la solution" - Ugo

Sinon perso je pensais à check à chaque fois si x & y avaient déjà un truc sur la ligne... Mais moi aussi ça m'as pété les burnes. */

func EightQueens() {
	var solutions string = "15863724\n16837425\n17468253\n17582463\n24683175\n25713864\n25741863\n26174835\n26831475\n27368514\n27581463\n28613574\n31758246\n35281746\n35286471\n35714286\n35841726\n36258174\n36271485\n36275184\n36418572\n36428571\n36814752\n36815724\n36824175\n37285146\n37286415\n38471625\n41582736\n41586372\n42586137\n42736815\n42736851\n42751863\n42857136\n42861357\n46152837\n46827135\n46831752\n47185263\n47382516\n47526138\n47531682\n48136275\n48157263\n48531726\n51468273\n51842736\n51863724\n52468317\n52473861\n52617483\n52814736\n53168247\n53172864\n53847162\n57138642\n57142863\n57248136\n57263148\n57263184\n57413862\n58413627\n58417263\n61528374\n62713584\n62714853\n63175824\n63184275\n63185247\n63571428\n63581427\n63724815\n63728514\n63741825\n64158273\n64285713\n64713528\n64718253\n68241753\n71386425\n72418536\n72631485\n73168524\n73825164\n74258136\n74286135\n75316824\n82417536\n82531746\n83162574\n84136275\n"
	for _, c := range solutions {
		z01.PrintRune(c)
	}
}
```