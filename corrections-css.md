## A) Tailles de texte : unités à compléter

Actuellement :

* `font-size: 1.2rem;` → ✅ OK (rem)

À ajouter :

* au moins **une taille en `px`**
* au moins **une taille en `em`**

💡 *Chaque unité a un usage pédagogique différent.*

> *`px` = taille fixe, `em` = relative au parent, `rem` = relative au document.*

Exemple possible :
```
h1 {
font-size: 32px;
}

section {
font-size: 1.1em;
}
```

---

## B) Image de fond manquante

Aucune image de fond n’est appliquée à la page.

À ajouter par exemple sur `body` :
```
body {
background-image: url("../img/background.jpg");
background-size: cover;
background-repeat: no-repeat;
}
```
---

## C) Police personnalisée absente (`@font-face`)

Aucune police personnalisée n’est déclarée.

À corriger :

* ajouter un dossier `fonts/`
* déclarer la police avec `@font-face`
* l’utiliser dans `body`

💡 *Utiliser `@font-face` permet d’éviter la dépendance à Google Fonts en ligne.*

---

## D) Bordure et ombre manquantes

Aucun élément n’a :

* de `border`
* de `box-shadow`

Exemple simple :
```
section {
border: 1px solid #2c5f7c;
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
```

---

## E) Largeur maximale et centrage manquants

La page n’a **pas de largeur maximale**, elle s’étale sur tout l’écran.

À ajouter :
```
main {
max-width: 800px;
margin: 0 auto;
}
```

---

## F) Images – règle CSS correcte mais améliorable

CSS actuel :
```
img {
max-width: 100%;
width: auto;
}
```

✔️ Fonctionne
⚠️ `width: auto` est inutile ici

À simplifier :
```
img {
max-width: 100%;
height: auto;
}
```

💡 *`max-width: 100%` suffit à rendre une image responsive.*

---

## Corrections HTML nécessaires (impact CSS)

### 1️⃣ `width` et `height` dans le HTML

Actuellement :
```
<img src="./img/logo.png" width="300" height="200">
```

À corriger :

* retirer `width` et `height`
* gérer la taille **uniquement en CSS**

💡 *Le HTML décrit le contenu, le CSS gère l’apparence.*

---

### 2️⃣ Liens du menu non fonctionnels

Dans le menu :
```
<a href="#compétences">
```

Mais l’`id` réel est :
```
<section id="competences">
```

Idem pour `Parcours professionnel`

❌ Accent interdit dans les `id` + privilégiez les traits d'unions au lieu des espaces

À corriger :

* uniformiser sans accent et sans espaces
* corriger les liens

---

### 3️⃣ Listes HTML incorrectes

Exemple problématique :
```
<ul><p>...</p></ul>
```

À corriger :

* un `<ul>` ne contient que des `<li>`

---

### 4️⃣ Balise `<footer>` mal fermée

Actuellement :
```
</p
```
