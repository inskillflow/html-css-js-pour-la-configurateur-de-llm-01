# Guide des Cours - Initiation au Développement Web

## Introduction

Bienvenue dans cette série de cours conçue pour vous initier au développement web à travers un projet concret. Ces cours sont progressifs et s'appuient sur le projet "Configurateur de Paramètres LLM".

## Prérequis

- Un ordinateur avec un navigateur web (Chrome, Firefox, Edge)
- Un éditeur de texte (Visual Studio Code recommandé, ou Notepad++)
- Aucune connaissance préalable en programmation requise

## Structure des Cours

Les cours sont numérotés de 01 à 06 et doivent être suivis **dans l'ordre**.

### Cours 01 : Les Bases de HTML
**Fichier :** `01-les-bases-html.md`  
**Durée :** 30 minutes  
**Objectifs :**
- Comprendre la structure d'une page HTML
- Maîtriser les balises essentielles (div, h1, p, select, button)
- Différencier balises ouvrantes et fermantes
- Créer un formulaire simple

**Concepts clés :**
- Balises HTML
- Structure de base (DOCTYPE, html, head, body)
- Attributs (id, class, value)
- Listes déroulantes et boutons

**Quiz inclus :** 3 questions  
**Exercice pratique :** Créer un formulaire HTML simple

---

### Cours 02 : Les Sélecteurs CSS et l'Attribut id
**Fichier :** `02-les-selecteurs-css.md`  
**Durée :** 45 minutes  
**Objectifs :**
- Comprendre le rôle de CSS
- Maîtriser les trois types de sélecteurs (balise, class, id)
- Différencier id et class
- Appliquer des styles de base

**Concepts clés :**
- Sélecteurs CSS (#id, .class, balise)
- Différence entre id (unique) et class (réutilisable)
- Propriétés CSS courantes (color, background, padding, margin)
- Introduction à Tailwind CSS

**Quiz inclus :** 4 questions  
**Exercice pratique :** Styliser une page HTML avec CSS

---

### Cours 03 : Introduction à JavaScript et le DOM
**Fichier :** `03-introduction-javascript.md`  
**Durée :** 45 minutes  
**Objectifs :**
- Comprendre le rôle de JavaScript
- Manipuler le DOM (Document Object Model)
- Récupérer des éléments HTML
- Utiliser les variables (const et let)

**Concepts clés :**
- Le DOM (représentation de la page)
- `document.getElementById()`
- Variables (const vs let)
- `.value` et `.textContent`
- `console.log()` pour déboguer

**Quiz inclus :** 4 questions  
**Exercice pratique :** Récupérer et modifier des éléments HTML

---

### Cours 04 : Les Événements en JavaScript
**Fichier :** `04-les-evenements-javascript.md`  
**Durée :** 50 minutes  
**Objectifs :**
- Comprendre les événements (click, change)
- Utiliser addEventListener
- Créer des fonctions
- Réagir aux actions de l'utilisateur

**Concepts clés :**
- Événements (click, change)
- `addEventListener('type', fonction)`
- Fonctions nommées vs anonymes
- Récupérer les valeurs des formulaires

**Quiz inclus :** 4 questions  
**Exercice pratique :** Créer une page interactive avec événements

---

### Cours 05 : Les Conditions if/else
**Fichier :** `05-conditions-if-else.md`  
**Durée :** 60 minutes  
**Objectifs :**
- Prendre des décisions dans le code
- Maîtriser if/else/else if
- Utiliser les opérateurs de comparaison
- Combiner plusieurs conditions

**Concepts clés :**
- Structures conditionnelles (if, else, else if)
- Opérateurs de comparaison (===, !==, >, <, >=, <=)
- Opérateurs logiques (&&, ||, !)
- Conditions imbriquées
- Le mot-clé `return`

**Quiz inclus :** 4 questions  
**Exercice pratique :** Calculateur de tarif avec conditions multiples

---

### Cours 06 : Organisation et Bonnes Pratiques
**Fichier :** `06-organisation-du-code.md`  
**Durée :** 60 minutes  
**Objectifs :**
- Écrire du code lisible et maintenable
- Organiser son code en sections
- Commenter efficacement
- Adopter les bonnes pratiques professionnelles

**Concepts clés :**
- Commentaires pertinents
- Nommage des variables (camelCase)
- Indentation et espacement
- Organisation en sections
- Principe DRY (Don't Repeat Yourself)
- Gestion des erreurs
- Débogage avec console.log

**Quiz inclus :** 4 questions  
**Exercice pratique :** Refactoriser du code mal écrit

---

## Projet Principal : Configurateur de Paramètres LLM

Le fichier `index.html` contient le projet complet qui utilise tous les concepts enseignés.

### Fonctionnalités du Projet

1. **Deux listes déroulantes :**
   - Profil de réponse (6 options)
   - Rôle du modèle (5 options)

2. **Bouton d'application :**
   - Déclenche les calculs
   - Vérifie les sélections

3. **Affichage dynamique :**
   - Paramètres configurés (Temperature, Max Tokens, etc.)
   - Prompt généré
   - Exemple de réponse attendue

### Concepts Appliqués dans le Projet

| Cours | Concepts Utilisés dans index.html |
|-------|-----------------------------------|
| 01 | Structure HTML, select, button, div |
| 02 | Attributs id, classes Tailwind CSS |
| 03 | getElementById, variables const/let |
| 04 | addEventListener, fonctions |
| 05 | if/else if pour profils et rôles |
| 06 | Commentaires, organisation en sections |

## Parcours d'Apprentissage Recommandé

### Semaine 1 : HTML et CSS
- **Jour 1-2 :** Cours 01 (HTML)
  - Lire le cours
  - Faire le quiz
  - Réaliser l'exercice
  - Observer le HTML de index.html

- **Jour 3-4 :** Cours 02 (CSS)
  - Lire le cours
  - Faire le quiz
  - Réaliser l'exercice
  - Observer les classes CSS de index.html

### Semaine 2 : JavaScript de Base
- **Jour 1-2 :** Cours 03 (JavaScript et DOM)
  - Lire le cours
  - Faire le quiz
  - Réaliser l'exercice
  - Identifier les getElementById dans index.html

- **Jour 3-4 :** Cours 04 (Événements)
  - Lire le cours
  - Faire le quiz
  - Réaliser l'exercice
  - Trouver les addEventListener dans index.html

### Semaine 3 : Logique et Bonnes Pratiques
- **Jour 1-2 :** Cours 05 (Conditions)
  - Lire le cours
  - Faire le quiz
  - Réaliser l'exercice
  - Analyser les if/else de index.html

- **Jour 3-4 :** Cours 06 (Organisation)
  - Lire le cours
  - Faire le quiz
  - Réaliser l'exercice
  - Refactoriser un de vos anciens exercices

### Semaine 4 : Projet Personnel
- **Créez votre propre configurateur !**
  - Inspirez-vous de index.html
  - Choisissez un autre thème (calculateur de prix, quiz, configurateur de produit)
  - Appliquez tous les concepts appris

## Méthode de Travail

### Pour Chaque Cours

1. **Lire attentivement** le cours
2. **Tester les exemples** dans un fichier HTML
3. **Répondre au quiz** (ne pas tricher !)
4. **Réaliser l'exercice pratique** entièrement
5. **Comparer** votre solution avec celle proposée
6. **Analyser** le code de index.html pour voir le concept appliqué

### Outils Nécessaires

**Navigateur avec Console :**
- Appuyez sur **F12** pour ouvrir les outils de développement
- Onglet **Console** : pour voir les console.log() et les erreurs
- Onglet **Éléments** : pour voir le HTML et CSS en temps réel

**Éditeur de Code Recommandé :**
- Visual Studio Code (gratuit)
  - Extension : Live Server (pour recharger automatiquement)
  - Extension : Prettier (pour formater le code)

## Ressources Complémentaires

### Documentation en Ligne
- MDN Web Docs (Mozilla) : Documentation de référence
- W3Schools : Tutoriels et exemples

### Pratique Supplémentaire
- FreeCodeCamp : Exercices interactifs gratuits
- Codecademy : Cours interactifs

### Communauté
- Stack Overflow : Pour poser des questions
- Reddit r/learnprogramming : Communauté d'entraide

## Foire aux Questions (FAQ)

### Pourquoi commencer par HTML/CSS/JavaScript ?
Ce sont les trois langages fondamentaux du web. Tout ce qui s'affiche dans un navigateur utilise ces trois technologies.

### Combien de temps faut-il pour maîtriser ces bases ?
Avec une pratique régulière (1-2 heures par jour), comptez 3 à 4 semaines pour bien assimiler ces concepts de base.

### Faut-il tout mémoriser ?
Non ! Comprenez les concepts et la logique. Vous pouvez toujours consulter la documentation pour les détails de syntaxe.

### Que faire si je ne comprends pas un concept ?
1. Relisez la section concernée
2. Testez les exemples vous-même
3. Modifiez les exemples pour voir ce qui change
4. Cherchez des explications alternatives en ligne
5. Demandez de l'aide à votre enseignant

### Puis-je sauter des cours ?
Non, les cours sont progressifs. Chaque cours s'appuie sur les précédents. Suivez-les dans l'ordre.

### Que faire après ces 6 cours ?
- Créez vos propres projets personnels
- Apprenez un framework (React, Vue.js)
- Explorez le backend (Node.js, PHP, Python)
- Approfondissez CSS avec Flexbox et Grid
- Découvrez les API et AJAX

## Conseils de Votre Professeur

### Pour Réussir

1. **Pratiquez tous les jours**, même 30 minutes
2. **Ne copiez pas** les solutions sans comprendre
3. **Expérimentez** : modifiez les exemples pour voir ce qui se passe
4. **Faites des erreurs** : c'est en se trompant qu'on apprend
5. **Commentez votre code** : ça vous force à comprendre
6. **Prenez des pauses** : votre cerveau a besoin de repos
7. **Enseignez** à quelqu'un d'autre : c'est la meilleure façon d'apprendre

### Erreurs Courantes à Éviter

1. Aller trop vite sans pratiquer
2. Sauter les exercices
3. Ne pas tester son code régulièrement
4. Ignorer les messages d'erreur dans la console
5. Copier du code sans le comprendre
6. Ne pas commenter son code
7. Abandonner au premier obstacle

### Progression Normale

- **Semaine 1 :** Tout semble nouveau et difficile (normal !)
- **Semaine 2 :** Vous commencez à comprendre la logique
- **Semaine 3 :** Les concepts s'assemblent dans votre tête
- **Semaine 4 :** Vous êtes capable de créer vos propres projets simples

## Évaluation de vos Compétences

Après avoir terminé tous les cours, vous devriez être capable de :

- [ ] Créer une page HTML structurée
- [ ] Styliser une page avec CSS (ou Tailwind)
- [ ] Récupérer des éléments HTML en JavaScript
- [ ] Réagir aux clics et changements
- [ ] Utiliser des conditions pour prendre des décisions
- [ ] Organiser votre code de manière professionnelle
- [ ] Déboguer votre code avec la console
- [ ] Créer un petit projet interactif complet

## Projet Final Suggéré

Créez un **Configurateur de Pizza** qui :
1. Propose des tailles (Petite, Moyenne, Grande)
2. Propose des ingrédients (cases à cocher)
3. Calcule le prix selon les choix
4. Affiche un résumé de la commande
5. Applique des réductions selon conditions

Ce projet utilise tous les concepts des 6 cours !

## Contact et Support

Pour toute question sur les cours :
- Consultez d'abord la FAQ ci-dessus
- Relisez attentivement le cours concerné
- Testez les exemples fournis
- Contactez votre enseignant


**Bon courage dans votre apprentissage !**


