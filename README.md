# TP Scripting Python - ESGI SRC3

Ce dépôt contient les sujets et le code source du TP de Scripting Python. L’objectif est de manipuler et d’approfondir les opérations fondamentales sur les chaînes de caractères, les listes et les dictionnaires en Python 3.x.

## Contenu du TP

Le TP se décompose en trois énoncés :

### Énoncé 1 : Manipulation de chaînes (10 points)

1. Créer et initialiser une chaîne de caractères `MaChaine = "abcdefghijklmnopqrstuvwxyz" * N` avec `N ≥ 5`.
2. Afficher `MaChaine`.
3. Extraire les 17 derniers caractères de `MaChaine` dans `TaChaine`.
4. Transformer `MaChaine` pour alterner un caractère minuscule et un caractère majuscule.
5. Inverser `MaChaine` et l’afficher.
6. Construire une pyramide à partir de `TaChaine` et l’afficher.
7. Rechercher une sous-chaîne (taille paramétrable) dans `TaChaine` et afficher sa taille.
8. Transformer `TaChaine` en liste triée puis l’afficher.

### Énoncé 2 : Manipulation de listes (10 points)

1. Créer et initialiser une liste `liste1` d’entiers (taille > 20).
2. Créer `liste2` contenant tous les entiers impairs de `liste1`.
3. Afficher `liste1` et `liste2` triées dans l’ordre décroissant.
4. Ajouter un ou plusieurs entiers à `liste1` (en fin de liste ou à un index donné).
5. Supprimer toutes les occurrences d’un entier donné dans `liste1`.
6. Créer `liste3` avec des éléments aléatoires pris dans `liste1` et `liste2`.
7. Inverser n’importe quelle liste (dont `liste3`) via une fonction.
8. Créer une fonction retournant une liste contenant deux sous-listes : 
   - `l_pairs` : éléments d’indices pairs de `liste2`.
   - `l_impairs` : éléments d’indices impairs de `liste1`.
9. Fournir une trace d’exécution claire et commentée.

### Énoncé 3 : Manipulation de dictionnaires (20 points)

1. Création et initialisation interactive du dictionnaire `My_PC` décrivant plusieurs PC (5 paramètres, ex. : processeur, RAM, stockage…).
2. Afficher les clés de `My_PC` via une fonction paramétrable.
3. Afficher les valeurs de `My_PC` via une fonction paramétrable.
4. Extraire les clés de `My_PC` dans une liste via une fonction.
5. Extraire les valeurs de `My_PC` dans une liste via une fonction.
6. Corriger la quantité de RAM via une fonction.
7. Trier `My_PC` selon la quantité de stockage via une fonction.
8. Inverser deux paramètres du dictionnaire via une fonction.
9. Sauvegarder `My_PC` dans `CP_MyPC` via une fonction.
10. Afficher le PC le plus performant de `My_PC` via une fonction (définir les critères de performance).

## Organisation du code

- Chaque énoncé peut être implémenté dans un fichier Python distinct.
- Utilisez des fonctions pour chacune des opérations demandées.
- Commentez votre code afin de le rendre lisible.
- Fournissez la trace d’exécution pour l’Énoncé 2 (et éventuellement pour les autres).

## Prérequis

- Python 3.x installé
- Éditeur de code ou IDE (PyCharm, VSCode, etc.)

## Exécution

Pour exécuter le code d’un énoncé, ouvrez votre terminal et lancez :

```bash
python3 nom_du_script.py
```

## Contribuer

Les contributions ne sont pas demandées dans le cadre de ce TP, mais vous pouvez proposer des améliorations ou signaler des problèmes en ouvrant une *Issue* ou une *Pull Request*.

## Licence

Ce projet est à usage pédagogique et ne fait l’objet d’aucune licence spécifique.
