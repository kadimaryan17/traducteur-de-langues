 la fonction pour ajouter un mot :
# Fonction ajouter mot
def ajouter_mot():
    fr = entree_fr.get().lower()
    en = entree_en.get().lower()

    if fr == "" or en == "":
        messagebox.showwarning("Attention", "Remplir les deux champs")
        return

    
