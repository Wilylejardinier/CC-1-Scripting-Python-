def saisir_entier():
    while True:
        try:
            val = int(input("Entrez un entier N (>=5) : "))
            if val >= 5:
                return val
            else:
                print("N doit être supérieur ou égal à 5.")
        except ValueError:
            print("Saisie invalide. Veuillez entrer un entier.")

def creation_chaine(N):
    """Crée la chaine de caractères MaChaine."""
    return "abcdefghijklmnopqrstuvwxyz" * N

def afficher_chaine(chaine):
    """Affiche la chaine passée en argument."""
    print(chaine)

def extraire_17_derniers_car(chaine):
    """Recopie les 17 derniers caractères de MaChaine dans TaChaine."""
    return chaine[-17:]

def alterner_maj_min(chaine):
    """Transforme la chaine afin d'alterner minuscule/majuscule."""
    # Indice pair : caractère minuscule, indice impair : caractère majuscule
    res = []
    for i, c in enumerate(chaine):
        if i % 2 == 0:
            # positions paires : minuscule
            res.append(c.lower())
        else:
            # positions impaires : majuscule
            res.append(c.upper())
    return "".join(res)

def inverser_chaine(chaine):
    """Inverse la chaine et la retourne."""
    return chaine[::-1]

def construire_pyramide(chaine):
    """Construit une pyramide à partir de TaChaine et la retourne en tant que liste de lignes."""
    lignes = []
    for i in range(1, len(chaine)+1):
        lignes.append(chaine[:i])
    return lignes

def afficher_pyramide(pyramide):
    """Affiche la pyramide."""
    for ligne in pyramide:
        print(ligne)

def rechercher_sous_chaine(chaine, taille):
    """Recherche une sous-chaine de taille donnée (au début par exemple) dans TaChaine."""
    if taille <= len(chaine):
        sous_chaine = chaine[:taille]
        return sous_chaine
    else:
        return None  # ou chaine si on souhaite autre traitement

def trier_chaine(chaine):
    """Transforme TaChaine en une liste triée puis la retourne."""
    lst = list(chaine)
    lst.sort()
    return lst

##############################
# Code principal (main) :
##############################

if __name__ == "__main__":
    # 1. Création et initialisation de MaChaine
    N = saisir_entier()
    MaChaine = creation_chaine(N)

    # 2. Afficher MaChaine
    print("MaChaine initiale:")
    afficher_chaine(MaChaine)

    # 3. Recopier les 17 derniers caractères dans TaChaine
    TaChaine = extraire_17_derniers_car(MaChaine)
    print("\nTaChaine (17 derniers caractères de MaChaine):")
    afficher_chaine(TaChaine)

    # 4. Transformer MaChaine pour alterner minuscule/majuscule
    MaChaine = alterner_maj_min(MaChaine)
    print("\nMaChaine après transformation (alternance min/maj):")
    afficher_chaine(MaChaine)

    # 5. Inverser MaChaine puis l’afficher
    MaChaine_inversee = inverser_chaine(MaChaine)
    print("\nMaChaine inversée:")
    afficher_chaine(MaChaine_inversee)

    # 6. Construire une pyramide avec TaChaine puis l’afficher
    print("\nPyramide construite avec TaChaine:")
    pyramide = construire_pyramide(TaChaine)
    afficher_pyramide(pyramide)

    # 7. Rechercher une sous-chaine dont la taille est paramétrable
    taille_sous_chaine = int(input("\nEntrez la taille de la sous-chaine à extraire de TaChaine: "))
    sous_chaine = rechercher_sous_chaine(TaChaine, taille_sous_chaine)
    if sous_chaine is not None:
        print("Sous-chaine extraite:", sous_chaine)
        print("Taille de la sous-chaine:", len(sous_chaine))
    else:
        print("La taille demandée est supérieure à la longueur de TaChaine.")

    # 8. Transformer TaChaine en une liste triée puis l'afficher
    TaChaine_triee = trier_chaine(TaChaine)
    print("\nTaChaine transformée en liste triée:")
    print(TaChaine_triee)
