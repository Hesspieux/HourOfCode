
# Gestion du compte bancaire par l'utilisateur

L'utilisateur a quatre choix :

	1. Afficher son solde

	2. D�poser de l'argent

	3. Retirer de l'argent

	4. Fermer sa session

## Algorithme de choix

```python
def choisir_option_gestion(compte_bancaire):

	continuer = True

	while continuer:

		choix = input("Tapez votre choix :")
		choix = int(choix)

		if choix == 1:
			compte_bancaire.afficher()

		elif choix == 2:
			somme = input("Montant d�sir� :")
			somme = int(somme)
			compte_bancaire.deposer(somme)
  
		elif choix == 3:
			somme = input("Montant d�sir� :")
			somme = int(somme)
			compte_bancaire.retirer(somme)
  
		elif choix == 4:
			continuer = False
			print("Fermeture de session pour", compte_bancaire.nom)

```

## Exemple d'affichage


```python
def gerer(compte_bancaire):
	continuer = True

	while continuer:

		print("##### Bonjour", compte_bancaire.nom, "#####")
		print("\n")
		print("- [1] Afficher")
		print("- [2] D�poser de l'argent")
		print("- [3] Retirer de l'argent")
		print("- [4] Quitter")
		print("\n")

	choisir_option_gestion()
```

---

# La suite

Vous �tes maintenant pr�ts pour g�rer lafficher la page d'accueil de l'application bancaire ! Rendez-vous � [l'�tape suivante](./3-homepage-bank-application.md).