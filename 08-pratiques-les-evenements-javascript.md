# Exercices addEventListener

> Pour chaque exercice :
>
> 1. Ouvrir **VS Code**
> 2. Créer un fichier **`index.html`**
> 3. **Copier-coller** le code de l’exercice
> 4. Ouvrir `index.html` dans le navigateur

---

## 1. Bouton « Changer la couleur du fond »

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Changer la couleur du fond</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding-top: 50px; }
    button { padding: 10px 20px; font-size: 16px; }
  </style>
</head>
<body>

  <h1>Changer la couleur du fond</h1>
  <button id="btnCouleur">Changer de couleur</button>
  <p>Couleur actuelle : <span id="couleurTexte">blanc</span></p>

  <script>
    const btn = document.getElementById('btnCouleur');
    const span = document.getElementById('couleurTexte');
    const couleurs = ['red', 'blue', 'green', 'purple', 'orange', 'pink', 'yellow'];

    btn.addEventListener('click', function () {
      const index = Math.floor(Math.random() * couleurs.length);
      const couleur = couleurs[index];
      document.body.style.backgroundColor = couleur;
      span.textContent = couleur;
    });
  </script>
</body>
</html>
```

---

## 2. Compteur de clics avec barre de progression

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Compteur de clics</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding-top: 40px; }
    #barreContainer {
      width: 300px; height: 25px; border: 1px solid #333;
      margin: 20px auto; background-color: #eee;
    }
    #barre {
      height: 100%; width: 0%; background-color: green;
      transition: width 0.2s;
    }
  </style>
</head>
<body>

  <h1>Compteur de clics</h1>
  <button id="btnClique">Cliquer ici</button>
  <p>Nombre de clics : <span id="compteur">0</span> / 20</p>

  <div id="barreContainer">
    <div id="barre"></div>
  </div>

  <p id="message"></p>

  <script>
    const btn = document.getElementById('btnClique');
    const compteurSpan = document.getElementById('compteur');
    const barre = document.getElementById('barre');
    const message = document.getElementById('message');

    let compteur = 0;
    const max = 20;

    btn.addEventListener('click', function () {
      if (compteur >= max) return;
      compteur++;
      compteurSpan.textContent = compteur;
      const pourcentage = (compteur / max) * 100;
      barre.style.width = pourcentage + '%';

      if (compteur === max) {
        message.textContent = 'Bravo, barre remplie !';
      }
    });
  </script>
</body>
</html>
```

---

## 3. Test de réaction (clic dès que le carré devient vert)

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Test de réaction</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding-top: 40px; }
    #zone {
      width: 200px; height: 200px; margin: 20px auto;
      background-color: red; cursor: pointer;
      display: flex; align-items: center; justify-content: center;
      color: white; font-size: 14px; user-select: none;
    }
  </style>
</head>
<body>

  <h1>Test de réaction</h1>
  <button id="btnStart">Lancer le test</button>
  <div id="zone">Attendez le vert</div>
  <p id="message"></p>

  <script>
    const btnStart = document.getElementById('btnStart');
    const zone = document.getElementById('zone');
    const message = document.getElementById('message');

    let pret = false;
    let timeoutId = null;
    let debut = 0;

    btnStart.addEventListener('click', function () {
      pret = false;
      message.textContent = '';
      zone.style.backgroundColor = 'red';
      zone.textContent = 'Attendez le vert';

      if (timeoutId) clearTimeout(timeoutId);

      const delai = 1000 + Math.random() * 3000;
      timeoutId = setTimeout(function () {
        pret = true;
        debut = Date.now();
        zone.style.backgroundColor = 'green';
        zone.textContent = 'Clique vite !';
      }, delai);
    });

    zone.addEventListener('click', function () {
      if (!pret) {
        message.textContent = 'Trop tôt ! Cliquez seulement quand c’est vert.';
      } else {
        const temps = Date.now() - debut;
        message.textContent = 'Réaction : ' + temps + ' ms';
        pret = false;
        zone.style.backgroundColor = 'red';
        zone.textContent = 'Attendez le vert';
      }
    });
  </script>
</body>
</html>
```

---

## 4. Déplacer un carré avec les flèches du clavier

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Déplacement au clavier</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; }
    #terrain {
      position: relative;
      margin: 30px auto;
      width: 500px;
      height: 300px;
      border: 2px solid #333;
      background-color: #f2f2f2;
    }
    #carre {
      position: absolute;
      width: 40px;
      height: 40px;
      background-color: blue;
      left: 10px;
      top: 10px;
    }
  </style>
</head>
<body>

  <h1>Déplacer le carré avec les flèches</h1>
  <p>Utilisez les touches ← ↑ → ↓ du clavier.</p>

  <div id="terrain">
    <div id="carre"></div>
  </div>

  <script>
    const terrain = document.getElementById('terrain');
    const carre = document.getElementById('carre');
    const pas = 10;

    document.addEventListener('keydown', function (e) {
      const rectTerrain = terrain.getBoundingClientRect();
      const rectCarre = carre.getBoundingClientRect();

      let left = carre.offsetLeft;
      let top = carre.offsetTop;

      if (e.key === 'ArrowLeft')  left -= pas;
      if (e.key === 'ArrowRight') left += pas;
      if (e.key === 'ArrowUp')    top -= pas;
      if (e.key === 'ArrowDown')  top += pas;

      if (left < 0) left = 0;
      if (top < 0) top = 0;
      if (left + rectCarre.width > rectTerrain.width) {
        left = rectTerrain.width - rectCarre.width;
      }
      if (top + rectCarre.height > rectTerrain.height) {
        top = rectTerrain.height - rectCarre.height;
      }

      carre.style.left = left + 'px';
      carre.style.top = top + 'px';
    });
  </script>
</body>
</html>
```

---

## 5. Mini “Paint” en grille de pixels

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Mini Paint en grille</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; }
    #palette { margin: 15px; }
    #grille {
      width: 400px;
      margin: 10px auto;
      display: grid;
      grid-template-columns: repeat(20, 1fr);
      border: 1px solid #ccc;
    }
    .pixel {
      width: 20px;
      height: 20px;
      border: 1px solid #eee;
      background-color: white;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>Mini Paint</h1>
  <div id="palette">
    Couleur : <input type="color" id="couleur" value="#ff0000">
  </div>
  <div id="grille"></div>

  <script>
    const grille = document.getElementById('grille');
    const couleur = document.getElementById('couleur');

    for (let i = 0; i < 400; i++) {
      const div = document.createElement('div');
      div.className = 'pixel';
      div.addEventListener('mousedown', function () {
        div.style.backgroundColor = couleur.value;
      });
      grille.appendChild(div);
    }
  </script>
</body>
</html>
```

---

## 6. Jeu « Devine le nombre » (1 à 100)

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Devine le nombre</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding-top: 40px; }
    input { padding: 5px; }
  </style>
</head>
<body>

  <h1>Devine le nombre (1 à 100)</h1>
  <p>Entrez un nombre :</p>
  <input type="number" id="proposition" min="1" max="100">
  <button id="btnTester">Tester</button>
  <p id="message"></p>
  <p>Essais : <span id="essais">0</span></p>

  <script>
    const secret = Math.floor(Math.random() * 100) + 1;
    const input = document.getElementById('proposition');
    const btn = document.getElementById('btnTester');
    const message = document.getElementById('message');
    const essaisSpan = document.getElementById('essais');

    let essais = 0;

    btn.addEventListener('click', function () {
      const valeur = Number(input.value);
      if (!valeur) return;

      essais++;
      essaisSpan.textContent = essais;

      if (valeur < secret) {
        message.textContent = 'Trop petit.';
      } else if (valeur > secret) {
        message.textContent = 'Trop grand.';
      } else {
        message.textContent = 'Bravo, trouvé en ' + essais + ' essais !';
      }
    });
  </script>
</body>
</html>
```

---

## 7. Effet “machine à écrire” sur un texte

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Effet Machine à écrire</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding-top: 40px; }
    #texte { font-size: 20px; margin-top: 20px; min-height: 30px; }
  </style>
</head>
<body>

  <h1>Effet Machine à écrire</h1>
  <button id="btnStart">Lancer</button>
  <div id="texte"></div>

  <script>
    const btn = document.getElementById('btnStart');
    const texteDiv = document.getElementById('texte');
    const phrase = 'Bienvenue dans le monde de JavaScript côté navigateur.';
    let index = 0;
    let intervalId = null;

    btn.addEventListener('click', function () {
      if (intervalId) clearInterval(intervalId);
      index = 0;
      texteDiv.textContent = '';
      intervalId = setInterval(function () {
        if (index < phrase.length) {
          texteDiv.textContent += phrase.charAt(index);
          index++;
        } else {
          clearInterval(intervalId);
        }
      }, 80);
    });
  </script>
</body>
</html>
```

---

## 8. Effet “Matrix” simple (pluie de caractères)

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Effet Matrix simple</title>
  <style>
    body {
      margin: 0;
      background-color: black;
      color: #00ff00;
      font-family: monospace;
      overflow: hidden;
    }
    #ecran {
      white-space: pre;
      padding: 10px;
      height: 100vh;
      box-sizing: border-box;
    }
  </style>
</head>
<body>

  <div id="ecran"></div>

  <script>
    const ecran = document.getElementById('ecran');
    const colonnes = 80;

    function ligneAleatoire() {
      let s = '';
      for (let i = 0; i < colonnes; i++) {
        const n = Math.floor(Math.random() * 2);
        s += n;
      }
      return s;
    }

    setInterval(function () {
      const ligne = ligneAleatoire();
      ecran.textContent = ligne + '\n' + ecran.textContent;
      const lignes = ecran.textContent.split('\n');
      if (lignes.length > 40) {
        ecran.textContent = lignes.slice(0, 40).join('\n');
      }
    }, 80);
  </script>
</body>
</html>
```

---

## 9. Balle qui rebondit dans un rectangle

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Balle qui rebondit</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; }
    #terrain {
      position: relative;
      margin: 30px auto;
      width: 500px;
      height: 300px;
      border: 2px solid #333;
      background-color: #fafafa;
      overflow: hidden;
    }
    #balle {
      position: absolute;
      width: 30px;
      height: 30px;
      border-radius: 50%;
      background-color: red;
      left: 10px;
      top: 10px;
    }
  </style>
</head>
<body>

  <h1>Balle qui rebondit</h1>
  <div id="terrain">
    <div id="balle"></div>
  </div>

  <script>
    const terrain = document.getElementById('terrain');
    const balle = document.getElementById('balle');

    let x = 10;
    let y = 10;
    let vx = 3;
    let vy = 2;

    function anime() {
      const largeur = terrain.clientWidth;
      const hauteur = terrain.clientHeight;
      const taille = balle.clientWidth;

      x += vx;
      y += vy;

      if (x <= 0 || x + taille >= largeur) vx = -vx;
      if (y <= 0 || y + taille >= hauteur) vy = -vy;

      balle.style.left = x + 'px';
      balle.style.top = y + 'px';

      requestAnimationFrame(anime);
    }

    anime();
  </script>
</body>
</html>
```

---

## 10. Effet “lampe de poche” qui suit la souris

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Effet Lampe de poche</title>
  <style>
    html, body {
      margin: 0;
      height: 100%;
      background-color: black;
      overflow: hidden;
    }
    #scene {
      position: relative;
      width: 100%;
      height: 100%;
      background-image: url('https://picsum.photos/800/600?blur=2');
      background-size: cover;
      filter: brightness(0.2);
    }
    #lampe {
      position: absolute;
      width: 200px;
      height: 200px;
      border-radius: 50%;
      pointer-events: none;
      box-shadow: 0 0 0 9999px rgba(0,0,0,0.8);
      mix-blend-mode: normal;
    }
  </style>
</head>
<body>

  <div id="scene">
    <div id="lampe"></div>
  </div>

  <script>
    const scene = document.getElementById('scene');
    const lampe = document.getElementById('lampe');

    scene.addEventListener('mousemove', function (e) {
      const rect = scene.getBoundingClientRect();
      const x = e.clientX - rect.left - lampe.offsetWidth / 2;
      const y = e.clientY - rect.top - lampe.offsetHeight / 2;
      lampe.style.left = x + 'px';
      lampe.style.top = y + 'px';
    });
  </script>
</body>
</html>
```

