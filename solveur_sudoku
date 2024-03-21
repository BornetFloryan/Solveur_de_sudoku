G_init=[[3,0,0,4,1,0,0,8,7],
       [0,0,9,0,0,5,0,6,0],
       [4,0,0,7,9,0,5,0,3],
       [0,7,3,2,4,0,0,0,0],
       [0,0,0,0,0,0,0,0,0],
       [0,0,0,0,7,8,2,4,0],
       [6,0,2,0,8,3,0,0,5],
       [0,5,0,1,0,0,3,0,0],
       [1,3,0,0,2,4,0,9,6]]

assert (type(G_init)==list), 'La grille doit être une liste !'
G=G_init.copy()

def suivant(G):
    
    """
    Fichier : Mini_Projet_n2_BORNET_Floryan_TE.py
    Nom fct: suivant(G)
    Fonction qui parcours les colonnes et les lignes de la grille à la recherche de 0.
    intput : une liste de liste
    output : ligne, colonne ou None, None
    """
    for ligne in range(len(G)):
        for colonne in range(len(G)):
            if G[ligne][colonne] == 0: 
                return ligne, colonne
    return(None,None)

def teste(ligne, colonne, n):
    
    """
    Fichier : Mini_Projet_n2_BORNET_Floryan_TE.py
    Nom fct: teste(ligne, colonne, n)
    Fonction qui vérifie si le nombre sélectionné est dans la ligne
    ou dans la colonne ou dans la grille diviser par partie de 3x3.
    intput : Des nombres entiers.
    output : False ou True.
    """

    if n in G[ligne]: #Vérifie si n est dans les lignes de la grilles.
        return False
        
    for i in range(len(G)):
        if n in [G[i][colonne]]: #Vérifie si n est dans les colonnes de la ligne.
            return False
        
    c = (colonne // 3) * 3 
    l = (ligne // 3) * 3
    
    for i in range(l, l + 3):
        for x in range(c, c + 3):
            if G[i][x] == n: #Vérifie si n est dans la grille divisé en 3x3.
                return False
    
    return True

def remplir(G):
    
    """
    Fichier : Mini_Projet_n2_BORNET_Floryan_TE.py
    Nom fct: remplir()
    Fonction qui remplie la grille de sudoku.
    intput : Une liste.
    output : True ou False.
    """
    
    assert len(G) > 0 , 'Votre liste doit contenir un nombre de liste de liste supérieur à zéro !'
    assert len(G) == 9, 'Votre liste doit contenir un nombre de liste de liste égale à neuf !'
    
    for i in range(len(G)):
        for x in range(len(G)):
            assert isinstance(G[i][x], int), "La liste G ne peut que contenir des entier..."
    
    ligne, colonne = suivant(G) 
    if ligne is None:
        return True
    
    for n in range(1, len(G)+1):
        if teste(ligne, colonne, n): #Vérifie si le chiffre est dans la liste.
            G[ligne][colonne] = n
            if remplir(G):
                return True
        G[ligne][colonne] = 0
    
    return False

def affichage_grille(G):
    
    """
    Fichier : Mini_Projet_n2_BORNET_Floryan_TE.py
    Nom fct: affiche_grille(G)
    Fonction qui affiche la grille de sudoku en plus lisible et qui divise la grille en 9 partie de 3x3.
    intput : Une liste.
    output : True ou False.
    """
    
    for ligne in range(len(G)):
        if ligne % 3 == 0 and ligne != 0: #Divise les lignes en 3.
            print("-----------------------")

        for colonne in range(len(G[0])):
            if colonne % 3 == 0 and colonne != 0: #Divise les colonnes en 3.
                print(" | ", end="")

            if colonne == 8:
                print(G[ligne][colonne])
            else:
                print(str(G[ligne][colonne]) + ' ', end="") #Met un espace entre les chiffres.

remplir(G)
affichage_grille(G)
