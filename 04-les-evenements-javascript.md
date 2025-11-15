# Cours 04 : Les Événements en JavaScript

## Introduction

Un événement est une **action** qui se produit sur la page :
- Un clic sur un bouton
- Un changement dans une liste déroulante
- Le survol d'un élément avec la souris
- L'appui sur une touche du clavier

JavaScript peut **écouter** ces événements et **réagir** en exécutant du code.

## Qu'est-ce qu'un Écouteur d'Événement ?

Un écouteur d'événement (event listener) surveille un élément et attend qu'un événement se produise.

### Syntaxe

```javascript
element.addEventListener('typeEvenement', fonction);
```

**Explication :**
- `element` : l'élément HTML à surveiller
- `'typeEvenement'` : le type d'événement (click, change, etc.)
- `fonction` : le code à exécuter quand l'événement se produit

## L'Événement Click (Clic)

Le plus courant : réagir au clic sur un bouton.

### Exemple Simple

```html
<button id="monBouton">Cliquez-moi</button>

<script>
    // 1. Récupérer le bouton
    const bouton = document.getElementById('monBouton');
    
    // 2. Ajouter un écouteur d'événement
    bouton.addEventListener('click', function() {
        alert("Vous avez cliqué !");
    });
</script>
```

**Étapes :**
1. On récupère l'élément
2. On ajoute un écouteur avec `addEventListener`
3. On définit ce qui se passe au clic dans une fonction

### Exemple du Projet

```javascript
// 6. ÉCOUTEUR D'ÉVÉNEMENT
// On attend que l'utilisateur clique sur le bouton
applyBtn.addEventListener('click', appliquerConfiguration);
```

**Explication :**
- `applyBtn` : le bouton "Appliquer la configuration"
- `'click'` : on écoute les clics
- `appliquerConfiguration` : la fonction à exécuter

## Créer une Fonction

Une fonction est un **bloc de code réutilisable** avec un nom.

### Syntaxe

```javascript
function nomDeLaFonction() {
    // Code à exécuter
}
```

### Exemple Simple

```javascript
function direBonjour() {
    console.log("Bonjour !");
}

// Appeler la fonction
direBonjour();  // Affiche "Bonjour !"
```

### Exemple du Projet

```javascript
function appliquerConfiguration() {
    // Récupérer les valeurs sélectionnées
    const profilChoisi = profileSelect.value;
    const roleChoisi = roleSelect.value;
    
    // Vérifier qu'un profil et un rôle sont sélectionnés
    if (profilChoisi === "" || roleChoisi === "") {
        alert("Veuillez sélectionner un profil ET un rôle !");
        return;
    }
    
    // ... reste du code
}
```

## L'Événement Change (Changement)

Déclenché quand on change la valeur d'une liste déroulante ou d'un champ de texte.

### Exemple Simple

```html
<select id="couleur">
    <option value="rouge">Rouge</option>
    <option value="bleu">Bleu</option>
</select>

<p id="message"></p>

<script>
    const couleur = document.getElementById('couleur');
    const message = document.getElementById('message');
    
    couleur.addEventListener('change', function() {
        const valeur = couleur.value;
        message.textContent = "Vous avez choisi : " + valeur;
    });
</script>
```

### Exemple du Projet

```javascript
profileSelect.addEventListener('change', function() {
    if (profileSelect.value && roleSelect.value) {
        // Si les deux sont sélectionnés, appliquer automatiquement
        appliquerConfiguration();
    }
});
```

**Explication :** Quand on change le profil, si le rôle est aussi sélectionné, on applique automatiquement la configuration.

## Les Fonctions Anonymes

Une fonction sans nom, utilisée directement dans l'addEventListener.

### Syntaxe

```javascript
element.addEventListener('click', function() {
    // Code ici
});
```

### Comparaison

**Fonction nommée :**
```javascript
function afficherMessage() {
    alert("Hello");
}
bouton.addEventListener('click', afficherMessage);
```

**Fonction anonyme :**
```javascript
bouton.addEventListener('click', function() {
    alert("Hello");
});
```

**Quand Utiliser Quoi ?**
- Fonction nommée : si réutilisée plusieurs fois
- Fonction anonyme : si utilisée une seule fois

## Récupérer des Valeurs dans une Fonction

### Valeur d'une Liste Déroulante

```javascript
const select = document.getElementById('profile');
const valeur = select.value;  // Ex: "factuel-court"
```

### Texte d'un Champ de Texte

```javascript
const input = document.getElementById('nom');
const texte = input.value;
```

### Exemple Complet du Projet

```javascript
function appliquerConfiguration() {
    // Récupérer les valeurs sélectionnées
    const profilChoisi = profileSelect.value;
    const roleChoisi = roleSelect.value;
    
    console.log("Profil :", profilChoisi);
    console.log("Rôle :", roleChoisi);
}
```

## Types d'Événements Courants

| Événement | Déclencheur | Usage Typique |
|-----------|-------------|---------------|
| `click` | Clic de souris | Boutons, liens |
| `change` | Changement de valeur | Select, input |
| `input` | Saisie en temps réel | Champs de texte |
| `submit` | Soumission de formulaire | Formulaires |
| `mouseover` | Survol souris | Effets au survol |
| `keydown` | Touche pressée | Raccourcis clavier |

## Quiz Pratique

### Question 1
Quelle est la syntaxe pour ajouter un écouteur de clic sur un bouton ?

- A) `bouton.onClick('click', fonction)`
- B) `bouton.addEventListener('click', fonction)`
- C) `bouton.addListener('click', fonction)`

**Réponse :** B - `bouton.addEventListener('click', fonction)`

### Question 2
Quel événement utilise-t-on pour détecter un changement dans une liste déroulante ?

**Réponse :** `'change'`

### Question 3
Dans notre projet, quel est le nom de la fonction appelée quand on clique sur le bouton "Appliquer" ?

**Réponse :** `appliquerConfiguration`

### Question 4
Comment récupère-t-on la valeur sélectionnée d'un `<select>` en JavaScript ?

**Réponse :** `element.value`

## Exercice Pratique

**Objectif :** Créer une page avec des événements interactifs.

### Énoncé

Créez un fichier `exercice-04.html` avec :
1. Une liste déroulante de fruits (id="fruit")
2. Un bouton "Valider" (id="valider")
3. Un paragraphe pour afficher le résultat (id="resultat")

**Fonctionnalités :**
- Quand on clique sur le bouton, afficher le fruit sélectionné
- Quand on change la sélection, afficher immédiatement le choix

### Solution

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 04</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        #resultat {
            margin-top: 20px;
            padding: 10px;
            background-color: #f0f0f0;
        }
    </style>
</head>
<body>
    <h1>Choisissez votre fruit préféré</h1>
    
    <select id="fruit">
        <option value="">-- Choisir un fruit --</option>
        <option value="pomme">Pomme</option>
        <option value="banane">Banane</option>
        <option value="orange">Orange</option>
        <option value="fraise">Fraise</option>
    </select>
    
    <button id="valider">Valider</button>
    
    <p id="resultat"></p>
    
    <script>
        // 1. RÉCUPÉRATION DES ÉLÉMENTS
        const fruitSelect = document.getElementById('fruit');
        const validerBtn = document.getElementById('valider');
        const resultat = document.getElementById('resultat');
        
        // 2. FONCTION D'AFFICHAGE
        function afficherChoix() {
            const choix = fruitSelect.value;
            
            if (choix === "") {
                resultat.textContent = "Veuillez choisir un fruit.";
            } else {
                resultat.textContent = "Vous avez choisi : " + choix;
            }
        }
        
        // 3. ÉCOUTEUR SUR LE BOUTON (clic)
        validerBtn.addEventListener('click', afficherChoix);
        
        // 4. ÉCOUTEUR SUR LA LISTE (changement)
        fruitSelect.addEventListener('change', function() {
            console.log("Changement détecté !");
            afficherChoix();
        });
    </script>
</body>
</html>
```

**Test :** Ouvrez le fichier et testez les deux façons d'afficher le résultat.

## Exercice Avancé

Ajoutez un compteur qui compte combien de fois l'utilisateur a changé de sélection :

```javascript
let compteur = 0;

fruitSelect.addEventListener('change', function() {
    compteur = compteur + 1;
    console.log("Nombre de changements :", compteur);
});
```

## Points Clés à Retenir

1. Un événement est une action de l'utilisateur (clic, changement, etc.)
2. `addEventListener('type', fonction)` écoute un événement
3. `'click'` pour les clics de bouton
4. `'change'` pour les changements de sélection
5. Une fonction regroupe du code réutilisable
6. `.value` récupère la valeur d'un input ou select
7. On peut avoir plusieurs écouteurs sur le même élément

## Schéma du Fonctionnement

```
Utilisateur → Clique sur bouton
       ↓
addEventListener détecte l'événement
       ↓
Exécute la fonction associée
       ↓
Code dans la fonction s'exécute
       ↓
Page mise à jour
```

## Comparaison avec Notre Projet

**Dans le projet :**
```javascript
applyBtn.addEventListener('click', appliquerConfiguration);
```

**Ce qui se passe :**
1. L'utilisateur clique sur "Appliquer la configuration"
2. L'écouteur détecte le clic
3. La fonction `appliquerConfiguration` s'exécute
4. Les paramètres sont calculés et affichés

## Pour Aller Plus Loin

Dans le prochain cours, nous verrons les **conditions if/else** qui permettent de prendre des décisions dans le code.

---

**Durée estimée :** 50 minutes  
**Niveau :** Débutant  
**Prérequis :** Cours 01, 02, 03

