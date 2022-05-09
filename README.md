# Methode-nombre-magique
Utilisation du nombre magique afin de calculer une plage d'adresse IP

### Qu'est-ce que le nombre magique?
```
Le nombre magique est simplement un calcul fait à partir de l'octet significatif du masque.
Il est égal à 256 - octet significatif.
```

## Fonctionnement
Par exemple dans notre exemple sur un masque de `255.224.0.0`
On voit vite que l'octet significatif (celui où la séparation a lieu) est 224.

Notre nombre magique vaut donc `256 - 224 = 32`

Pour cela, il va falloir écrire tous les multiples du nombre magique (jusqu'à 256 bien sûr)<br>
0, 32, 64, 96, 128, 160, 192, 224, 256.

* La première adresse du réseau sera le multiple du nombre magique, inférieur ou égal à l'octet correspondant dans l'adresse.
* La dernière adresse du réseau sera le multiple suivant, moins 1.

