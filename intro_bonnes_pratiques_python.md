# Bonnes pratiques Python 

# ![logo](https://www.pngall.com/wp-content/uploads/2016/05/Python-Logo-PNG-Image.png)

Plusieurs choses sont nécessaires pour écrire un code lisible : la syntaxe, l'organisation du code, le découpage en fonctions (et possiblement en classes que nous verrons dans le chapitre 19 Avoir la classe avec les objets), mais souvent, aussi, le bon sens. Pour cela, les « PEP » peuvent nous aider.

```bash
Afin d'améliorer le langage Python, la communauté qui développe Python publie régulièrement des Python Enhancement Proposal (PEP), suivi d'un numéro. Il s'agit de propositions concrètes pour améliorer le code, ajouter de nouvelles fonctionnalités, mais aussi des recommandations sur la manière d'utiliser Python, bien écrire du code, etc.
```

1. **Indentation** 
Utiliser 4 espaces. Sur VSCode (ou autre editeur) remplacer tabulation par 4 espaces

2. **Importation des modules**  
- Utiliser  "import module"
- Une ligne par module
- import des modules en début de fichier

3. **Règles de nommage** 

- Variables, fonctions, modules sous fome snake_case :

```bash
ma_variable
fonction_test()
mon_module
```
- Constantes en majuscule :

```bash
MA_CONSTANTE
```

- Nom de classe en CamlCase : 

```bash
MaClasse
MyException
```

4. **Gestion des espaces**

- Mettre un espace avant et après un opérateur (+, -, /, ==, and, or...)
```bash
# code recommandé :
ma_variable = 3 + 7
mon_texte = "souris"
mon_texte == ma_variable
# code non recommandé :
ma_variable=3+7
mon_texte="souris"
mon_texte== ma_variable

```
- Ne pas mettre d'espace dans les accolades, parenthèses et crochets ni avant :

```bash
# code recommandé :
ma_liste[1]
mon_dico{"clé"}
ma_fonction(argument)
# code non recommandé :
ma_liste [ 1 ]
mon_dico {"clé" }
ma_fonction ( argument )
```
- On met un espace après les caractères : et , (mais pas avant) sauf pour les tranches de liste, pas d'espace.


5. **Logueur de ligne**

Une ligne de code ne doit pas dépasser 79 caractères, on peut utiliser \ pour indiquer que l'instruction continue sur la ligne suivante.
En cas de l'utilisation de la parenthèse, toutes les lignes suivantes seront concaténées à la première ligne tant que la parenthèse n'est pas fermée

6. **Lignes vides**

- 2 lignes vides avant la definition d'une fonction / classe
- 1 ligne vide avant la définition d'une méthode

7. **Commentaires**

Servent à donner des explications sur l'utilité du code, penser à les mettre à jour en cas de modification du code.

- #: commentaire sur une ligne
- """ ... """ pour une commentaire sur plusieurs lignes
- Il est recommandé de les rédiger en anglais
- Si commentaires en anglais, variables, fonctions... en anglais également.
- Eviter les commentaires sur la même ligne que le code

8. **Les docstrings**

- Première ligne sert à décrire de façon brève
- Après un saut de ligne on renseigne la documentation du code/bloc de code
- Il est recommande d'utiliser """...""" au lieu de '''...'''
    - Indiquer ce que fait la fonction / méthode
    - Indiquer ce qu'elle prend en argument
    - Indiquer de ce qu'elle renvoie
ex : 

```bash
def multiplie_nombres(nombre1, nombre2):
    """Multiplication de deux nombres entiers.

    Cette fonction ne sert pas à grand chose.

    Parameters
    ----------
    nombre1 : int
        Le premier nombre entier.
    nombre2 : int
        Le second nombre entier.

        Avec une description plus longue.
        Sur plusieurs lignes.

    Returns
    -------
    int
        Le produit des deux nombres.
    """
    return nombre1 * nombre2
```
9. **Outils de controle de qualité de code**

Sous Linux : 

```bash
$ sudo apt install pycodestyle pydocstyle pylint
$ pycodestyle script.py
$ pydocstyle script.py
$ pylint script.py
```
10. **Quelques conseils sur la conception d'un script**

- Réfléchissez avec un papier, un crayon... et un cerveau (voire même plusieurs) ! Reformulez avec des mots en français (ou en anglais) les consignes qui vous ont été données ou le cahier des charges qui vous a été communiqué. Dessinez ou construisez des schémas si cela vous aide.
- Découpez en fonctions chaque élément de votre programme. Vous pourrez ainsi tester chaque élément indépendamment du reste. Pensez à écrire les docstrings en même temps que vous écrivez vos fonctions.
- Quand l'algorithme est complexe, commentez votre code pour expliquer votre raisonnement. Utiliser des fonctions (ou méthodes) encore plus petites peut aussi être une solution.
- Documentez-vous. L'algorithme dont vous avez besoin existe-t-il déjà dans un autre module ? Existe-t-il sous la forme de pseudo-code ? De quels outils mathématiques avez-vous besoin dans votre algorithme ?
- Si vous créez ou manipulez une entité cohérente avec des propriétés propres, essayez de construire une classe. Jetez, pour cela, un œil au chapitre 19 Avoir la classe avec les objets.
- Utilisez des noms de variables explicites, qui signifient quelque chose. En lisant votre code, on doit comprendre ce que vous faites. Choisir des noms de variables pertinents permet aussi de réduire les commentaires.
- Quand vous construisez une structure de données complexe (par exemple une liste de dictionnaires contenant d'autres objets), documentez et illustrez l'organisation de cette structure de données sur un exemple simple.
- Testez toujours votre code sur un jeu de données simple pour pouvoir comprendre rapidement ce qui se passe. Par exemple, une séquence de 1000 bases est plus facile à gérer que le génome humain ! Cela vous permettra également de retrouver plus facilement une erreur lorsque votre programme ne fait pas ce que vous souhaitez.
- Lorsque votre programme « plante », lisez le message d'erreur. Python tente de vous expliquer ce qui ne va pas. Le numéro de la ligne qui pose problème est aussi indiqué.
- Discutez avec des gens. Faites tester votre programme par d'autres. Les instructions d'utilisation sont-elles claires ?
- Si vous distribuez votre code :
    - Rédigez une documentation claire.
    - Testez votre programme (jetez un œil aux tests unitaires).
    - Précisez une licence d'utilisation. Voir par exemple le site Choose an open source license.


