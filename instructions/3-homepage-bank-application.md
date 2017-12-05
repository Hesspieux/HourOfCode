# Page d'accueil de l'application

L'utilisateur a trois choix :

	1. Ouvrir un nouveau compte bancaire
	
	2. S'identifier
	
	3. Quitter l'application

## Algorithme de choix sur les options au démarrage


```python
def choisir_option_demarrage()
 	
	continuer = True
  
    while continuer:
	
	    choix = input("Tapez votre choix :")
        choix = int(choix)
	
		if choix == 1:	
		  creer_compte_bancaire(comptes_bancaires) 
		  
		elif choix == 2:
		  nom = input("Votre nom :")
		  compte_bancaire = identifier(comptes_bancaires, nom)
		  gerer(compte_bancaire)
		  
		elif choix == 3:
		  continuer = False
		  print("Au revoir !")
```

## Exemple de page d'accueil

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
	
	choisir_option_demarrage()
```

---

# La suite

Vous êtes maintenant prêts pour gérer lafficher la page d'accueil de l'application bancaire ! Rendez-vous à [l'étape suivante](./4-execute-the-application.md).
