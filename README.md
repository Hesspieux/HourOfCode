class: center, middle

# Une application bancaire

Sur le site [replt.it](https://repl.it/repls/GoodnaturedGraveTurtle)

---

### D&eacute;finition d'un objet **Compte Bancaire**

#### 1) Cr&eacute;er une classe *CompteBancaire* qui poss&egrave;de les propri&eacute;t&eacute;s suivantes :
- *nom* : le nom du propri&eacute;taire du compte
- *solde* : le solde du compte

```python
class CompteBancaire:
  
  def __init__(self, nom, solde = 0):
  
	self.nom = nom
    self.solde = solde
	
	print("Bienvenue", nom, "chez HourOfCode Bank !")
	print("Votre solde est :", self.solde, "&#x20ac;")
```

**\> Test du programme**	

```python
compte_de_pierre = CompteBancaire("Pierre")

compte_de_jean = CompteBancaire("Jean", 1500)
```

---

### D&eacute;finition d'un objet **Compte Bancaire**

#### 2) Ajouter une fonction sur la classe *CompteBancaire* pour cr&eacute;diter le compte :
- Cette fonction accepte un param&egrave;tre : la somme &agrave; d&eacute;poser sur le compte.

```python
  def deposer(self, somme):
  
	self.solde = self.solde + somme
	
	print("Votre solde est :", self.solde, "&#x20ac;")
```

**\> Test du programme**	

```python
compte_de_pierre = CompteBancaire("Pierre")

compte_de_pierre.deposer(1500)
```

---

### D&eacute;finition d'un objet **Compte Bancaire**

#### 3) Ajouter une fonction sur la classe *CompteBancaire* pour d&eacute;biter le compte :
- Cette fonction accepte un param&egrave;tre : la somme &agrave; retirer du compte.

```python
  def retirer(self, somme):
  
	self.solde = self.solde - somme
	
	print("Votre solde est :", self.solde, "&#x20ac;")
```

**\> Test du programme**	

```python
compte_de_pierre = CompteBancaire("Pierre", 1500)

compte_de_pierre.retirer(500)
```

---

### D&eacute;finition d'un objet **Compte Bancaire**

#### 4) Ajouter une fonction sur la classe *CompteBancaire* pour afficher le solde du compte :

```python
  def afficher(self):
  
	print("Votre solde est :", self.solde, "&#x20ac;")
```

**\> Test du programme**	

```python
compte_de_pierre = CompteBancaire("Pierre", 1500)

compte_de_pierre.afficher(500)
```

---

### D&eacute;finition d'un objet **Compte Bancaire**

#### 5) Exemple final

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
	print("Votre solde est :", self.solde, "&#x20ac;")
```

---

### Fonctions de gestion de compte bancaire

#### 1) Ajout d'une liste de compte bancaire

```python
comptes_bancaires = []
```

**\> Test du programme**
```python
len(comptes_bancaires)
```

---

### Fonctions de gestion de compte bancaire

#### 2) Cr&eacute;ation un nouveau compte bancaire

- Cette fonction prend en param&egrave;tre une liste de comptes bancaire
- On demande &agrave; l'utilisateur un nom et &eacute;ventuellement un premier versement
- On met &agrave; jour la liste de compte bancaire


```python
def creer_compte_bancaire(comptes_bancaires):

  nom = input("Votre nom :")
  
  solde = input("Premier versement :")
  
  nouveau_compte_bancaire = CompteBancaire(nom, solde)
  
  compte_bancaires.append(nouveau_compte_bancaire)
  
  return nouveau_compte_bancaire
```

**\> Test du programme**
```python
creer_compte_bancaire(comptes_bancaires)

len(comptes_bancaires)
```

---

### Fonctions de gestion de compte bancaire

#### 3) R&eacute;cup&eacute;ration d'un compte bancaire existant

- Cette fonction prend en param&egrave; une liste de comptes bancaires et le nom du propri&eacute;taire 
- Cette fonction demandera &agrave; l'utilisateur un nom et &eacute;ventuellement un premier versement

```python
def recuperer(comptes_bancaires, nom):
  
  for compte_bancaire in comptes_bancaires:
  
    if compte_bancaire.nom == nom:
	
      return compte_bancaire
      
  print("Pas de compte bancaire trouv&eacute; pour", nom)
```

**\> Test du programme**
```python
nouveau_compte_bancaire = creer_compte_bancaire(comptes_bancaires)
mon_compte_bancaire = recuperer(comptes_bancaires, compte_bancaire.nom)

mon_compte_bancaire.nom = nouveau_compte_bancaire.nom
mon_compte_bancaire.solde = nouveau_compte_bancaire.solde
```

---

### Gestion du compte bancaire par l'utilisateur

L'utilisateur a quatre choix :

	1. Afficher son solde
	
	2. D&eacute;poser de l'argent
	
	3. Retirer de l'argent
	
	4. Fermer sa session
	
---

### Gestion du compte bancaire par l'utilisateur

#### 1) Algorithme de choix

```python
def choisir_option_gestion(compte_bancaire):
  
  continuer = True

  while continuer:
  
    choix = input("Tapez votre choix :")
    choix = int(choix)
    
    if choix == 1:
      compte_bancaire.afficher()
	  
    elif choix == 2:
      somme = input("Montant d&eacute;sir&eacute; :")
      somme = int(somme)
      compte_bancaire.deposer(somme)
	  
    elif choix == 3:
      somme = input("Montant d&eacute;sir&eacute; :")
      somme = int(somme)
      compte_bancaire.retirer(somme)
	  
    elif choix == 4:
      continuer = False
      print("Fermeture de session pour", compte_bancaire.nom)

```

---

### Gestion du compte bancaire par l'utilisateur

#### 2) Exemple d'affichage


```python
def gerer(compte_bancaire):
  continuer = True

  while continuer:
  
    print("##### Bonjour", compte_bancaire.nom, "#####")
    print("\n")
    print("- [1] Afficher")
    print("- [2] D&eacute;poser de l'argent")
    print("- [3] Retirer de l'argent")
    print("- [4] Quitter")
    print("\n")
	
	choisir_option_gestion()
	
```

---

### Page d'accueil de l'application

L'utilisateur a trois choix :

	1. Ouvrir un nouveau compte bancaire
	
	2. S'identifier
	
	3. Quitter l'application
	
---

### Page d'accueil de l'application

#### 1) Algorithme de choix sur les options au d&eacute;marrage


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

---

### Page d'accueil de l'application

#### 2) Exemple de page d'accueil

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

### Execution de l'application !

```python
comptes_bancaires = []
demarrer(comptes_bancaires)

```

---

class: center, middle

# Solution

---

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
  
	  print("Votre solde est :", self.solde, "&#x20ac;")
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
	  
  print("Pas de compte bancaire trouv&eacute; pour", nom)
  
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
	
      somme = input("Montant d&eacute;sir&eacute; :")
      somme = int(somme)
      compte_bancaire.deposer(somme)
	  
    elif choix == 3:
	
      somme = input("Montant d&eacute;sir&eacute; :")
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
    print("- [2] D&eacute;poser de l'argent")
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