# Cours 06 : Organisation et Bonnes Pratiques

## Introduction

Écrire du code qui fonctionne, c'est bien. Écrire du code **lisible et maintenable**, c'est mieux ! Ce cours vous apprend à organiser votre code comme un professionnel.

## Pourquoi Organiser son Code ?

Un code bien organisé est :
- Plus **facile à lire** et à comprendre
- Plus **simple à modifier** ou corriger
- Plus **rapide à déboguer**
- Plus **agréable** pour vous et vos collègues

## Les Commentaires

Les commentaires expliquent le code sans l'exécuter. Ils sont essentiels !

### Types de Commentaires

**1. Commentaires de section (grands blocs)**

```javascript
// ============================================
// 1. RÉCUPÉRATION DES ÉLÉMENTS HTML
// ============================================
const profileSelect = document.getElementById('profile');
const roleSelect = document.getElementById('role');
```

**2. Commentaires explicatifs**

```javascript
// On vérifie que l'utilisateur a bien fait ses choix
if (profilChoisi === "" || roleChoisi === "") {
    alert("Veuillez sélectionner un profil ET un rôle !");
    return;  // Arrêter la fonction si pas de sélection
}
```

**3. Commentaires de documentation**

```javascript
/**
 * Fonction qui applique la configuration selon les choix
 * Cette fonction est appelée quand on clique sur "Appliquer"
 */
function appliquerConfiguration() {
    // ...
}
```

### Quand Commenter ?

**À FAIRE :**
- Expliquer le POURQUOI, pas le QUOI
- Commenter les parties complexes
- Décrire les fonctions importantes

**À ÉVITER :**
```javascript
// Mauvais : répète ce que fait le code
let age = 25;  // Créer une variable age avec 25

// Bon : explique pourquoi
let age = 25;  // Âge minimum requis pour l'inscription
```

## Nommer les Variables

Le nom d'une variable doit être **clair et descriptif**.

### Bonnes Pratiques

**Convention camelCase en JavaScript :**
```javascript
const profilChoisi = "factuel-court";
const maxTokensValue = 250;
const tempValue = 0.3;
```

**Règles :**
- Commencer par une minuscule
- Première lettre de chaque mot suivant en majuscule
- Pas d'espaces, pas d'accents, pas de tirets

### Exemples de Bons Noms

```javascript
// BON : descriptif et clair
const boutonValider = document.getElementById('valider');
const temperatureCourante = 0.5;
const estEtudiant = true;

// MAUVAIS : trop court, peu clair
const btn = document.getElementById('valider');
const temp = 0.5;
const e = true;
```

### Types de Noms

**Variables qui stockent des éléments HTML :**
```javascript
const profileSelect = document.getElementById('profile');
const applyBtn = document.getElementById('applyBtn');
```

**Variables qui stockent des valeurs :**
```javascript
let temperature = 0;
let maxTokens = 0;
const profilChoisi = "factuel-court";
```

**Variables booléennes (vrai/faux) :**
```javascript
const estValide = true;
const aUnRole = false;
```

## Organisation d'un Fichier JavaScript

Notre projet suit une structure claire en 6 sections.

### Structure Recommandée

```javascript
// ============================================
// 1. RÉCUPÉRATION DES ÉLÉMENTS HTML
// ============================================
const element1 = document.getElementById('id1');
const element2 = document.getElementById('id2');

// ============================================
// 2. DÉCLARATION DES CONSTANTES
// ============================================
const TARIF_ADULTE = 10;
const TARIF_ENFANT = 5;

// ============================================
// 3. FONCTIONS
// ============================================
function maFonction() {
    // Code de la fonction
}

// ============================================
// 4. ÉCOUTEURS D'ÉVÉNEMENTS
// ============================================
bouton.addEventListener('click', maFonction);
```

### Exemple du Projet

```javascript
// 1. RÉCUPÉRATION DES ÉLÉMENTS HTML
const profileSelect = document.getElementById('profile');
const roleSelect = document.getElementById('role');
const applyBtn = document.getElementById('applyBtn');

// 2. FONCTION PRINCIPALE AVEC IF/ELSE
function appliquerConfiguration() {
    // Récupérer les valeurs sélectionnées
    const profilChoisi = profileSelect.value;
    const roleChoisi = roleSelect.value;
    
    // Vérification
    if (profilChoisi === "" || roleChoisi === "") {
        alert("Veuillez sélectionner un profil ET un rôle !");
        return;
    }
    
    // Variables pour stocker les paramètres
    let temperature = 0;
    let maxTokens = 0;
    
    // Conditions selon le profil
    if (profilChoisi === "factuel-court") {
        temperature = 0.3;
        maxTokens = 60;
    } else if (profilChoisi === "creatif-court") {
        temperature = 0.8;
        maxTokens = 70;
    }
    
    // Affichage des résultats
    tempValue.textContent = temperature;
    maxTokensValue.textContent = maxTokens;
}

// 3. ÉCOUTEUR D'ÉVÉNEMENT
applyBtn.addEventListener('click', appliquerConfiguration);
```

## Indentation et Espacement

L'indentation rend le code lisible en montrant la structure.

### Règles d'Indentation

**Chaque niveau = 4 espaces (ou 1 tabulation)**

```javascript
function calculer() {
    if (age >= 18) {
        if (etudiant) {
            tarif = tarif - 2;
        }
    }
}
```

**Espaces autour des opérateurs :**
```javascript
// BON
let total = prix + taxe;
if (age >= 18) {

// MAUVAIS
let total=prix+taxe;
if(age>=18){
```

## Découper le Code en Fonctions

Une fonction doit faire **une seule chose** et la faire bien.

### Mauvais Exemple

```javascript
// Fonction qui fait TOUT
function toutFaire() {
    const age = prompt("Âge ?");
    let tarif = 0;
    if (age < 18) tarif = 5;
    else tarif = 10;
    const reduction = prompt("Étudiant ?");
    if (reduction === "oui") tarif = tarif - 2;
    alert("Tarif : " + tarif);
}
```

### Bon Exemple

```javascript
// Fonctions séparées, chacune avec un rôle précis

function calculerTarifBase(age) {
    if (age < 18) {
        return 5;
    } else {
        return 10;
    }
}

function appliquerReduction(tarif, estEtudiant) {
    if (estEtudiant) {
        return tarif - 2;
    }
    return tarif;
}

function afficherTarif(tarif) {
    alert("Votre tarif : " + tarif + " euros");
}

// Utilisation
const age = 20;
const etudiant = true;
let tarif = calculerTarifBase(age);
tarif = appliquerReduction(tarif, etudiant);
afficherTarif(tarif);
```

## Éviter la Répétition (DRY)

DRY = "Don't Repeat Yourself" (Ne vous répétez pas)

### Mauvais Exemple

```javascript
if (profil === "A") {
    tempValue.textContent = 0.3;
    maxTokensValue.textContent = 60;
    topPValue.textContent = 0.9;
}
if (profil === "B") {
    tempValue.textContent = 0.4;
    maxTokensValue.textContent = 250;
    topPValue.textContent = 0.9;
}
```

### Bon Exemple

```javascript
function afficherParametres(temp, tokens, topP) {
    tempValue.textContent = temp;
    maxTokensValue.textContent = tokens;
    topPValue.textContent = topP;
}

if (profil === "A") {
    afficherParametres(0.3, 60, 0.9);
}
if (profil === "B") {
    afficherParametres(0.4, 250, 0.9);
}
```

## Gestion des Erreurs

Toujours vérifier les entrées utilisateur.

### Exemple du Projet

```javascript
// Vérifier qu'un profil et un rôle sont sélectionnés
if (profilChoisi === "" || roleChoisi === "") {
    alert("Veuillez sélectionner un profil ET un rôle !");
    return;  // Arrêter si problème
}

// Vérifier que le profil existe
if (profilChoisi !== "factuel-court" && 
    profilChoisi !== "creatif-court" && 
    profilChoisi !== "factuel-developpe") {
    alert("Profil non reconnu !");
    return;
}
```

## Console.log pour Déboguer

Utilisez `console.log()` pour comprendre ce qui se passe.

### Stratégie de Débogage

```javascript
function calculerTarif(age, etudiant) {
    console.log("=== DÉBUT calculerTarif ===");
    console.log("Âge reçu :", age);
    console.log("Étudiant :", etudiant);
    
    let tarif = 0;
    
    if (age < 18) {
        tarif = 5;
        console.log("Tarif enfant appliqué :", tarif);
    } else {
        tarif = 10;
        console.log("Tarif adulte appliqué :", tarif);
    }
    
    if (etudiant) {
        tarif = tarif - 2;
        console.log("Réduction étudiant appliquée. Nouveau tarif :", tarif);
    }
    
    console.log("Tarif final :", tarif);
    console.log("=== FIN calculerTarif ===");
    
    return tarif;
}
```

**Résultat dans la console :**
```
=== DÉBUT calculerTarif ===
Âge reçu : 20
Étudiant : true
Tarif adulte appliqué : 10
Réduction étudiant appliquée. Nouveau tarif : 8
Tarif final : 8
=== FIN calculerTarif ===
```

## Quiz Pratique

### Question 1
Quelle convention de nommage utilise-t-on en JavaScript ?

**Réponse :** camelCase (première lettre minuscule, majuscules pour les mots suivants)

### Question 2
Qu'est-ce que le principe DRY ?

**Réponse :** "Don't Repeat Yourself" - Ne pas répéter le même code, utiliser des fonctions.

### Question 3
Où doit-on placer les commentaires ?

**Réponse :** 
- Au début des sections importantes
- Pour expliquer le POURQUOI d'un code complexe
- Documenter les fonctions

### Question 4
Comment débogue-t-on efficacement son code ?

**Réponse :** Avec `console.log()` pour afficher les valeurs des variables à différentes étapes.

## Exercice Pratique : Refactoriser du Code

**Objectif :** Améliorer un code mal organisé.

### Code de Départ (Mauvais)

```javascript
const b=document.getElementById('bouton');
const r=document.getElementById('resultat');
b.addEventListener('click',function(){
const a=document.getElementById('age').value;
if(a<18){r.textContent="5 euros";}
else if(a>=18&&a<65){r.textContent="10 euros";}
else{r.textContent="7 euros";}
});
```

### Votre Mission

Réécrivez ce code avec :
1. Des noms de variables clairs
2. Des commentaires
3. Une fonction séparée pour le calcul
4. Une bonne indentation

### Solution

```javascript
// ============================================
// 1. RÉCUPÉRATION DES ÉLÉMENTS
// ============================================
const boutonCalculer = document.getElementById('bouton');
const resultatDiv = document.getElementById('resultat');
const champAge = document.getElementById('age');

// ============================================
// 2. FONCTION DE CALCUL DU TARIF
// ============================================
/**
 * Calcule le tarif selon l'âge
 * @param {number} age - L'âge de la personne
 * @returns {number} Le tarif en euros
 */
function calculerTarifSelonAge(age) {
    console.log("Calcul du tarif pour l'âge :", age);
    
    let tarif = 0;
    
    if (age < 18) {
        // Tarif enfant
        tarif = 5;
    } else if (age >= 18 && age < 65) {
        // Tarif adulte
        tarif = 10;
    } else {
        // Tarif senior
        tarif = 7;
    }
    
    console.log("Tarif calculé :", tarif);
    return tarif;
}

// ============================================
// 3. FONCTION D'AFFICHAGE
// ============================================
function afficherResultat() {
    // Récupérer l'âge saisi
    const age = parseInt(champAge.value);
    
    // Vérifier que l'âge est valide
    if (isNaN(age) || age < 0) {
        resultatDiv.textContent = "Veuillez entrer un âge valide";
        return;
    }
    
    // Calculer et afficher le tarif
    const tarif = calculerTarifSelonAge(age);
    resultatDiv.textContent = tarif + " euros";
}

// ============================================
// 4. ÉCOUTEUR D'ÉVÉNEMENT
// ============================================
boutonCalculer.addEventListener('click', afficherResultat);
```

## Points Clés à Retenir

1. **Commentez** votre code pour expliquer le pourquoi
2. **Nommez** clairement vos variables (camelCase)
3. **Indentez** correctement (4 espaces par niveau)
4. **Organisez** en sections logiques
5. **Découpez** en fonctions (une fonction = une tâche)
6. **Ne répétez pas** le code (principe DRY)
7. **Vérifiez** les entrées utilisateur
8. **Déboguez** avec console.log()

## Checklist de Code Propre

Avant de considérer votre code terminé, vérifiez :

- [ ] Tous les éléments HTML ont des id ou class clairs
- [ ] Les variables ont des noms descriptifs
- [ ] Le code est indenté correctement
- [ ] Les sections principales sont commentées
- [ ] Les fonctions complexes sont expliquées
- [ ] Pas de code répété inutilement
- [ ] Les entrées utilisateur sont vérifiées
- [ ] Le code fonctionne sans erreur dans la console
- [ ] Vous pouvez relire le code 1 mois plus tard et le comprendre

## Comparaison : Avant / Après

### Avant (Code Débutant)

```javascript
const p=document.getElementById('p');
const r=document.getElementById('r');
const b=document.getElementById('b');
b.addEventListener('click',function(){
const v=p.value;
if(v==="factuel-court"){
r.textContent="0.3";
}else if(v==="creatif-court"){
r.textContent="0.8";
}
});
```

### Après (Code Professionnel)

```javascript
// ============================================
// RÉCUPÉRATION DES ÉLÉMENTS HTML
// ============================================
const profilSelect = document.getElementById('profile');
const temperatureDisplay = document.getElementById('temperature');
const boutonAppliquer = document.getElementById('appliquer');

// ============================================
// FONCTION PRINCIPALE
// ============================================
/**
 * Applique les paramètres selon le profil choisi
 */
function appliquerParametres() {
    const profilChoisi = profilSelect.value;
    
    // Déterminer la température selon le profil
    let temperature = 0;
    
    if (profilChoisi === "factuel-court") {
        temperature = 0.3;  // Température basse pour précision
    } else if (profilChoisi === "creatif-court") {
        temperature = 0.8;  // Température haute pour créativité
    }
    
    // Afficher le résultat
    temperatureDisplay.textContent = temperature;
    console.log("Température appliquée :", temperature);
}

// ============================================
// ÉCOUTEUR D'ÉVÉNEMENT
// ============================================
boutonAppliquer.addEventListener('click', appliquerParametres);
```

## Pour Aller Plus Loin

Maintenant que vous maîtrisez les bases, vous pouvez :
- Créer des projets plus complexes
- Apprendre à utiliser des frameworks (React, Vue.js)
- Explorer les API externes
- Approfondir la manipulation du DOM
- Étudier les animations CSS et JavaScript

**Conseil de professeur :** La meilleure façon d'apprendre est de **pratiquer régulièrement**. Créez vos propres petits projets, même simples !

---

**Durée estimée :** 60 minutes  
**Niveau :** Débutant à Intermédiaire  
**Prérequis :** Cours 01 à 05

