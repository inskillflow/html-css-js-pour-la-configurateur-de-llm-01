# Cours 05 : Les Conditions if/else

## Introduction

Les conditions permettent à votre programme de **prendre des décisions**. C'est comme dire : "Si cette situation se produit, alors fais ceci, sinon fais cela."

## La Structure if (si)

### Syntaxe de Base

```javascript
if (condition) {
    // Code exécuté si la condition est vraie
}
```

### Exemple Simple

```javascript
const age = 18;

if (age >= 18) {
    console.log("Vous êtes majeur");
}
```

**Explication :**
- `age >= 18` : condition à vérifier
- `>=` : supérieur ou égal
- Si la condition est **vraie**, le code dans les `{}` s'exécute

## La Structure if/else (si/sinon)

```javascript
if (condition) {
    // Code si la condition est vraie
} else {
    // Code si la condition est fausse
}
```

### Exemple Simple

```javascript
const age = 16;

if (age >= 18) {
    console.log("Vous êtes majeur");
} else {
    console.log("Vous êtes mineur");
}
```

## La Structure if/else if/else (si/sinon si/sinon)

Permet de tester plusieurs conditions successivement.

```javascript
if (condition1) {
    // Code si condition1 est vraie
} else if (condition2) {
    // Code si condition2 est vraie
} else {
    // Code si aucune condition n'est vraie
}
```

### Exemple avec les Notes

```javascript
const note = 15;

if (note >= 16) {
    console.log("Très bien");
} else if (note >= 14) {
    console.log("Bien");
} else if (note >= 10) {
    console.log("Passable");
} else {
    console.log("Insuffisant");
}
```

## Les Opérateurs de Comparaison

| Opérateur | Signification | Exemple | Résultat |
|-----------|---------------|---------|----------|
| `===` | Égal à | `5 === 5` | true |
| `!==` | Différent de | `5 !== 3` | true |
| `>` | Supérieur à | `10 > 5` | true |
| `<` | Inférieur à | `3 < 5` | true |
| `>=` | Supérieur ou égal | `5 >= 5` | true |
| `<=` | Inférieur ou égal | `3 <= 5` | true |

**Attention :** Utilisez toujours `===` (triple égal) et non `==` (double égal) pour plus de précision.

## Les Opérateurs Logiques

### ET logique (&&)

Les deux conditions doivent être vraies.

```javascript
const age = 20;
const permis = true;

if (age >= 18 && permis === true) {
    console.log("Vous pouvez conduire");
}
```

### OU logique (||)

Au moins une des conditions doit être vraie.

```javascript
const jour = "samedi";

if (jour === "samedi" || jour === "dimanche") {
    console.log("C'est le week-end !");
}
```

### NON logique (!)

Inverse une condition.

```javascript
const pluie = false;

if (!pluie) {
    console.log("Il ne pleut pas");
}
```

## Exemple du Projet : Vérification des Sélections

```javascript
// Vérifier qu'un profil et un rôle sont sélectionnés
if (profilChoisi === "" || roleChoisi === "") {
    alert("Veuillez sélectionner un profil ET un rôle !");
    return;
}
```

**Explication :**
- `profilChoisi === ""` : vérifie si le profil est vide
- `||` : OU logique
- `roleChoisi === ""` : vérifie si le rôle est vide
- Si l'un **ou** l'autre est vide, on affiche une alerte
- `return` : arrête la fonction

## Exemple du Projet : Choix du Profil

Voici comment notre projet choisit les paramètres selon le profil :

```javascript
if (profilChoisi === "factuel-court") {
    // Profil A : très factuel, court (1 phrase)
    temperature = 0.3;
    maxTokens = 60;
    topP = 0.9;
    frequencyPenalty = 0.0;
    presencePenalty = 0.0;
    but = "1 phrase, factuel, clair (25–40 mots)";
    
} else if (profilChoisi === "factuel-developpe") {
    // Profil B : factuel, développé (120-160 mots)
    temperature = 0.4;
    maxTokens = 250;
    topP = 0.9;
    frequencyPenalty = 0.0;
    presencePenalty = 0.0;
    but = "Définition + critère + impact (120–160 mots)";
    
} else if (profilChoisi === "creatif-court") {
    // Profil D : créatif mais court (1 phrase)
    temperature = 0.8;
    maxTokens = 70;
    topP = 0.95;
    frequencyPenalty = 0.3;
    presencePenalty = 0.2;
    but = "1 phrase, créatif, critère explicite";
    
} else {
    // Cas par défaut
    alert("Profil non reconnu !");
    return;
}
```

**Logique :**
1. **Si** le profil est "factuel-court", utiliser ces paramètres
2. **Sinon si** le profil est "factuel-developpe", utiliser ces autres paramètres
3. **Sinon si** le profil est "creatif-court", utiliser encore d'autres paramètres
4. **Sinon**, afficher une erreur

## Conditions Imbriquées

On peut mettre des `if` à l'intérieur d'autres `if`.

### Exemple Simple

```javascript
const age = 20;
const etudiant = true;

if (age >= 18) {
    if (etudiant === true) {
        console.log("Tarif étudiant adulte");
    } else {
        console.log("Tarif adulte normal");
    }
} else {
    console.log("Tarif enfant");
}
```

### Exemple du Projet : Adaptation selon le Rôle

```javascript
if (roleChoisi === "assistant-friendly") {
    roleTexte = "Assistant Friendly - Ton amical et accessible";
    prefixeRole = "En tant qu'assistant amical et accessible, ";
    
    // Adapter l'exemple selon le profil
    if (profilChoisi === "factuel-court") {
        exemple = "Salut ! Alors, flex et flex-col...";
    } else if (profilChoisi === "factuel-developpe") {
        exemple = "Hey ! Laisse-moi t'expliquer...";
    }
    
} else if (roleChoisi === "expert-professionnel") {
    roleTexte = "Expert Professionnel - Ton formel et précis";
    prefixeRole = "En qualité d'expert professionnel, ";
}
```

**Explication :**
- Premier niveau : quel rôle ?
- Deuxième niveau : quel profil pour ce rôle ?

## Le mot-clé return

`return` arrête immédiatement l'exécution d'une fonction.

### Exemple

```javascript
function verifierAge(age) {
    if (age < 18) {
        console.log("Accès refusé");
        return;  // Arrête ici
    }
    
    console.log("Accès autorisé");
    // Ce code ne s'exécute que si age >= 18
}
```

### Dans Notre Projet

```javascript
if (profilChoisi === "" || roleChoisi === "") {
    alert("Veuillez sélectionner un profil ET un rôle !");
    return;  // On arrête la fonction ici
}

// Le reste du code ne s'exécute que si les deux sont sélectionnés
```

## Quiz Pratique

### Question 1
Que fait ce code ?

```javascript
if (age >= 18) {
    console.log("Majeur");
} else {
    console.log("Mineur");
}
```

**Réponse :** Affiche "Majeur" si l'âge est supérieur ou égal à 18, sinon affiche "Mineur".

### Question 2
Quelle est la différence entre `&&` et `||` ?

**Réponse :** 
- `&&` (ET) : les deux conditions doivent être vraies
- `||` (OU) : au moins une condition doit être vraie

### Question 3
Dans notre projet, combien y a-t-il de `else if` pour tester les profils ?

**Réponse :** 5 (factuel-court, factuel-developpe, nuance, creatif-court, creatif-developpe, hybride)

### Question 4
Que fait le mot-clé `return` ?

**Réponse :** Il arrête immédiatement l'exécution de la fonction.

## Exercice Pratique

**Objectif :** Créer une page avec des conditions pour calculer un tarif.

### Énoncé

Créez un fichier `exercice-05.html` avec :
1. Une liste déroulante pour l'âge : "Enfant", "Adulte", "Senior"
2. Une case à cocher "Étudiant"
3. Un bouton "Calculer le tarif"
4. Un paragraphe pour afficher le résultat

**Tarifs :**
- Enfant (< 18 ans) : 5 euros
- Adulte : 10 euros
- Senior (> 65 ans) : 7 euros
- Réduction étudiant : -2 euros

### Solution

```html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exercice 05</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
        }
        .formulaire {
            background-color: #f0f0f0;
            padding: 20px;
            border-radius: 8px;
            max-width: 400px;
        }
        .champ {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        select, button {
            padding: 8px;
            font-size: 16px;
        }
        #resultat {
            margin-top: 20px;
            padding: 15px;
            background-color: #4CAF50;
            color: white;
            border-radius: 5px;
            display: none;
        }
    </style>
</head>
<body>
    <h1>Calculateur de Tarif</h1>
    
    <div class="formulaire">
        <div class="champ">
            <label for="categorie">Catégorie d'âge :</label>
            <select id="categorie">
                <option value="">-- Choisir --</option>
                <option value="enfant">Enfant (moins de 18 ans)</option>
                <option value="adulte">Adulte (18-65 ans)</option>
                <option value="senior">Senior (plus de 65 ans)</option>
            </select>
        </div>
        
        <div class="champ">
            <label>
                <input type="checkbox" id="etudiant">
                Je suis étudiant (réduction de 2€)
            </label>
        </div>
        
        <button id="calculer">Calculer le tarif</button>
    </div>
    
    <div id="resultat"></div>
    
    <script>
        // 1. RÉCUPÉRATION DES ÉLÉMENTS
        const categorieSelect = document.getElementById('categorie');
        const etudiantCheck = document.getElementById('etudiant');
        const calculerBtn = document.getElementById('calculer');
        const resultatDiv = document.getElementById('resultat');
        
        // 2. FONCTION DE CALCUL
        function calculerTarif() {
            // Récupérer les valeurs
            const categorie = categorieSelect.value;
            const estEtudiant = etudiantCheck.checked;
            
            // Vérifier qu'une catégorie est sélectionnée
            if (categorie === "") {
                alert("Veuillez choisir une catégorie d'âge !");
                return;
            }
            
            // Variable pour stocker le tarif
            let tarif = 0;
            
            // 3. CONDITIONS POUR DÉTERMINER LE TARIF DE BASE
            if (categorie === "enfant") {
                tarif = 5;
            } else if (categorie === "adulte") {
                tarif = 10;
            } else if (categorie === "senior") {
                tarif = 7;
            } else {
                alert("Catégorie non reconnue !");
                return;
            }
            
            // 4. RÉDUCTION ÉTUDIANT
            if (estEtudiant === true) {
                tarif = tarif - 2;
                // S'assurer que le tarif ne soit pas négatif
                if (tarif < 0) {
                    tarif = 0;
                }
            }
            
            // 5. AFFICHER LE RÉSULTAT
            let message = "Tarif : " + tarif + " euros";
            
            if (estEtudiant) {
                message = message + " (réduction étudiant appliquée)";
            }
            
            resultatDiv.textContent = message;
            resultatDiv.style.display = "block";
            
            // Afficher aussi dans la console
            console.log("Catégorie :", categorie);
            console.log("Étudiant :", estEtudiant);
            console.log("Tarif final :", tarif);
        }
        
        // 6. ÉCOUTEUR D'ÉVÉNEMENT
        calculerBtn.addEventListener('click', calculerTarif);
    </script>
</body>
</html>
```

**Test :** Essayez différentes combinaisons pour vérifier que les conditions fonctionnent.

## Exercice Avancé

Ajoutez une réduction famille : si l'utilisateur coche "Famille nombreuse", réduction supplémentaire de 3 euros.

## Points Clés à Retenir

1. `if` teste une condition et exécute du code si elle est vraie
2. `else` exécute du code si la condition est fausse
3. `else if` teste une autre condition
4. On peut enchaîner autant de `else if` que nécessaire
5. `===` teste l'égalité, `!==` teste la différence
6. `&&` = ET (les deux conditions), `||` = OU (au moins une)
7. `return` arrête la fonction immédiatement
8. Les conditions imbriquées permettent des décisions complexes

## Organigramme d'une Condition

```
Début
  ↓
Condition ?
  ↓         ↓
 OUI       NON
  ↓         ↓
Code A    Code B
  ↓         ↓
Fin ←------
```

## Application dans Notre Projet

Notre projet utilise des conditions pour :
1. Vérifier que l'utilisateur a fait des choix
2. Déterminer les paramètres selon le profil choisi
3. Adapter le texte selon le rôle choisi
4. Personnaliser les exemples selon profil + rôle

**Structure générale :**
```
Si profil = A → paramètres A
Sinon si profil = B → paramètres B
Sinon si profil = C → paramètres C
...
Sinon → erreur
```

## Pour Aller Plus Loin

Dans le prochain cours, nous verrons comment **organiser et commenter** votre code pour le rendre plus lisible et maintenable.

---

**Durée estimée :** 60 minutes  
**Niveau :** Débutant  
**Prérequis :** Cours 01, 02, 03, 04

