## 0. Mise en place (à faire une seule fois)

1. Ouvre ton navigateur (Chrome, Edge ou Firefox).
2. Va sur n’importe quel site (par exemple `https://example.com`).
3. Appuie sur **F12** (ou clic droit → **Inspecter**).
4. Clique sur l’onglet **Console**.

Tout ce qui suit se fait **en tapant du JavaScript dans la console**, puis en appuyant sur **Entrée**.



## 1. Découvrir `console.log` (afficher des messages)

### Objectif

Comprendre que `console.log(...)` sert à **afficher des infos** dans la console.

### Explication rapide

```js
console.log("Bonjour JavaScript !");
console.log(42);
console.log("2 + 2 =", 2 + 2);
```

### Exercices

1. Tape et exécute :

   ```js
   console.log("Je découvre la console JavaScript");
   ```

   → Que vois-tu comme résultat ?

2. Affiche ton prénom et ton âge dans la même ligne, par exemple :

   ```js
   console.log("Prénom :", "Haythem", "Âge :", 40);
   ```

3. Affiche un petit calcul :

   ```js
   console.log("10 + 5 =", 10 + 5);
   console.log("10 * 5 =", 10 * 5);
   ```

4. Crée un message **d’erreur simulé** :

   ```js
   console.log("Erreur : identifiants invalides (simulation)");
   ```

---

## 2. Variables et réutilisation (`let`, `const`)

### Objectif

Apprendre à **stocker des valeurs** dans des variables, puis les afficher.

### Explication rapide

```js
let age = 25;        // variable modifiable
const pays = "Canada"; // constante

console.log(age);
console.log(pays);
```

### Exercices

1. Crée une variable pour ton prénom, puis affiche-la :

   ```js
   let prenom = "Haythem";
   console.log(prenom);
   ```

2. Crée une variable pour ton âge et affiche un message complet :

   ```js
   let age = 40;
   console.log("Je m'appelle", prenom, "et j'ai", age, "ans.");
   ```

3. Modifie ta variable `age` (sans la redéclarer) :

   ```js
   age = age + 1;
   console.log("Anniversaire ! J'ai maintenant", age, "ans.");
   ```

4. Crée une constante pour ta ville et utilise-la dans une phrase :

   ```js
   const ville = "Montréal";
   console.log("Je vis à", ville);
   ```

5. Combine plusieurs valeurs :

   ```js
   let cours = "JavaScript";
   let duree = 4; // en heures
   console.log("Cours :", cours, "- Durée :", duree, "heures");
   ```

---

## 3. Travailler avec les chaînes de caractères

### Objectif

Apprendre à manipuler du **texte (string)** : concaténation et *template literals*.

### Explication rapide

Concaténation classique :

```js
let message = "Bonjour " + prenom + " !";
console.log(message);
```

Avec un *template literal* (backticks ` `) :

```js
let message2 = `Bonjour ${prenom}, tu as ${age} ans.`;
console.log(message2);
```

### Exercices

1. Crée un message de bienvenue :

   ```js
   let messageBienvenue = "Bienvenue dans le cours de " + cours + " !";
   console.log(messageBienvenue);
   ```

2. Refais le même message avec un template literal :

   ```js
   let messageBienvenue2 = `Bienvenue dans le cours de ${cours} !`;
   console.log(messageBienvenue2);
   ```

3. Crée une phrase résumant ton profil :

   ```js
   let profil = `Je m'appelle ${prenom}, j'habite à ${ville} et j'ai ${age} ans.`;
   console.log(profil);
   ```

---

## 4. `alert` : afficher une fenêtre d’alerte

### Objectif

Découvrir `alert(...)` pour afficher un message dans une **popup**.

### Explication rapide

```js
alert("Attention : ceci est une alerte !");
```

### Exercices

1. Affiche une alerte simple :

   ```js
   alert("Bienvenue dans ce mini cours JavaScript !");
   ```

2. Utilise une variable dans ton alerte :

   ```js
   alert("Bonjour " + prenom + " !");
   ```

3. Utilise un template literal :

   ```js
   alert(`Bonjour ${prenom}, prêt pour JavaScript dans la console ?`);
   ```

> Remarque : `alert` bloque la page tant que tu n’as pas cliqué sur “OK”. C’est normal.

---

## 5. `confirm` : poser une question Oui / Non

### Objectif

Utiliser `confirm(...)` pour demander une réponse **booléenne** (true/false).

### Explication rapide

```js
let reponse = confirm("Voulez-vous continuer ?");
console.log("Réponse de l'utilisateur :", reponse);
```

### Exercices

1. Demande à l’utilisateur s’il aime JavaScript :

   ```js
   let aimeJS = confirm("Est-ce que tu aimes JavaScript ?");
   console.log("L'utilisateur aime JS :", aimeJS);
   ```

2. Crée un petit scénario :

   ```js
   let pret = confirm("Es-tu prêt à faire le prochain exercice ?");
   if (pret) {
     console.log("Super, on continue !");
   } else {
     console.log("D'accord, fais une pause et reviens plus tard.");
   }
   ```

3. Utilise `confirm` + `alert` :

   ```js
   let continuer = confirm("Veux-tu afficher un message secret ?");
   if (continuer) {
     alert("Voici le message secret : JavaScript n'est pas si compliqué 😉".replace("😉",""));
   } else {
     alert("Pas de message secret pour l'instant.");
   }
   ```

---

## 6. Mini-projet console : fiche utilisateur simple

### Objectif

Assembler `variables + console.log + alert + confirm` dans un mini scénario.

> On va tout taper **dans la console**, ligne par ligne.

1. Déclare quelques variables de base :

   ```js
   let nom = "Dupont";
   let prenomUser = "Alice";
   let ageUser = 25;
   ```

2. Affiche un résumé dans la console :

   ```js
   console.log(`Utilisateur : ${prenomUser} ${nom}, ${ageUser} ans.`);
   ```

3. Demande si l’utilisateur veut recevoir une alerte de bienvenue :

   ```js
   let veutAlerte = confirm("Voulez-vous afficher une alerte de bienvenue ?");
   ```

4. Si `veutAlerte` est vrai, affiche une alerte personnalisée :

   ```js
   if (veutAlerte) {
     alert(`Bienvenue ${prenomUser} ${nom} !`);
   } else {
     console.log("Pas d’alerte affichée.");
   }
   ```

5. Bonus : calcule l’âge dans 5 ans et l’affiche :

   ```js
   let ageDans5Ans = ageUser + 5;
   console.log(`${prenomUser} aura ${ageDans5Ans} ans dans 5 ans.`);
   ```

---

## 7. Idée de “devoir console” pour étudiants

Tu peux leur donner un petit énoncé du genre :

> **Travail Console 1 :**
>
> 1. Ouvrir la console JavaScript (F12 → Console).
> 2. Créer des variables `prenom`, `age`, `ville`, `cours`.
> 3. Afficher dans la console une phrase complète avec ces informations.
> 4. Utiliser `alert` pour afficher un message de bienvenue personnalisé.
> 5. Utiliser `confirm` pour demander à l’utilisateur s’il veut afficher un “résumé”.
> 6. Si oui, afficher le résumé dans la console avec `console.log`.

