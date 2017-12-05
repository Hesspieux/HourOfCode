# Une implémentation de l'application bancaire

```python
class CompteBancaire:

	def __init__(self, nom, solde = 0):

		self.nom = nom
		self.solde = int(solde)
		print("Bienvenue", nom, "chez HourOfCode Bank !")
		self.afficher()

	def deposer(self, somme):

		self.solde = self.solde + somme
		self.afficher()

	def retirer(self, somme):

		self.solde = self.solde - somme;
		self.afficher()

	def afficher(self):

		print("Votre solde est :", self.solde, "€")
```

---

```python
def creer_compte_bancaire(comptes_bancaires):

	nom = input("Votre nom :")

	solde = input("Premier versement :")

	nouveau_compte_bancaire = CompteBancaire(nom, solde)

	comptes_bancaires.append(nouveau_compte_bancaire)

	return nouveau_compte_bancaire
```

---

```python
def recuperer(comptes_bancaires, nom):

	for compte_bancaire in comptes_bancaires:

		if compte_bancaire.nom == nom:

			return compte_bancaire

	print("Pas de compte bancaire trouvé pour", nom)

	demarrer(comptes_bancaires)
```

---

```python
def choisir_option_gestion(compte_bancaire):

	continuer = True

	while continuer:

		choix = input("Tapez votre choix :")
		choix = int(choix)

		if choix == 1:

			compte_bancaire.afficher()

		elif choix == 2:

			somme = input("Montant désiré :")
			somme = int(somme)
			compte_bancaire.deposer(somme)

		elif choix == 3:

			somme = input("Montant désiré :")
			somme = int(somme)
			compte_bancaire.retirer(somme)

		elif choix == 4:

			continuer = False

	print("Fermeture de session pour", compte_bancaire.nom)
```

---

```python
def gerer(compte_bancaire):

	print("##### Bonjour", compte_bancaire.nom, "#####")
	print("\n")

	print("- [1] Afficher")
	print("- [2] Déposer de l'argent")
	print("- [3] Retirer de l'argent")
	print("- [4] Fermer la session")
	print("\n")

	choisir_option_gestion(compte_bancaire)
```

---

```python
def choisir_option_demarrage():

	continuer = True
	stop = False

	while continuer:

		choix = input("Tapez votre choix :")
		choix = int(choix)

		if choix == 1:

			nouveau = creer_compte_bancaire(comptes_bancaires)
			gerer(nouveau)
			continuer = False

		elif choix == 2:

			nom = input("Votre nom :")
			compte_bancaire = recuperer(comptes_bancaires, nom)
			gerer(compte_bancaire)
			continuer = False

		elif choix == 3:

			continuer = False
			stop = True
			print("Au revoir !")

	return stop
```

---

```python
def demarrer(comptes_bancaires):

	print("###################################")
	print("#         HourOfCode Bank         #")
	print("###################################")
	print("\n")

	print("- [1] Ouvrir un nouveau compte bancaire")
	print("- [2] S'identifier")
	print("- [3] Quitter")
	print("\n")

	return choisir_option_demarrage()
```

---

```python
comptes_bancaires = []

stop = False

while not stop:

    stop = demarrer(comptes_bancaires)
```