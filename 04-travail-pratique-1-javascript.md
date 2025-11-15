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



## 7. Devoir
Tu peux leur donner un petit énoncé du genre :

> **Travail Console 1 :**
>
> 1. Ouvrir la console JavaScript (F12 → Console).
> 2. Créer des variables `prenom`, `age`, `ville`, `cours`.
> 3. Afficher dans la console une phrase complète avec ces informations.
> 4. Utiliser `alert` pour afficher un message de bienvenue personnalisé.
> 5. Utiliser `confirm` pour demander à l’utilisateur s’il veut afficher un “résumé”.
> 6. Si oui, afficher le résumé dans la console avec `console.log`.




## 8 . Correction


Je suppose que vous avez choisi :

```js
let prenom = "Alice";
let age = 25;
let ville = "Montréal";
let cours = "JavaScript";
```

Tu pourras adapter les valeurs au besoin.



## Travail Console 1 — Sorties attendues (exemple de correction)

> **8.1. Ouvrir la console JavaScript (F12 → Console).**

Aucune sortie attendue, c’est juste de la mise en place.

---

> **8.2. Créer des variables `prenom`, `age`, `ville`, `cours`.**

Code typique dans la console :

```js
let prenom = "Alice";
let age = 25;
let ville = "Montréal";
let cours = "JavaScript";
```

**Sortie attendue :**

Dans la console, **aucune sortie particulière** (juste l’écho de la ligne ou `undefined` selon le navigateur).
Le plus important : les variables existent sans erreur.

---

> **8.3. Afficher dans la console une phrase complète avec ces informations.**

Exemple de code :

```js
console.log(
  "Je m'appelle " + prenom + ", j'ai " + age + " ans, j'habite à " + ville + " et je suis le cours " + cours + "."
);
```

**Sortie attendue dans la console :**

```text
Je m'appelle Alice, j'ai 25 ans, j'habite à Montréal et je suis le cours JavaScript.
```

(Le texte exact dépend des valeurs choisies par l’étudiant, mais la structure doit être similaire.)

---

> **8.4. Utiliser `alert` pour afficher un message de bienvenue personnalisé.**

Exemple de code :

```js
alert("Bienvenue " + prenom + " dans le cours " + cours + " !");
```

**Sortie attendue :**

Une **fenêtre popup** apparaît avec :

```text
Bienvenue Alice dans le cours JavaScript !
```

L’étudiant doit cliquer sur **OK** pour continuer.

---

> **8.5. Utiliser `confirm` pour demander à l’utilisateur s’il veut afficher un “résumé”.**

Exemple de code :

```js
let afficherResume = confirm("Veux-tu afficher un résumé de ton profil ?");
```

**Sortie attendue :**

1. Une fenêtre de confirmation apparaît avec le texte :

   ```text
   Veux-tu afficher un résumé de ton profil ?
   ```

   et deux boutons : **OK** / **Annuler**.

2. Selon le choix :

   * Si l’utilisateur clique sur **OK** → la variable `afficherResume` vaut `true`.
   * Si l’utilisateur clique sur **Annuler** → la variable `afficherResume` vaut `false`.

Dans la console, si l’apprenant tape ensuite simplement :

```js
afficherResume
```

il verra :

```text
true
```

ou

```text
false
```



> **8.6. Si oui, afficher le résumé dans la console avec `console.log`.**

Exemple de code :

```js
if (afficherResume) {
  console.log(
    "Résumé : " +
    prenom + " a " + age + " ans, habite à " + ville +
    " et suit le cours " + cours + "."
  );
}
```

**Sortie attendue si l’utilisateur a cliqué sur OK (true) :**

```text
Résumé : Alice a 25 ans, habite à Montréal et suit le cours JavaScript.
```

**Sortie attendue si l’utilisateur a cliqué sur Annuler (false) :**

Aucune nouvelle ligne `console.log` ne s’affiche.
(Le bloc `if` ne s’exécute pas.)



<br/>

# Annexe 1




## 1. Titre “HACKED” stylé dans la console

<details>

<summary> 1. Titre “HACKED” stylé dans la console </summary>

À taper tel quel dans la console :

```js
console.log(
  "%c  H A C K E D  ",
  "color: #00ff00; background: #000; font-size: 40px; font-weight: bold; text-shadow: 0 0 10px #00ff00; padding: 10px;"
);
```

**Effet attendu :**
Un énorme “HACKED” vert fluo s’affiche dans la console, sur fond noir, comme dans un film.


</details>


<details>

<summary>  2. Pluie de codes verts (style Matrix) dans la console </summary>


## 2. Pluie de codes verts (style Matrix) dans la console

```js
let matrixId = setInterval(() => {
  const line = Math.random().toString(16).substring(2, 18).toUpperCase();
  console.log("%c" + line, "color:#00ff00; font-family: monospace;");
}, 100);
```

Pour **arrêter** la pluie :

```js
clearInterval(matrixId);
```

**Effet attendu :**
La console se remplit de lignes comme :

```text
3AF9C2D87B193F0A
7E21B9D3A4F6C0B1
...
```

en vert, qui défilent rapidement → **gros effet “terminal de hacker”**.


</details>

<details>
<summary>  2. Pluie de codes verts (style Matrix) dans la console </summary>


## 3. “Hack visuel” de la page (fond noir + texte vert)

À taper dans la console :

```js
document.body.style.backgroundColor = "black";
document.body.style.color = "#00ff00";
document.body.style.fontFamily = "monospace";
```

**Effet attendu :**
Toute la page web devient :

* fond noir
* texte vert
* police monospace

→ ça donne l’impression que le site a été transformé en vieux terminal.

Pour **revenir à peu près normal** (simple reset grossier) :

```js
document.body.style = "";
```

</details>

<details>
<summary>  2. Pluie de codes verts (style Matrix) dans la console </summary>

## 4. Message “scan” avec animation simple

```js
let step = 0;
let scanId = setInterval(() => {
  step++;
  console.log("Scanning system" + ".".repeat(step % 4));
  if (step > 20) {
    clearInterval(scanId);
    console.log("%cScan terminé : aucune menace détectée.", "color:#00ff00; font-weight:bold;");
  }
}, 150);
```

**Effet attendu :**

Dans la console, tu vois :

```text
Scanning system.
Scanning system..
Scanning system...
Scanning system.
...
Scan terminé : aucune menace détectée.
```

→ petit côté “outil de scan de film de hackers”, mais c’est juste du texte.


</details>

<details>
<summary>  2. Pluie de codes verts (style Matrix) dans la console </summary>


## 5. Dessin ASCII simple (pyramide)

```js
let hauteur = 8;
for (let i = 1; i <= hauteur; i++) {
  let espaces = " ".repeat(hauteur - i);
  let etoiles = "*".repeat(2 * i - 1);
  console.log(espaces + etoiles + espaces);
}
```

**Effet attendu :**
Une pyramide de `*` s’affiche dans la console :

```text
       *
      ***
     *****
    *******
   *********
  ***********
 *************
***************
```

Tu peux dire aux étudiants : *“Vous venez de faire un dessin en ASCII avec une boucle for.”*

</details>

<details>
<summary>  2. Pluie de codes verts (style Matrix) dans la console </summary>

## 6. Popup façon “terminal secret” (alerte + console)

```js
alert("Accès au terminal sécurisé accordé (simulation). Ouvrez la console F12.");
console.log("%cBienvenue dans le terminal secret (faux).", "color:#0f0; font-weight:bold;");
```

**Effet attendu :**

* Une popup s’ouvre avec un message “sérieux”
* Puis la console montre un message en vert.


</details>


<br/>

# Annexe 2



## 1. Vraie animation “Matrix” en plein écran (canvas)

**Effet :** pluie de caractères verts qui tombent sur toute la page.
**Utilisation :** copie-colle TOUT dans la console, Entrée.

```js
(function () {
  // Création du canvas plein écran
  const canvas = document.createElement("canvas");
  const ctx = canvas.getContext("2d");
  canvas.id = "matrix-hack-canvas";
  canvas.style.position = "fixed";
  canvas.style.top = 0;
  canvas.style.left = 0;
  canvas.style.width = "100%";
  canvas.style.height = "100%";
  canvas.style.zIndex = 999999;
  canvas.style.pointerEvents = "none"; // ne bloque pas les clics
  document.body.appendChild(canvas);

  // Ajuste la taille au viewport
  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  resize();
  window.addEventListener("resize", resize);

  const letters = "01ZXCVBNMASDFGHJKLQWERTYUIOP";
  const fontSize = 16;
  const columns = Math.floor(canvas.width / fontSize);
  const drops = Array.from({ length: columns }, () => Math.floor(Math.random() * canvas.height));

  function draw() {
    // fond noir transparent pour effet de trainée
    ctx.fillStyle = "rgba(0, 0, 0, 0.1)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = "#0F0";
    ctx.font = fontSize + "px monospace";

    for (let i = 0; i < drops.length; i++) {
      const text = letters.charAt(Math.floor(Math.random() * letters.length));
      const x = i * fontSize;
      const y = drops[i] * fontSize;
      ctx.fillText(text, x, y);

      if (y > canvas.height && Math.random() > 0.975) {
        drops[i] = 0;
      } else {
        drops[i]++;
      }
    }

    requestAnimationFrame(draw);
  }

  draw();
})();
```

👉 **Pour arrêter / enlever l’effet :**

```js
const c = document.getElementById("matrix-hack-canvas");
if (c) c.remove();
```

---

## 2. Écran d’alerte rouge “SYSTEM BREACH” (overlay animé)

**Effet :** gros écran rouge semi-transparent, texte qui flash au milieu.
**Utilisation :** colle dans la console.

```js
(function () {
  if (document.getElementById("breach-overlay")) return;

  const overlay = document.createElement("div");
  overlay.id = "breach-overlay";
  overlay.style.position = "fixed";
  overlay.style.top = 0;
  overlay.style.left = 0;
  overlay.style.width = "100%";
  overlay.style.height = "100%";
  overlay.style.background = "rgba(150, 0, 0, 0.7)";
  overlay.style.zIndex = 999998;
  overlay.style.display = "flex";
  overlay.style.alignItems = "center";
  overlay.style.justifyContent = "center";
  overlay.style.pointerEvents = "none";

  const text = document.createElement("div");
  text.textContent = "SYSTEM BREACH";
  text.style.color = "#fff";
  text.style.fontFamily = "Impact, system-ui, sans-serif";
  text.style.fontSize = "6vw";
  text.style.letterSpacing = "0.4em";
  text.style.textShadow = "0 0 20px #ff0000, 0 0 40px #ff0000";
  text.style.textAlign = "center";

  overlay.appendChild(text);
  document.body.appendChild(overlay);

  let visible = true;
  const intervalId = setInterval(() => {
    visible = !visible;
    text.style.opacity = visible ? "1" : "0.2";
  }, 200);

  // on garde l'id pour pouvoir arrêter
  window.__breachOverlayInterval = intervalId;
})();
```

👉 **Pour l’enlever :**

```js
clearInterval(window.__breachOverlayInterval);
const ov = document.getElementById("breach-overlay");
if (ov) ov.remove();
```

---

## 3. Faux “scan de système” + barre de progression dans la console

**Effet :** progression avec barres `##########` + messages qui montent à 100 %.

```js
(function () {
  let step = 0;
  const total = 30;

  const intervalId = setInterval(() => {
    step++;
    const percent = Math.floor((step / total) * 100);
    const barLength = 20;
    const filled = Math.floor((percent / 100) * barLength);
    const empty = barLength - filled;
    const bar = "[" + "#".repeat(filled) + " ".repeat(empty) + "]";

    console.clear();
    console.log("%cInitialisation du scan…", "color:#0f0; font-weight:bold;");
    console.log(bar + " " + percent + "%");
    console.log("Analyse des ports...");
    console.log("Analyse des processus...");
    console.log("Analyse de la mémoire...");

    if (step >= total) {
      clearInterval(intervalId);
      console.log("%cScan terminé : 0 menaces détectées.", "color:#0f0; font-weight:bold;");
    }
  }, 150);
})();
```

👉 **Effet attendu :**
La console “bouge” en continu, barre qui se remplit, très *terminal admin sécurité*.

---

## 4. Animation de texte qui “se décrypte” (titre de la page)

**Effet :** le texte d’un titre (H1) passe par des caractères aléatoires qui se stabilisent sur le vrai texte (effet “décryptage”).

```js
(function () {
  const h1 = document.querySelector("h1") || document.body;
  const finalText = h1.textContent || "ACCESS GRANTED";
  const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789#@$%&";

  let frame = 0;
  const maxFrames = finalText.length * 6;

  const intervalId = setInterval(() => {
    frame++;
    let out = "";
    for (let i = 0; i < finalText.length; i++) {
      if (i * 6 < frame) {
        out += finalText[i];
      } else {
        out += letters[Math.floor(Math.random() * letters.length)];
      }
    }
    h1.textContent = out;

    if (frame > maxFrames) {
      clearInterval(intervalId);
      h1.textContent = finalText;
    }
  }, 50);
})();
```

👉 **Effet attendu :**
Le titre se met à “glitcher”, puis lettre par lettre il revient à la phrase originale.

---

## 5. Vibration / tremblement de l’écran (screen shake)

**Effet :** tout le contenu de la page tremble comme un impact.

```js
(function () {
  const body = document.body;
  if (body.classList.contains("shake-active")) return;

  const originalTransition = body.style.transition;
  const originalTransform = body.style.transform;

  body.classList.add("shake-active");
  body.style.transition = "transform 0.05s";

  let count = 0;
  const max = 40;

  const intervalId = setInterval(() => {
    const x = (Math.random() - 0.5) * 20;
    const y = (Math.random() - 0.5) * 20;
    body.style.transform = `translate(${x}px, ${y}px)`;
    count++;
    if (count > max) {
      clearInterval(intervalId);
      body.style.transform = originalTransform;
      body.style.transition = originalTransition;
      body.classList.remove("shake-active");
    }
  }, 50);
})();
```

👉 **Effet attendu :**
La page bouge dans tous les sens pendant 2–3 secondes, puis se stabilise.

---

## 6. Combo “animation terminal” dans la console (spinner + log)

**Effet :** un petit spinner tourne dans la console, comme une vraie commande qui tourne.

```js
(function () {
  const frames = ["|", "/", "-", "\\"];
  let i = 0;
  let ticks = 0;
  const maxTicks = 60;

  const id = setInterval(() => {
    const frame = frames[i % frames.length];
    i++;
    ticks++;
    console.clear();
    console.log("%cExécution du script de maintenance...", "color:#0f0;");
    console.log("[" + frame + "] Traitement en cours...");
    if (ticks >= maxTicks) {
      clearInterval(id);
      console.clear();
      console.log("%cMaintenance terminée avec succès.", "color:#0f0; font-weight:bold;");
    }
  }, 100);

  window.__spinnerId = id;
})();
```

👉 **Pour stopper manuellement :**

```js
clearInterval(window.__spinnerId);
```





