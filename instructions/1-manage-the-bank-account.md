# Fonctions de gestion de compte bancaire

## Ajout d'une liste de compte bancaire

```python
comptes_bancaires = []
```

**\> Test du programme**
```python
len(comptes_bancaires)
```

## Cr�ation un nouveau compte bancaire

- Cette fonction prend en param&egrave;tre une liste de comptes bancaire
- On demande � l'utilisateur un nom et �ventuellement un premier versement
- On met � jour la liste de compte bancaire


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

## R�cup�ration d'un compte bancaire existant

- Cette fonction prend en param&egrave; une liste de comptes bancaires et le nom du propri�taire 
- Cette fonction demandera � l'utilisateur un nom et �ventuellement un premier versement

```python
def recuperer(comptes_bancaires, nom):
  
  for compte_bancaire in comptes_bancaires:
  
    if compte_bancaire.nom == nom:
	
      return compte_bancaire
      
  print("Pas de compte bancaire trouv� pour", nom)
```

**\> Test du programme**
```python
nouveau_compte_bancaire = creer_compte_bancaire(comptes_bancaires)
mon_compte_bancaire = recuperer(comptes_bancaires, compte_bancaire.nom)

mon_compte_bancaire.nom = nouveau_compte_bancaire.nom
mon_compte_bancaire.solde = nouveau_compte_bancaire.solde
```

---

# La suite

Vous �tes maintenant pr�ts pour g�rer les options de l'utilisateur sur son compte ! Rendez-vous � [l'�tape suivante](./2-user-account-options.md).