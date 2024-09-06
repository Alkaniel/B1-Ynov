#B1 #go #ytrack #ymmersion #required 

## Instructions
**Write a program that prints the decimal digits in ascending order (from `0` to `9`) on a single line.
A line is a sequence of characters preceding the end of line character (`'\n'`).

## Usage 
```
$ go run . 0123456789 $
```

## Solution & Explications 

``` go

/** Same as printalphabet. Here the starting ASCII number is 48 for '1' and we replace the end condition with 10 as we ask 10 numbers*/
func main() {
    var startingASCIINumber int = 48

    for i := 0; i < 10; i++ {
        z01.PrintRune(rune(startingASCIINumber + i))
    }
    z01.PrintRune('\n')
}
```


