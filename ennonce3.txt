import copy

def saisie_interactive_MyPC():
    """
    Création et initialisation interactive du dictionnaire My_PC.
    On demande d'abord le nombre de PC à renseigner, puis pour chacun,
    on demande les 5 paramètres.
    """
    My_PC = {}
    n = int(input("Combien de PC souhaitez-vous décrire ? "))
    for i in range(1, n+1):
        pc_id = "ID_PC_" + str(i)
        print(f"\nSaisie des informations pour {pc_id}:")
        processeur = input("Processeur : ")
        ram = int(input("Quantité de RAM (en Go) : "))
        stockage = int(input("Quantité de stockage (en Go) : "))
        carte_graphique = input("Carte graphique : ")
        os = input("Système d'exploitation : ")
        My_PC[pc_id] = {
            "processeur": processeur,
            "RAM": ram,
            "stockage": stockage,
            "carte_graphique": carte_graphique,
            "OS": os
        }
        # Message indiquant la fin de la saisie pour ce PC
        print(f"---- Fin de la saisie pour {pc_id} ----")
    return My_PC

def afficher_cles_ou_valeurs(My_PC, afficher_cles=True):
    """
    Afficher par une fonction paramétrable les clés ou les valeurs de My_PC.
    Si afficher_cles = True, affiche les clés (i.e. les ID des PC)
    Si afficher_cles = False, affiche les valeurs (i.e. les dicts des PC)
    """
    if afficher_cles:
        for k in My_PC.keys():
            print(k)
    else:
        for v in My_PC.values():
            print(v)

def extraire_cles_dans_liste(My_PC):
    """
    Extraire les clés de My_PC dans une liste.
    """
    return list(My_PC.keys())

def extraire_valeurs_dans_liste(My_PC):
    """
    Extraire les valeurs de My_PC dans une liste.
    """
    return list(My_PC.values())

def corriger_RAM(My_PC, pc_id, nouvelle_RAM):
    """
    Correction de la quantité de RAM pour un PC spécifique.
    """
    if pc_id in My_PC:
        My_PC[pc_id]["RAM"] = nouvelle_RAM
    else:
        print("PC introuvable.")

def trier_par_stockage(My_PC):
    """
    Retourne un nouveau dictionnaire My_PC trié selon la quantité de stockage.
    Le tri s'effectue par ordre croissant de stockage.
    """
    items = list(My_PC.items())
    items.sort(key=lambda x: x[1]["stockage"])  # tri sur la valeur "stockage"
    My_PC_tries = {k: v for k, v in items}
    return My_PC_tries

def inverser_parametres(My_PC, pc_id, param1, param2):
    """
    Inverse deux paramètres au sein du dictionnaire d'un PC donné.
    """
    if pc_id in My_PC:
        if param1 in My_PC[pc_id] and param2 in My_PC[pc_id]:
            My_PC[pc_id][param1], My_PC[pc_id][param2] = My_PC[pc_id][param2], My_PC[pc_id][param1]
        else:
            print("L'un des paramètres spécifiés n'existe pas dans ce PC.")
    else:
        print("PC introuvable.")

def sauvegarder_dans_CP_MyPC(My_PC):
    """
    Sauvegarde de My_PC dans un autre dictionnaire CP_MyPC (copie profonde).
    """
    CP_MyPC = copy.deepcopy(My_PC)
    return CP_MyPC

def pc_le_plus_performant(My_PC):
    """
    Affiche le PC le plus performant de My_PC.
    On définit la performance par la RAM, puis par le stockage.
    """
    if not My_PC:
        print("My_PC est vide.")
        return
    
    pc_id, pc_val = max(My_PC.items(), key=lambda x: (x[1]["RAM"], x[1]["stockage"]))
    print("Le PC le plus performant est :", pc_id)
    print("Détails :", pc_val)

# Exemple d'utilisation :
if __name__ == "__main__":
    My_PC = saisie_interactive_MyPC()
    
    print("\nClés de My_PC :")
    afficher_cles_ou_valeurs(My_PC, afficher_cles=True)
    
    print("\nValeurs de My_PC :")
    afficher_cles_ou_valeurs(My_PC, afficher_cles=False)
    
    liste_cles = extraire_cles_dans_liste(My_PC)
    liste_valeurs = extraire_valeurs_dans_liste(My_PC)
    print("\nListe des clés :", liste_cles)
    print("Liste des valeurs :", liste_valeurs)
    
    # Exemple de correction de la RAM pour le premier PC (si existe)
    if liste_cles:
        corriger_RAM(My_PC, liste_cles[0], 32)
    
    # Tri par stockage
    My_PC_tries = trier_par_stockage(My_PC)
    print("\nMy_PC trié par stockage :", My_PC_tries)
    
    # Inversion de deux paramètres pour le premier PC (si param existent)
    if liste_cles:
        inverser_parametres(My_PC, liste_cles[0], "processeur", "carte_graphique")
    
    # Sauvegarde dans CP_MyPC
    CP_MyPC = sauvegarder_dans_CP_MyPC(My_PC)
    print("\nCP_MyPC :", CP_MyPC)
    
    # PC le plus performant
    pc_le_plus_performant(My_PC)
