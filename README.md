# Methode-nombre-magique
Utilisation du nombre magique afin de calculer une plage d'adresse IP

### Qu'est-ce que le nombre magique?
```
Le nombre magique est simplement un calcul fait à partir de l'octet significatif du masque.
Il est égal à 256 - octet significatif.
```

## Fonctionnement
* Par exemple dans notre exemple sur un masque de `255.224.0.0`
* Dans notre masque, l’octet significatif est le deuxième (255.224.0.0), soit 224
* Nous allons donc prendre le deuxième octet de notre adresse (192.168.0.1), soit 168.

* Notre nombre magique vaut donc `256 - 224 = 32`

* La première adresse du réseau sera donc le multiple du nombre magique, strictement inférieur à 168.
* Pour cela, il va falloir écrire tous les multiples du nombre magique en partant de 0 (jusqu'à 256)<br>
`0, 32, 64, 96, 128, 160, 192, 224, 256`.

* La dernière adresse du réseau sera le multiple suivant, moins 1.
* Le multiple suivant est `192`. Auquel on enlève 1 pour trouver 191
* La première adresse de la plage est donc `192.160.0.0` et la dernière `192.191.255.255`.

![image](https://user-images.githubusercontent.com/83721477/167442993-45beded6-3530-44bf-92df-d56e32e3b538.png)
