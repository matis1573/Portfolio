---
layout: post
title: Calculatrice.py
date: 2026-01-03 11:33:00 +0100
categories: [projet]
description: Une calculatrice simple en Python expliquée étape par étape.
---

Voici comment j'ai réalisé une calculatrice simple en Python.

<video width="100%" autoplay loop muted playsinline style="border-radius: 8px; margin: 20px 0; pointer-events: none;">
  <source src="{{site.baseurl}}/assets/videos/calculatrice-demo.mov" type="video/mp4">
  Votre navigateur ne supporte pas la lecture de vidéos.
</video>

### Le Code Complet

```python
while True:
    print("\n--- CALCULATRICE ---")
    print("1. Addition (+)")
    print("2. Soustraction (-)")
    print("3. Multiplication (*)")
    print("4. Division (/)")
    print("5. Quitter")

    choix = input("Choisis une opération : ")

    if choix in ["1", "2", "3", "4"]:
        num1 = float(input("Entrez le premier nombre : "))
        num2 = float(input("Entrez le deuxième nombre : "))

        if choix == "1":
            resultat = num1 + num2
        elif choix == "2":
            resultat = num1 - num2
        elif choix == "3":
            resultat = num1 * num2
        elif choix == "4":
            if num2 != 0:
                resultat = num1 / num2
            else:
                print("Erreur : division par zéro !")
                continue

        print("Résultat :", resultat)

    elif choix == "5":
        print("Au revoir 👋")
        break

    else:
        print("Choix invalide ❗")
```

### Explication Étape par Étape

**1. La Boucle Infinie**
```python
while True:
```
On utilise `while True` pour que le programme continue de tourner indéfiniment jusqu'à ce que l'utilisateur décide de quitter. Cela permet de faire plusieurs calculs à la suite sans relancer le script.

**2. Le Menu**
```python
    print("\n--- CALCULATRICE ---")
    print("1. Addition (+)")
    ...
```
On affiche les options disponibles à l'utilisateur pour qu'il sache quoi taper.

**3. Le Choix de l'Utilisateur**
```python
    choix = input("Choisis une opération : ")
```
La fonction `input()` permet de récupérer ce que l'utilisateur tape au clavier.

**4. Vérification et Saisie des Nombres**
```python
    if choix in ["1", "2", "3", "4"]:
        num1 = float(input("Entrez le premier nombre : "))
        num2 = float(input("Entrez le deuxième nombre : "))
```
Si l'utilisateur choisit une opération mathématique (1 à 4), on lui demande alors les deux nombres. On utilise `float()` pour permettre les nombres à virgule (ex: 5.5).

**5. Les Calculs**
On utilise une série de `if` et `elif` (sinon si) pour effectuer la bonne opération :
*   **Addition** (`+`)
*   **Soustraction** (`-`)
*   **Multiplication** (`*`)
*   **Division** (`/`) : Pour la division, on ajoute une sécurité `if num2 != 0` car il est impossible de diviser par zéro !

**6. Quitter le Programme**
```python
    elif choix == "5":
        print("Au revoir 👋")
        break
```
Si l'utilisateur tape "5", on utilise l'instruction `break` qui casse la boucle `while` et arrête le programme.

**7. Gestion des Erreurs**
```python
    else:
        print("Choix invalide ❗")
```
Si l'utilisateur tape autre chose que 1, 2, 3, 4 ou 5, on lui dit que son choix n'est pas valide.
