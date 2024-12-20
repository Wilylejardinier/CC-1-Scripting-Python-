import random

# 1. Création et initialisation d'une liste liste1 d'entiers de taille > 20
#    Pour l'exemple, on va créer une liste de 25 entiers allant de 1 à 25.
def creer_liste1(taille=25):
    # On crée une liste d'entiers [1, 2, 3, ..., taille]
    return list(range(1, taille+1))

# 2. Création de liste2 avec les entiers impairs de liste1
def extraire_impairs(liste):
    return [x for x in liste if x % 2 == 1]

# 3. Fonction pour afficher deux listes triées dans un ordre décroissant
def afficher_listes_decroissantes(l1, l2):
    # Tri en ordre décroissant sans altérer les listes originales
    l1_sorted = sorted(l1, reverse=True)
    l2_sorted = sorted(l2, reverse=True)
    print("Liste1 triée décroissante :", l1_sorted)
    print("Liste2 triée décroissante :", l2_sorted)

# 4. Fonction ajoutant un ou plusieurs entiers à liste1
#    On peut soit ajouter à la fin, soit à un indice spécifique.
def ajouter_elements(liste, elements, index=None):
    # elements doit être une liste d'entiers
    # Si index est None, on ajoute à la fin
    # Sinon, on insère à partir de cet index
    if index is None:
        liste.extend(elements)
    else:
        # On insère les éléments à partir de l'indice spécifié
        # Pour insérer plusieurs éléments à un indice donné, on peut faire un slice
        liste[index:index] = elements

# 5. Fonction supprimant de liste1 toutes les occurrences d’un entier donné
def supprimer_toutes_occurrences(liste, valeur):
    # Filtrer la liste pour garder seulement les éléments != valeur
    return [x for x in liste if x != valeur]

# 6. Création de liste3 avec des éléments aléatoires de liste1 et liste2
#    On mélange liste1 et liste2, et on pioche un certain nombre d'éléments au hasard.
def creer_liste3(liste1, liste2, taille=10):
    # On fusionne les deux listes
    fusion = liste1 + liste2
    # On mélange la liste fusionnée
    random.shuffle(fusion)
    # On prend les 'taille' premiers éléments après mélange
    return fusion[:taille]

# 7. Fonction qui inverse une liste
def inverser_liste(liste):
    return liste[::-1]

# 8. Fonction qui prend liste1 et liste2 en paramètres et renvoie une liste contenant
#    deux sous-listes : [l_pairs, l_impairs]
#    l_pairs = éléments d'indices pairs de liste2 (indices 0, 2, 4, ...)
#    l_impairs = éléments d'indices impairs de liste1 (indices 1, 3, 5, ...)
def extraire_pairs_impairs(liste1, liste2):
    l_pairs = [liste2[i] for i in range(len(liste2)) if i % 2 == 0]
    l_impairs = [liste1[i] for i in range(len(liste1)) if i % 2 == 1]
    return [l_pairs, l_impairs]


##############################
# Code principal (main) :
##############################

# Étape 1 : Créer et initialiser liste1
print("Étape 1 : Création de liste1")
liste1 = creer_liste1(25)  # liste de 1 à 25
print("liste1 =", liste1)

# Étape 2 : Créer liste2 avec les impairs de liste1
print("\nÉtape 2 : Création de liste2 avec les entiers impairs de liste1")
liste2 = extraire_impairs(liste1)
print("liste2 =", liste2)

# Étape 3 : Afficher les 2 listes triées dans un ordre décroissant
print("\nÉtape 3 : Affichage des deux listes dans l'ordre décroissant")
afficher_listes_decroissantes(liste1, liste2)

# Étape 4 : Ajouter des éléments à liste1
print("\nÉtape 4 : Ajout d'éléments à liste1")
print("liste1 avant ajout :", liste1)
ajouter_elements(liste1, [99, 100])  # Ajout à la fin
print("liste1 après ajout en fin :", liste1)
ajouter_elements(liste1, [50, 51], index=5)  # Ajout à l'indice 5
print("liste1 après ajout à l'indice 5 :", liste1)

# Étape 5 : Suppression de toutes les occurrences d'un entier
valeur_a_supprimer = 3
print("\nÉtape 5 : Suppression de toutes les occurrences de", valeur_a_supprimer, "dans liste1")
liste1 = supprimer_toutes_occurrences(liste1, valeur_a_supprimer)
print("liste1 après suppression des occurrences de", valeur_a_supprimer, ":", liste1)

# Étape 6 : Création de liste3 avec des éléments aléatoires pris dans liste1 et liste2
print("\nÉtape 6 : Création de liste3 aléatoire à partir de liste1 et liste2")
liste3 = creer_liste3(liste1, liste2, taille=10)
print("liste3 =", liste3)

# Étape 7 : Inversion de liste3 (et on peut appliquer la même fonction à d'autres listes)
print("\nÉtape 7 : Inversion de liste3")
liste3 = inverser_liste(liste3)
print("liste3 inversée =", liste3)

# Étape 8 : Extraire et renvoyer une liste contenant [l_pairs, l_impairs]
print("\nÉtape 8 : Extraction l_pairs et l_impairs")
l_p_i = extraire_pairs_impairs(liste1, liste2)
l_pairs, l_impairs = l_p_i[0], l_p_i[1]
print("l_pairs (éléments d'indices pairs de liste2) =", l_pairs)
print("l_impairs (éléments d'indices impairs de liste1) =", l_impairs)

print("\nProgramme terminé.")
