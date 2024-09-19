Une fonction **récursive** est une fonction qui s'appelle elle-même.
On définira toujours la valeur de la fonction quand la variable vaut 0.
On peut l'exprimer de cette manière :

U(_n+1_) = U(_n_) + U(_n-1_)
ou
U(_n_) = U(_n-1_) + U(_n-2_)

Exemple : 
f(0) = 3
f(x) = 5x + 3

Donc par exemple : 
f(8) = f(7) + f(6) 
f(8) = (5 * 7 + 3) + (5 * 6 + 3)
f(8) = 38 + 33
f(8) = 71

En code pour la [[Fonction Factorielle]] cela pourrait se traduire par :
```go
func recursive(n int) int {
	if n == 0 { //on retourne 1 quand n vaut 0 par convention.
		return 1
	}
	return n * recursive(n-1)
}
```
On fait bien n * n-1 * ... n-(n-1) puis on multiplie par _n-n_.
(le (n-n) vaut 0 ce qui multiplie le n final par 1, c'est la seul différence qu'il y a avec la formule de la Fonction factorielle)