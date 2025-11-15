# Cours 07 : Exercices Pratiques sur index.html

## Introduction

Maintenant que vous avez suivi les 6 premiers cours, il est temps de **mettre en pratique** vos connaissances en modifiant directement le fichier `index.html`.

Ces exercices sont **progressifs** et **simples**. Chaque exercice vous demande d'ajouter ou de modifier un petit élément de la page.

## Objectif

Vérifier que vous maîtrisez :
- L'ajout d'éléments HTML
- L'application de styles CSS
- L'ajout d'interactivité JavaScript

## Comment Travailler

1. Ouvrez `index.html` dans votre éditeur de code
2. Ouvrez aussi `index.html` dans votre navigateur (pour voir les résultats)
3. Faites les exercices **dans l'ordre**
4. Testez après chaque modification (rafraîchissez le navigateur avec F5)
5. Utilisez F12 pour ouvrir la console et vérifier les erreurs

---

## Exercice 1 : Ajouter un Paragraphe (HTML)

**Niveau :** Très facile  
**Durée :** 5 minutes

### Consigne

Ajoutez un paragraphe dans la section En-tête pour indiquer la date.

### Où Modifier

Trouvez la section En-tête (ligne ~15), juste après le paragraphe existant.

### Code à Ajouter

```html
<p class="text-gray-500 text-sm">Dernière mise à jour : Novembre 2024</p>
```

### Résultat Attendu

Un petit texte gris s'affiche sous la description principale.

### Vérification

- Le texte apparaît-il en gris et en petite taille ?
- Est-il bien positionné sous la description ?

---

## Exercice 2 : Ajouter une Nouvelle Option (HTML)

**Niveau :** Très facile  
**Durée :** 5 minutes

### Consigne

Ajoutez une nouvelle option "Assistant Technique" dans la liste déroulante des rôles.

### Où Modifier

Dans le `<select id="role">` (ligne ~48), ajoutez une nouvelle `<option>`.

### Code à Ajouter

```html
<option value="assistant-technique">Assistant Technique</option>
```

**Attention :** Ajoutez-la APRÈS la dernière option existante, mais AVANT la balise `</select>`.

### Résultat Attendu

Une nouvelle option "Assistant Technique" apparaît dans la liste déroulante.

### Vérification

- La nouvelle option apparaît-elle dans la liste ?
- Pouvez-vous la sélectionner ?

**Note :** Pour l'instant, elle ne fera rien car le JavaScript n'est pas modifié. C'est normal !

---

## Exercice 3 : Changer une Couleur (CSS Tailwind)

**Niveau :** Facile  
**Durée :** 5 minutes

### Consigne

Changez la couleur du bouton "Appliquer la configuration" de bleu à vert.

### Où Modifier

Trouvez le bouton avec `id="applyBtn"` (ligne ~61).

### Modification à Faire

**Remplacez :**
```html
class="mt-6 w-full bg-blue-600 hover:bg-blue-700 text-white font-semibold py-3 px-6 rounded-lg transition-colors shadow-md"
```

**Par :**
```html
class="mt-6 w-full bg-green-600 hover:bg-green-700 text-white font-semibold py-3 px-6 rounded-lg transition-colors shadow-md"
```

**Explication :** On change `bg-blue-600` en `bg-green-600` et `hover:bg-blue-700` en `hover:bg-green-700`.

### Résultat Attendu

Le bouton est maintenant vert au lieu de bleu, et devient vert foncé au survol.

### Vérification

- Le bouton est-il vert ?
- Change-t-il de teinte quand vous passez la souris dessus ?

---

## Exercice 4 : Ajouter un Message d'Accueil (JavaScript)

**Niveau :** Facile  
**Durée :** 10 minutes

### Consigne

Affichez un message dans la console quand la page se charge.

### Où Modifier

À la fin de la section JavaScript, juste après le dernier `addEventListener` (ligne ~405).

### Code à Ajouter

```javascript
// 7. MESSAGE DE BIENVENUE
console.log("=================================");
console.log("Configurateur de Paramètres LLM");
console.log("Page chargée avec succès !");
console.log("=================================");
```

### Résultat Attendu

Quand vous rafraîchissez la page, un message s'affiche dans la console (F12).

### Vérification

- Ouvrez la console (F12)
- Rafraîchissez la page (F5)
- Voyez-vous le message encadré de lignes ?

---

## Exercice 5 : Ajouter un Compteur de Clics (JavaScript)

**Niveau :** Moyen  
**Durée :** 15 minutes

### Consigne

Ajoutez un compteur qui affiche combien de fois l'utilisateur a cliqué sur le bouton "Appliquer".

### Étape 1 : Ajouter un Paragraphe HTML

Juste après le bouton "Appliquer" (ligne ~63), ajoutez :

```html
<p id="compteur" class="mt-4 text-center text-gray-600 text-sm"></p>
```

### Étape 2 : Ajouter le JavaScript

Dans la section JavaScript, ajoutez :

**1. Récupérer l'élément (avec les autres récupérations, ligne ~205) :**
```javascript
const compteurElement = document.getElementById('compteur');
```

**2. Créer une variable compteur (ligne ~207, avant la fonction) :**
```javascript
// Variable pour compter les clics
let nombreClics = 0;
```

**3. Modifier la fonction appliquerConfiguration**

Au **début** de la fonction `appliquerConfiguration()` (ligne ~210), ajoutez :

```javascript
// Incrémenter le compteur
nombreClics = nombreClics + 1;
compteurElement.textContent = "Nombre de configurations appliquées : " + nombreClics;
console.log("Clic numéro :", nombreClics);
```

### Résultat Attendu

- Un texte sous le bouton affiche le nombre de clics
- Le nombre augmente à chaque clic sur "Appliquer"
- Le nombre s'affiche aussi dans la console

### Vérification

- Cliquez plusieurs fois sur "Appliquer" (même sans sélection)
- Le compteur augmente-t-il ?
- Voyez-vous les messages dans la console ?

---

## Exercice 6 : Ajouter un Bouton de Réinitialisation (HTML + JavaScript)

**Niveau :** Moyen  
**Durée :** 15 minutes

### Consigne

Ajoutez un bouton pour réinitialiser les sélections et masquer les résultats.

### Étape 1 : Ajouter le Bouton HTML

Juste après le bouton "Appliquer" (ligne ~63), ajoutez :

```html
<button id="resetBtn" 
        class="mt-3 w-full bg-red-600 hover:bg-red-700 text-white font-semibold py-3 px-6 rounded-lg transition-colors shadow-md">
    Réinitialiser
</button>
```

### Étape 2 : Ajouter le JavaScript

**1. Récupérer le bouton (avec les autres éléments, ligne ~192) :**
```javascript
const resetBtn = document.getElementById('resetBtn');
```

**2. Créer la fonction de réinitialisation (après la fonction appliquerConfiguration, ligne ~380) :**

```javascript
// Fonction pour réinitialiser la page
function reinitialiser() {
    console.log("Réinitialisation en cours...");
    
    // Réinitialiser les listes déroulantes
    profileSelect.value = "";
    roleSelect.value = "";
    
    // Masquer les résultats
    parametersDisplay.classList.add('hidden');
    
    // Message de confirmation
    console.log("Page réinitialisée !");
}
```

**3. Ajouter l'écouteur d'événement (avec les autres écouteurs, ligne ~395) :**

```javascript
// Écouteur pour le bouton réinitialiser
resetBtn.addEventListener('click', reinitialiser);
```

### Résultat Attendu

- Un bouton rouge "Réinitialiser" apparaît sous le bouton vert
- Quand on clique dessus :
  - Les listes déroulantes se vident
  - Les résultats se masquent
  - Un message apparaît dans la console

### Vérification

1. Choisissez un profil et un rôle
2. Cliquez sur "Appliquer"
3. Cliquez sur "Réinitialiser"
4. Les sélections sont-elles revenues à "--Choisir--" ?
5. Les résultats ont-ils disparu ?

---

## Exercice 7 : Ajouter une Validation Visuelle (CSS + JavaScript)

**Niveau :** Moyen à Difficile  
**Durée :** 20 minutes

### Consigne

Ajoutez une bordure rouge aux listes déroulantes si l'utilisateur clique sur "Appliquer" sans faire de sélection.

### Modification du JavaScript

Dans la fonction `appliquerConfiguration()`, trouvez la section de vérification (ligne ~215).

**Remplacez :**
```javascript
if (profilChoisi === "" || roleChoisi === "") {
    alert("Veuillez sélectionner un profil ET un rôle !");
    return;
}
```

**Par :**
```javascript
if (profilChoisi === "" || roleChoisi === "") {
    alert("Veuillez sélectionner un profil ET un rôle !");
    
    // Ajouter une bordure rouge si pas de sélection
    if (profilChoisi === "") {
        profileSelect.classList.add('border-red-500');
        profileSelect.classList.remove('border-gray-300');
    }
    if (roleChoisi === "") {
        roleSelect.classList.add('border-red-500');
        roleSelect.classList.remove('border-gray-300');
    }
    
    return;
}

// Si tout est OK, enlever les bordures rouges
profileSelect.classList.remove('border-red-500');
profileSelect.classList.add('border-gray-300');
roleSelect.classList.remove('border-red-500');
roleSelect.classList.add('border-gray-300');
```

### Résultat Attendu

- Si vous cliquez sur "Appliquer" sans sélection, les listes déroulantes ont une bordure rouge
- Quand vous faites une sélection et cliquez sur "Appliquer", les bordures redeviennent grises

### Vérification

1. Cliquez sur "Appliquer" sans rien sélectionner
2. Les bordures deviennent-elles rouges ?
3. Faites les sélections et cliquez sur "Appliquer"
4. Les bordures redeviennent-elles grises ?

---

## Exercice 8 : Afficher la Date et l'Heure (JavaScript)

**Niveau :** Facile  
**Durée :** 10 minutes

### Consigne

Ajoutez un élément qui affiche la date et l'heure actuelles quand on applique la configuration.

### Étape 1 : Ajouter l'Élément HTML

Dans la section "Rôle Sélectionné" (ligne ~73), ajoutez après le `<p id="selectedRole">` :

```html
<p id="dateHeure" class="text-sm text-gray-500 mt-2"></p>
```

### Étape 2 : Ajouter le JavaScript

**1. Récupérer l'élément (ligne ~205) :**
```javascript
const dateHeureElement = document.getElementById('dateHeure');
```

**2. Dans la fonction appliquerConfiguration, juste avant l'affichage final (ligne ~375) :**

```javascript
// Afficher la date et l'heure
const maintenant = new Date();
const dateFormatee = maintenant.toLocaleDateString('fr-FR');
const heureFormatee = maintenant.toLocaleTimeString('fr-FR');
dateHeureElement.textContent = "Configuration appliquée le " + dateFormatee + " à " + heureFormatee;
```

### Résultat Attendu

Quand vous cliquez sur "Appliquer", la date et l'heure s'affichent sous le rôle sélectionné.

### Vérification

- La date et l'heure s'affichent-elles au format français ?
- Se mettent-elles à jour à chaque clic ?

---

## Exercice Bonus : Ajouter un Mode Sombre (Difficile)

**Niveau :** Difficile  
**Durée :** 30 minutes

### Consigne

Ajoutez un bouton pour passer la page en mode sombre.

### Étape 1 : Ajouter le Bouton HTML

Dans la section En-tête (ligne ~18), ajoutez :

```html
<button id="toggleDark" 
        class="mt-3 px-4 py-2 bg-gray-800 text-white rounded hover:bg-gray-700">
    Mode Sombre
</button>
```

### Étape 2 : Ajouter le JavaScript

**1. Récupérer le bouton (ligne ~192) :**
```javascript
const toggleDarkBtn = document.getElementById('toggleDark');
```

**2. Variable pour suivre l'état (ligne ~207) :**
```javascript
let modeSombre = false;
```

**3. Fonction de basculement (après reinitialiser, ligne ~390) :**

```javascript
function basculerModeSombre() {
    const body = document.body;
    
    if (modeSombre) {
        // Retour au mode clair
        body.classList.remove('bg-gray-900');
        body.classList.add('bg-gray-50');
        toggleDarkBtn.textContent = "Mode Sombre";
        modeSombre = false;
        console.log("Mode clair activé");
    } else {
        // Passage au mode sombre
        body.classList.remove('bg-gray-50');
        body.classList.add('bg-gray-900');
        toggleDarkBtn.textContent = "Mode Clair";
        modeSombre = true;
        console.log("Mode sombre activé");
    }
}
```

**4. Écouteur d'événement (ligne ~400) :**

```javascript
toggleDarkBtn.addEventListener('click', basculerModeSombre);
```

### Résultat Attendu

Un bouton permet de changer le fond de la page de clair à sombre et vice-versa.

### Vérification

- Le bouton change-t-il de texte ?
- Le fond de la page change-t-il de couleur ?
- Pouvez-vous basculer plusieurs fois ?

---

## Récapitulatif des Exercices

| Exercice | Compétence | Difficulté | Durée |
|----------|-----------|------------|-------|
| 1 | HTML (paragraphe) | Très facile | 5 min |
| 2 | HTML (option) | Très facile | 5 min |
| 3 | CSS (couleur) | Facile | 5 min |
| 4 | JavaScript (console) | Facile | 10 min |
| 5 | JS (compteur) | Moyen | 15 min |
| 6 | HTML + JS (bouton reset) | Moyen | 15 min |
| 7 | CSS + JS (validation) | Moyen-Difficile | 20 min |
| 8 | JS (date/heure) | Facile | 10 min |
| Bonus | JS avancé (mode sombre) | Difficile | 30 min |

**Total :** ~2h pour les exercices 1-8, +30 min pour le bonus

---

## Conseils

### Avant de Commencer

1. **Faites une copie** de index.html (nommez-la index-backup.html)
2. Travaillez sur la copie originale
3. Testez après **chaque** exercice

### Si Vous Êtes Bloqué

1. Relisez attentivement la consigne
2. Vérifiez les numéros de ligne (ils peuvent varier légèrement)
3. Ouvrez la console (F12) pour voir les erreurs
4. Comparez avec les exemples des cours précédents

### Erreurs Courantes

**L'élément ne s'affiche pas :**
- Vérifiez l'orthographe de l'id
- Vérifiez que la balise est bien fermée
- Rafraîchissez le navigateur (F5)

**Le JavaScript ne fonctionne pas :**
- Ouvrez la console (F12) pour voir les erreurs
- Vérifiez que getElementById utilise le bon id
- Vérifiez les parenthèses et accolades

**Le CSS ne s'applique pas :**
- Vérifiez l'orthographe des classes Tailwind
- Assurez-vous d'être dans l'attribut class="..."

---

## Auto-Évaluation

Après avoir terminé ces exercices, vous devriez pouvoir :

- [ ] Ajouter des éléments HTML à une page existante
- [ ] Modifier des classes CSS pour changer l'apparence
- [ ] Récupérer des éléments avec getElementById
- [ ] Créer des variables et les modifier
- [ ] Ajouter des écouteurs d'événements
- [ ] Créer des fonctions simples
- [ ] Utiliser console.log pour déboguer
- [ ] Manipuler les classes CSS avec JavaScript

---

## Pour Aller Plus Loin

Une fois ces exercices terminés, essayez de :

1. **Personnaliser complètement** l'apparence (couleurs, polices)
2. **Ajouter d'autres rôles** dans la liste avec leur comportement
3. **Créer un système de sauvegarde** des préférences utilisateur
4. **Ajouter des animations** au changement de paramètres
5. **Créer votre propre configurateur** pour un autre sujet

---

**Bon courage et bonne pratique !**

*Ces exercices progressifs vous permettront de vérifier que vous avez bien assimilé les concepts des cours 01 à 06.*

**Durée totale :** 2h-2h30  
**Niveau :** Débutant à Intermédiaire  
**Prérequis :** Cours 01 à 06 complétés

