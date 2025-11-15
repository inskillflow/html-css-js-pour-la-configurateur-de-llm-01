# Cours 02 : Les Sélecteurs CSS et l'Attribut id

## Introduction

CSS (Cascading Style Sheets) est le langage qui **décore** votre page HTML. Si HTML est le squelette, CSS est la peinture, les meubles et la décoration.

## Qu'est-ce qu'un Sélecteur ?

Un sélecteur CSS permet de **cibler** un ou plusieurs éléments HTML pour leur appliquer un style.

### Syntaxe de Base

```css
selecteur {
    propriete: valeur;
}
```

## Les Trois Types de Sélecteurs Principaux

### 1. Le Sélecteur par Balise

Cible **toutes** les balises du même type.

```css
h1 {
    color: blue;
}
```

**Résultat :** Tous les `<h1>` de la page seront bleus.

### 2. Le Sélecteur par Classe (.)

Cible les éléments avec un attribut `class` spécifique.

```css
.ma-classe {
    background-color: yellow;
}
```

```html
<div class="ma-classe">Ce texte aura un fond jaune</div>
```

**Attention :** Le point `.` est obligatoire en CSS, mais pas dans le HTML.

### 3. Le Sélecteur par ID (#)

Cible **un seul** élément avec un attribut `id` spécifique.

```css
#mon-id {
    font-size: 20px;
}
```

```html
<p id="mon-id">Ce paragraphe aura une taille de 20px</p>
```

**Attention :** Le dièse `#` est obligatoire en CSS, mais pas dans le HTML.

## Différence Entre id et class

### L'attribut id

**Caractéristiques :**
- **Unique** : un seul élément par page peut avoir cet id
- Utilisé pour cibler un élément précis
- Prioritaire en CSS (plus fort qu'une classe)

**Exemple dans notre projet :**

```html
<select id="profile">
```

En CSS, on ciblerait ainsi :
```css
#profile {
    border: 2px solid blue;
}
```

En JavaScript, on récupère ainsi :
```javascript
const profileSelect = document.getElementById('profile');
```

### L'attribut class

**Caractéristiques :**
- **Réutilisable** : plusieurs éléments peuvent avoir la même classe
- Utilisé pour styliser plusieurs éléments similaires
- Moins prioritaire que l'id

**Exemple dans notre projet :**

```html
<div class="bg-white rounded-lg shadow-md p-6 mb-6">
```

## Exemples Pratiques du Projet

### Exemple 1 : Cibler un Bouton par son id

**HTML :**
```html
<button id="applyBtn" class="mt-6 w-full bg-blue-600">
    Appliquer la configuration
</button>
```

**CSS :**
```css
#applyBtn {
    background-color: blue;
    color: white;
    padding: 12px;
}
```

### Exemple 2 : Cibler Plusieurs Éléments par class

**HTML :**
```html
<div class="card">Carte 1</div>
<div class="card">Carte 2</div>
<div class="card">Carte 3</div>
```

**CSS :**
```css
.card {
    border: 1px solid gray;
    padding: 20px;
    margin: 10px;
}
```

**Résultat :** Les 3 cartes auront le même style.

## Propriétés CSS Courantes

### Couleurs

```css
color: blue;              /* Couleur du texte */
background-color: yellow; /* Couleur de fond */
```

### Tailles

```css
width: 300px;    /* Largeur */
height: 200px;   /* Hauteur */
font-size: 16px; /* Taille du texte */
```

### Espacements

```css
margin: 10px;   /* Espace extérieur */
padding: 20px;  /* Espace intérieur */
```

### Bordures

```css
border: 2px solid black;  /* Bordure : épaisseur style couleur */
border-radius: 8px;       /* Coins arrondis */
```

## Tailwind CSS dans Notre Projet

Notre projet utilise **Tailwind CSS**, un framework qui applique des classes utilitaires directement dans le HTML.

### Exemple de Classes Tailwind

```html
<div class="bg-white rounded-lg shadow-md p-6 mb-6">
```

**Traduction :**
- `bg-white` : fond blanc
- `rounded-lg` : coins arrondis (large)
- `shadow-md` : ombre moyenne
- `p-6` : padding (espacement intérieur) de 6 unités
- `mb-6` : margin-bottom (marge basse) de 6 unités

## Quiz Pratique

### Question 1
Quelle est la différence principale entre `id` et `class` ?

**Réponse :** L'`id` est **unique** (un seul par page), la `class` est **réutilisable** (plusieurs éléments peuvent l'avoir).

### Question 2
Comment cible-t-on en CSS un élément avec `id="profile"` ?

- A) `.profile`
- B) `#profile`
- C) `profile`

**Réponse :** B - `#profile`

### Question 3
Dans notre projet, trouvez un élément avec un `id` et expliquez pourquoi il a un id.

**Exemple de réponse :**
```html
<select id="profile">
```
Il a un `id` car c'est un élément **unique** que nous devons cibler en JavaScript pour récupérer sa valeur.

### Question 4
Combien d'éléments peuvent avoir la classe `bg-white` dans une page ?

**Réponse :** Autant qu'on veut ! Une classe est réutilisable.

## Exercice Pratique

**Objectif :** Créer un fichier HTML avec du CSS pour styliser des éléments.

### Énoncé

Créez un fichier `exercice-02.html` contenant :
1. Un titre avec l'id `titre-principal`
2. Trois paragraphes avec la classe `paragraphe-info`
3. Un bouton avec l'id `btn-action`

Puis ajoutez du CSS pour :
- Le titre : couleur bleue, taille 32px
- Les paragraphes : fond gris clair, padding 10px
- Le bouton : fond vert, texte blanc, padding 15px

### Solution

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 02</title>
    <style>
        /* Sélecteur par ID */
        #titre-principal {
            color: blue;
            font-size: 32px;
        }
        
        /* Sélecteur par classe */
        .paragraphe-info {
            background-color: #f0f0f0;
            padding: 10px;
            margin-bottom: 10px;
        }
        
        /* Sélecteur par ID */
        #btn-action {
            background-color: green;
            color: white;
            padding: 15px;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1 id="titre-principal">Mon Titre Principal</h1>
    
    <p class="paragraphe-info">Premier paragraphe d'information.</p>
    <p class="paragraphe-info">Deuxième paragraphe d'information.</p>
    <p class="paragraphe-info">Troisième paragraphe d'information.</p>
    
    <button id="btn-action">Cliquez ici</button>
</body>
</html>
```

## Points Clés à Retenir

1. CSS stylise le HTML avec des sélecteurs
2. Trois types principaux : balise, `.classe`, `#id`
3. `id` = unique, un seul par page
4. `class` = réutilisable, plusieurs éléments
5. En CSS : `#` pour id, `.` pour class
6. En HTML : pas de `#` ni de `.`
7. Tailwind applique des classes utilitaires directement

## Tableau Récapitulatif

| Concept | HTML | CSS | Usage |
|---------|------|-----|-------|
| ID | `id="profile"` | `#profile { }` | Élément unique |
| Class | `class="card"` | `.card { }` | Plusieurs éléments |
| Balise | `<h1>` | `h1 { }` | Tous les h1 |

## Pour Aller Plus Loin

Dans le prochain cours, nous verrons comment **récupérer** ces éléments en JavaScript pour les manipuler.

---

**Durée estimée :** 45 minutes  
**Niveau :** Débutant  
**Prérequis :** Cours 01

