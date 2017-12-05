# Définition d'un objet **Compte Bancaire**

## Créer une classe *CompteBancaire* qui poss&egrave;de les propriétés suivantes :
- *nom* : le nom du propriétaire du compte
- *solde* : le solde du compte

```python
class CompteBancaire:
  
	def __init__(self, nom, solde = 0):
  
		self.nom = nom
		self.solde = solde
	
		print("Bienvenue", nom, "chez HourOfCode Bank !")
		print("Votre solde est :", self.solde, "€")
```

**\> Test du programme**

```python
compte_de_pierre = CompteBancaire("Pierre")

compte_de_jean = CompteBancaire("Jean", 1500)
```

## Ajouter une fonction sur la classe *CompteBancaire* pour créditer le compte :
- Cette fonction accepte un param&egrave;tre : la somme à déposer sur le compte.

```python
def deposer(self, somme):
  
	self.solde = self.solde + somme

	print("Votre solde est :", self.solde, "€")
```

**\> Test du programme**

```python
compte_de_pierre = CompteBancaire("Pierre")

compte_de_pierre.deposer(1500)
```

## Ajouter une fonction sur la classe *CompteBancaire* pour débiter le compte :
- Cette fonction accepte un param&egrave;tre : la somme à retirer du compte.

```python
def retirer(self, somme):
  
	self.solde = self.solde - somme

	print("Votre solde est :", self.solde, "€")
```

**\> Test du programme**

```python
compte_de_pierre = CompteBancaire("Pierre", 1500)

compte_de_pierre.retirer(500)
```

## Ajouter une fonction sur la classe *CompteBancaire* pour afficher le solde du compte :

```python
def afficher(self):
  
	print("Votre solde est :", self.solde, "€")
```

**\> Test du programme**

```python
compte_de_pierre = CompteBancaire("Pierre", 1500)

compte_de_pierre.afficher(500)
```

## Exemple final

```python
class CompteBancaire:
  
	def __init__(self, nom, solde = 0):
		self.nom = nom
		self.solde = solde
		print("Bienvenue", nom, "chez HourOfCode Bank !")
		self.afficher()
    
	def deposer(self, somme):
		self.solde = self.solde + somme
		self.afficher()

	def retirer(self, somme):
		self.solde = self.solde - somme;
		self.afficher()

	def afficher(self):
		print("Votre solde est :", self.solde, "€;")
```

---

# La suite

Vous êtes maintenant prêts pour ajouter des fonction de gestion sur le compte en banque ! Rendez-vous à [l'étape suivante](./1-manage-the-bank-account.md).