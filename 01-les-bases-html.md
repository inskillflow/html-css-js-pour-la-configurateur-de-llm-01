# Cours 01 : Les Bases de HTML

## Introduction

HTML (HyperText Markup Language) est le langage qui structure une page web. Pensez à HTML comme au squelette d'une maison : il définit les murs, les pièces, les portes, mais pas encore la décoration.

## Les Balises HTML

Une balise HTML s'écrit entre chevrons `<>` et fonctionne généralement par paire :
- Une balise **ouvrante** : `<div>`
- Une balise **fermante** : `</div>`

### Exemple dans notre projet

```html
<div class="max-w-4xl mx-auto">
    <h1 class="text-3xl font-bold">Configurateur de Paramètres LLM</h1>
</div>
```

**Explication :**
- `<div>` : crée une boîte (division) pour regrouper du contenu
- `<h1>` : crée un titre principal (heading 1)
- Les balises se ferment dans l'ordre inverse de leur ouverture

## Structure de Base d'une Page HTML

Toute page HTML suit cette structure :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Titre de la page</title>
</head>
<body>
    <!-- Le contenu visible ici -->
</body>
</html>
```

**Explication des parties :**
- `<!DOCTYPE html>` : indique que c'est du HTML5
- `<html>` : balise racine qui contient tout
- `<head>` : informations sur la page (non visibles)
- `<body>` : contenu visible de la page

## Les Balises Importantes du Projet

### 1. Les Titres (h1, h2, h3)

```html
<h1>Titre Principal</h1>
<h2>Sous-titre</h2>
<h3>Sous-sous-titre</h3>
```

**Hiérarchie :** h1 > h2 > h3 (du plus important au moins important)

### 2. Les Paragraphes

```html
<p>Ceci est un paragraphe de texte.</p>
```

### 3. Les Listes Déroulantes (select)

```html
<select id="profile">
    <option value="">-- Choisir un profil --</option>
    <option value="factuel-court">Factuel Court</option>
</select>
```

**Explication :**
- `<select>` : crée une liste déroulante
- `<option>` : chaque choix dans la liste
- `value=""` : la valeur envoyée au JavaScript

### 4. Les Boutons

```html
<button id="applyBtn">Appliquer la configuration</button>
```

## Les Attributs HTML

Les attributs donnent des informations supplémentaires aux balises.

### Syntaxe

```html
<balise attribut="valeur">Contenu</balise>
```

### Attributs Courants dans le Projet

**1. id (identifiant unique)**
```html
<select id="profile">
```
- Donne un nom **unique** à un élément
- Utilisé pour cibler l'élément en JavaScript ou CSS

**2. class (classe CSS)**
```html
<div class="bg-white rounded-lg shadow-md">
```
- Applique des styles CSS
- Peut être utilisé sur plusieurs éléments

**3. value (valeur)**
```html
<option value="factuel-court">Factuel Court</option>
```
- Définit la valeur envoyée au programme

## Quiz Pratique

### Question 1
Quelle est la différence entre `<div>` et `<span>` ?
- A) Aucune différence
- B) `<div>` est un bloc, `<span>` est en ligne
- C) `<div>` est pour les images, `<span>` pour le texte

**Réponse :** B - `<div>` crée un bloc (nouvelle ligne), `<span>` reste dans la ligne

### Question 2
Dans notre projet, identifiez la balise qui crée le titre principal.

```html
<h1 class="text-3xl font-bold text-gray-800 mb-2">
    Configurateur de Paramètres LLM
</h1>
```

**Réponse :** `<h1>` est la balise de titre principal

### Question 3
Combien y a-t-il de listes déroulantes (`<select>`) dans notre projet ?

**Réponse :** 2 (une pour le profil, une pour le rôle)

## Exercice Pratique

**Objectif :** Créer une structure HTML simple

Créez un fichier `exercice-01.html` avec :
1. Un titre principal "Mon Premier Formulaire"
2. Un paragraphe explicatif
3. Une liste déroulante avec 3 options de couleurs
4. Un bouton "Valider"

### Solution

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 01</title>
</head>
<body>
    <h1>Mon Premier Formulaire</h1>
    <p>Choisissez votre couleur préférée :</p>
    
    <select id="couleur">
        <option value="">-- Choisir --</option>
        <option value="rouge">Rouge</option>
        <option value="bleu">Bleu</option>
        <option value="vert">Vert</option>
    </select>
    
    <button id="valider">Valider</button>
</body>
</html>
```

## Points Clés à Retenir

1. HTML structure le contenu avec des balises
2. Les balises fonctionnent par paires (ouverture/fermeture)
3. Les attributs donnent des informations supplémentaires
4. `id` = identifiant unique, `class` = style réutilisable
5. `<select>` crée une liste déroulante
6. `<button>` crée un bouton cliquable

## Pour Aller Plus Loin

Dans le prochain cours, nous verrons comment **styliser** ces éléments HTML avec CSS (couleurs, tailles, espacements).

---

**Durée estimée :** 30 minutes  
**Niveau :** Débutant  
**Prérequis :** Aucun

