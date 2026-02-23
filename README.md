 la fonction pour ajouter un mot :
# Fonction ajouter mot
def ajouter_mot():
    fr = entree_fr.get().lower()
    en = entree_en.get().lower()

    if fr == "" or en == "":
        messagebox.showwarning("Attention", "Remplir les deux champs")
        return

    try:
        cursor.execute("INSERT INTO dictionnaire VALUES (?, ?)", (fr, en))
        conn.commit()
        messagebox.showinfo("Succès", "Mot ajouté !")
        entree_fr.delete(0, tk.END)
        entree_en.delete(0, tk.END)
    except:
        messagebox.showerror("Erreur", "Mot déjà existant")
bouton Ajouter :
tk.Button(app, text="Ajouter",
          command=ajouter_mot,
          bg="yellow").pack(pady=5)
