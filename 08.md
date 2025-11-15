## Travail Console 2 — Conditions `if / else` (avec sorties attendues)

> **Travail Console 2 : Conditions if / else**
>
> 1. Créer une variable `age` et tester si la personne est majeure ou mineure avec `if / else`.
> 2. Modifier la valeur de `age` et observer le changement de résultat.
> 3. Créer une variable `note` (0 à 100) et utiliser `if / else if / else` pour afficher une mention.
> 4. Créer une variable `heure` (0 à 23) et afficher un message différent selon la plage horaire (matin, après-midi, soir).

---

### 1. Variable `age` — majeur ou mineur

**Code à taper dans la console :**

```js
let age = 16;

if (age >= 18) {
  console.log("La personne est majeure.");
} else {
  console.log("La personne est mineure.");
}
```

**Sortie attendue dans la console :**

```text
La personne est mineure.
```

> Normal : `age` vaut `16`, donc la condition `age >= 18` est fausse → le bloc `else` s’exécute.

---

### 2. Modifier `age` et observer le changement

On **réutilise** la même structure, mais on change la valeur de `age`.

**Code :**

```js
age = 21;  // on ne remet pas "let", on modifie juste la variable existante

if (age >= 18) {
  console.log("La personne est majeure.");
} else {
  console.log("La personne est mineure.");
}
```

**Sortie attendue dans la console :**

```text
La personne est majeure.
```

> Cette fois, `age` vaut `21`, donc la condition `age >= 18` est vraie → le bloc `if` s’exécute.

---

### 3. Variable `note` — mention avec `if / else if / else`

On veut afficher une **mention** en fonction d’une note sur 100.

**Code (exemple avec une note de 72) :**

```js
let note = 72;

if (note >= 90) {
  console.log("Mention : A (Excellent)");
} else if (note >= 80) {
  console.log("Mention : B (Très bien)");
} else if (note >= 70) {
  console.log("Mention : C (Bien)");
} else if (note >= 60) {
  console.log("Mention : D (Passable)");
} else {
  console.log("Mention : E (Échec)");
}
```

**Sortie attendue dans la console (avec `note = 72`) :**

```text
Mention : C (Bien)
```

> La première condition `note >= 90` est fausse, `note >= 80` fausse aussi,
> `note >= 70` est vraie → on exécute le bloc correspondant et on **ignore** les suivants.

---

#### Variante pour tester d’autres cas

Tu peux demander aux étudiants de changer la valeur de `note` :

* `note = 95` → sortie attendue :

  ```text
  Mention : A (Excellent)
  ```

* `note = 83` → sortie attendue :

  ```text
  Mention : B (Très bien)
  ```

* `note = 58` → sortie attendue :

  ```text
  Mention : E (Échec)
  ```

---

### 4. Variable `heure` — message selon la plage horaire

On simule une heure sur 24h (0–23) et on affiche un message différent.

**Code (exemple avec `heure = 9`) :**

```js
let heure = 9;

if (heure >= 6 && heure < 12) {
  console.log("Bonjour, c'est le matin.");
} else if (heure >= 12 && heure < 18) {
  console.log("Bon après-midi.");
} else if (heure >= 18 && heure < 22) {
  console.log("Bonsoir.");
} else {
  console.log("Il est tard, pensez à vous reposer.");
}
```

**Sortie attendue (avec `heure = 9`) :**

```text
Bonjour, c'est le matin.
```

---

#### Autres valeurs à tester

* `heure = 14;` puis relancer le `if / else if / else` :

  **Sortie attendue :**

  ```text
  Bon après-midi.
  ```

* `heure = 20;` :

  **Sortie attendue :**

  ```text
  Bonsoir.
  ```

* `heure = 2;` :

  **Sortie attendue :**

  ```text
  Il est tard, pensez à vous reposer.
  ```
