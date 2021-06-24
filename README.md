# Motifcreateprint
Créer un motif avec des prints 
Beaucoup de nombres dans tous les sens avec cet exercice mais au final vous allez voir que c'est assez simple.

Le but de cet exercice était d'afficher une moitié de losange :

    *
    **
    ***
    ****
    *****
    ******
    *******
    ********
    *******
    ******
    *****
    ****
    ***
    **
    *

Nous avons donc besoin d'afficher le symbole contenu dans la variable 'symbole' 1 fois, puis 2, puis 3 etc, jusqu'à la valeur du nombre contenu dans la variable n. Il va donc falloir dans un premier temps incrémenter le nombre de fois que l'on affiche le symbole, puis dans un deuxième temps, décrémenter cette variable pour revenir à 1.

L'objectif est donc de créer une première liste allant de 1 jusqu'au nombre n :

    >>> n = 8
    >>> liste = range(1, n+1)
    >>> print(liste)
    [1, 2, 3, 4, 5, 6, 7, 8]

La deuxième valeur indiquée dans la fonction range est n+1 car la fonction range est exclusive. Il faut donc indiquer 9 (n+1) si l'on veut avoir le nombre 8 dans la liste. La première valeur que nous indiquons à la fonction range est 1 puisque nous voulons commencer la liste à partir du nombre 1.

Deuxièmement, il nous faut une liste qui cette fois-ci, commence à 7 (n-1, puisque le nombre 8 est déjà dans la première liste, nous n'en n'avons pas besoin une seconde fois). La liste doit se rendre jusqu'à 1 et décrémenter à chaque fois.
Pour cela, nous passons le nombre -1 en troisième paramètre à la fonction range, afin d'avoir une liste décrémenté.
On part donc de 7 (8-1), pour aller jusqu'à 1 (on indique donc 0 en deuxième paramètre à la fonction range car là encore, cette fonction est exclusive).

    >>> n = 8
    >>> liste = range(n-1, 0, -1)
    >>> print(liste)
    [7, 6, 5, 4, 3, 2, 1]

Nous additionnons ensuite ces deux listes ensemble, en prenant le soin de les convertir en liste car nous ne pouvons pas ajouter deux objets range l'un avec l'autre :

    >>> nombres = list(range(1, n+1)) + list(range(n-1, 0, -1))
    >>> print(nombres)
    [1, 2, 3, 4, 5, 6, 7, 8, 7, 6, 5, 4, 3, 2, 1]

Nous avons donc maintenant la liste qui va nous permettre d'afficher le bon nombre de symboles à chaque itération. Il ne reste donc plus qu'à boucler dans cet liste et afficher le symbole multiplié par le nombre à chaque itération de la boucle :

    for i in nombres:
        print(symbole*i)

On va donc printer le symbole 1 fois, puis 2, puis 3... jusqu'à 8, et ensuite redescendre à 7, 6, 5... jusqu'à 1.
