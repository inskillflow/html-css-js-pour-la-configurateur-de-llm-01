# Cours 03 : Introduction à JavaScript et le DOM

## Introduction

JavaScript est le langage qui rend votre page **interactive**. Si HTML est le squelette et CSS la décoration, JavaScript est le système nerveux qui fait bouger et réagir la page.

## Qu'est-ce que JavaScript ?

JavaScript permet de :
- Réagir aux actions de l'utilisateur (clics, saisies)
- Modifier le contenu de la page dynamiquement
- Faire des calculs
- Afficher ou masquer des éléments

## Où Placer le Code JavaScript ?

### Dans la Balise `<script>`

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <title>Ma Page</title>
</head>
<body>
    <h1>Bonjour</h1>
    
    <script>
        // Votre code JavaScript ici
        console.log("Hello World");
    </script>
</body>
</html>
```

**Important :** Placez toujours le `<script>` **avant** la fermeture de `</body>` pour que le HTML soit chargé avant le JavaScript.

## Le DOM (Document Object Model)

Le DOM est une **représentation** de votre page HTML que JavaScript peut manipuler.

### Visualisation du DOM

```
document
  └── html
       ├── head
       │    └── title
       └── body
            ├── h1
            └── div
                 └── p
```

Chaque élément HTML devient un **objet** manipulable en JavaScript.

## Récupérer des Éléments HTML

### Méthode 1 : Par ID (getElementById)

**La plus courante et la plus simple.**

**HTML :**
```html
<select id="profile">
    <option value="factuel-court">Factuel Court</option>
</select>
```

**JavaScript :**
```javascript
const profileSelect = document.getElementById('profile');
```

**Explication :**
- `document` : représente toute la page
- `.getElementById()` : cherche un élément par son id
- `'profile'` : le nom de l'id (sans le `#`)
- `const profileSelect` : stocke l'élément dans une variable

### Exemple du Projet

```javascript
const profileSelect = document.getElementById('profile');
const roleSelect = document.getElementById('role');
const applyBtn = document.getElementById('applyBtn');
```

### Méthode 2 : Par Classe (getElementsByClassName)

```javascript
const cards = document.getElementsByClassName('card');
```

**Attention :** Retourne une **liste** d'éléments, pas un seul.

### Méthode 3 : Par Sélecteur CSS (querySelector)

```javascript
const titre = document.querySelector('#titre-principal');
const premiereParagraphe = document.querySelector('.paragraphe-info');
```

**Avantage :** Utilise la syntaxe CSS (`#` pour id, `.` pour class).

## Les Variables en JavaScript

Une variable est une **boîte** qui stocke une valeur.

### Déclaration avec const

```javascript
const prenom = "Jean";
const age = 25;
```

**Règle :** Utilisez `const` quand la valeur **ne change pas**.

### Déclaration avec let

```javascript
let compteur = 0;
compteur = compteur + 1;  // On peut changer la valeur
```

**Règle :** Utilisez `let` quand la valeur **peut changer**.

### Exemple dans Notre Projet

```javascript
// Ces variables stockent les éléments HTML
const profileSelect = document.getElementById('profile');
const roleSelect = document.getElementById('role');

// Ces variables vont changer de valeur
let temperature = 0;
let maxTokens = 0;
```

## Lire et Modifier du Contenu

### Lire la Valeur d'un Élément

```javascript
const select = document.getElementById('profile');
const valeurChoisie = select.value;  // Récupère la valeur sélectionnée
```

### Modifier le Texte d'un Élément

```javascript
const titre = document.getElementById('titre');
titre.textContent = "Nouveau texte";  // Change le texte
```

### Exemple du Projet

```javascript
const tempValue = document.getElementById('tempValue');
tempValue.textContent = temperature;  // Affiche la température
```

## Les Commentaires en JavaScript

Les commentaires expliquent le code sans l'exécuter.

### Commentaire sur une Ligne

```javascript
// Ceci est un commentaire
const nom = "Alice";  // Commentaire en fin de ligne
```

### Commentaire sur Plusieurs Lignes

```javascript
/*
Ceci est un commentaire
sur plusieurs lignes
*/
```

### Dans Notre Projet

```javascript
// 1. RÉCUPÉRATION DES ÉLÉMENTS HTML
// On récupère tous les éléments dont on a besoin
const profileSelect = document.getElementById('profile');
const roleSelect = document.getElementById('role');
```

## Console JavaScript

La console permet d'afficher des messages pour déboguer.

### Afficher un Message

```javascript
console.log("Hello World");
console.log(profileSelect);  // Affiche l'élément
```

**Pour Voir la Console :**
- Chrome/Edge : F12 puis onglet "Console"
- Firefox : F12 puis onglet "Console"

## Quiz Pratique

### Question 1
Comment récupère-t-on un élément avec `id="profile"` en JavaScript ?

- A) `document.getElement('profile')`
- B) `document.getElementById('profile')`
- C) `document.getElementById('#profile')`

**Réponse :** B - `document.getElementById('profile')` (sans le `#`)

### Question 2
Quelle est la différence entre `const` et `let` ?

**Réponse :** `const` pour les valeurs qui **ne changent pas**, `let` pour les valeurs qui **peuvent changer**.

### Question 3
Dans notre projet, combien d'éléments sont récupérés avec `getElementById` ?

**Réponse :** 10 éléments (profileSelect, roleSelect, applyBtn, parametersDisplay, selectedRoleDisplay, tempValue, maxTokensValue, topPValue, freqPenaltyValue, presPenaltyValue, butAttendu, profileDescription, generatedPrompt, exampleResponse)

### Question 4
Comment affiche-t-on un message dans la console ?

**Réponse :** `console.log("mon message")`

## Exercice Pratique

**Objectif :** Récupérer des éléments HTML et modifier leur contenu.

### Énoncé

Créez un fichier `exercice-03.html` avec :
1. Un titre avec `id="titre"`
2. Un paragraphe avec `id="message"`
3. Une liste déroulante avec `id="couleur"`
4. Un script JavaScript qui :
   - Récupère les 3 éléments
   - Change le texte du titre en "Bienvenue"
   - Affiche les éléments dans la console

### Solution

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 03</title>
</head>
<body>
    <h1 id="titre">Titre Original</h1>
    <p id="message">Message original</p>
    
    <select id="couleur">
        <option value="rouge">Rouge</option>
        <option value="bleu">Bleu</option>
    </select>
    
    <script>
        // 1. Récupération des éléments
        const titre = document.getElementById('titre');
        const message = document.getElementById('message');
        const couleur = document.getElementById('couleur');
        
        // 2. Modification du contenu
        titre.textContent = "Bienvenue";
        message.textContent = "Le JavaScript fonctionne !";
        
        // 3. Affichage dans la console
        console.log("Titre :", titre);
        console.log("Message :", message);
        console.log("Couleur :", couleur);
        console.log("Valeur sélectionnée :", couleur.value);
    </script>
</body>
</html>
```

**Test :** Ouvrez le fichier dans un navigateur et appuyez sur F12 pour voir la console.

## Exercice Avancé

Modifiez l'exercice pour que le message affiche la couleur sélectionnée :

```javascript
const couleur = document.getElementById('couleur');
const message = document.getElementById('message');

// Récupérer la valeur sélectionnée
const valeurCouleur = couleur.value;

// Afficher dans le message
message.textContent = "Vous avez choisi : " + valeurCouleur;
```

## Points Clés à Retenir

1. JavaScript rend la page interactive
2. `document.getElementById('nom')` récupère un élément par son id (sans `#`)
3. `const` pour les valeurs constantes, `let` pour les valeurs variables
4. `.value` récupère la valeur d'un input ou select
5. `.textContent` modifie le texte d'un élément
6. `console.log()` affiche dans la console pour déboguer
7. Le script doit être après le HTML ou attendre le chargement

## Tableau Récapitulatif

| Action | Code JavaScript |
|--------|----------------|
| Récupérer un élément | `document.getElementById('id')` |
| Lire la valeur | `element.value` |
| Modifier le texte | `element.textContent = "texte"` |
| Afficher dans console | `console.log(variable)` |
| Variable constante | `const nom = valeur;` |
| Variable modifiable | `let nom = valeur;` |

## Pour Aller Plus Loin

Dans le prochain cours, nous verrons comment réagir aux **événements** (clics de bouton, changements de sélection).

---

**Durée estimée :** 45 minutes  
**Niveau :** Débutant  
**Prérequis :** Cours 01 et 02

