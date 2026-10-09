  # Documentation des acquis — Migration du site Élan Fitness

**Auteur :** Ilyass
**Projet :** migration du site Élan Fitness d'un one pager vers un site multipage
**Période :** du 06/10/2026 au 09/10/2026
**Dépôt GitHub :** `[https://github.com/rostomilyass/projet-fitness2.0]`
**Site en ligne (GitHub Pages) :** `[https://rostomilyass.github.io/projet-fitness2.0/]`

---

## 1. Présentation du projet

Élan Fitness est une salle de sport à Casablanca. Le site existait sous la forme d'une seule page (one pager). L'objectif du brief était de le transformer en un site de 4 pages reliées entre elles, pour améliorer la présence de la salle sur le web.

## 2. Organisation des fichiers

**Choix :** une seule feuille `style.css` pour toutes les pages garantit la cohérence visuelle et évite de répéter le code. L'en-tête, le menu et le pied de page sont identiques sur chaque page ; seule la classe `lien-actif` change pour indiquer la page en cours.

## 3. Acquis en HTML5

- **Structure sémantique :** `header`, `nav`, `main`, `section`, `article`, `footer` à la place de `div` partout. Cela aide les lecteurs d'écran et les moteurs de recherche à comprendre la page.
- **Navigation accessible :** `<nav aria-label="Navigation principale">` et un second `nav` pour le pied de page, avec un `aria-label` différent.
- **Images :** attribut `alt` descriptif sur les photos, `alt=""` sur les images purement décoratives (icônes, logo à côté du texte).
- **Formulaire :** `<label for="...">` relié à l'`id` de chaque champ, types de champs adaptés (`type="email"`, `type="tel"`), `placeholder` pour guider la saisie.
- **Hiérarchie des titres :** un seul `h1` par page, puis `h2`, `h3`, `h4` sans saut de niveau.
- **Langue :** `<html lang="fr">`.

## 4. Acquis en CSS3

- **Reset de base :** `* { box-sizing: border-box; margin: 0; padding: 0; }` pour que la largeur d'un élément inclue son padding et sa bordure.
- **En-tête collant :** `position: sticky; top: 0;` garde le menu visible pendant le défilement.
- **Pseudo-éléments :** le point orange du logo est créé en CSS avec `.logo::after` sans ajouter de balise HTML.
- **Badge « Populaire » :** `position: relative` sur la carte et `position: absolute` sur le badge pour le placer sur le bord haut.
- **Images :** `object-fit: cover` pour que les photos remplissent leur cadre sans se déformer.
- **Icônes de liste :** `background-image` sur les `li` des formules pour afficher une coche sans balise supplémentaire.
- **Interactions :** états `:hover` sur les boutons et les liens du menu, `:focus-visible` pour la navigation au clavier.
- **Transition (bonus) :** `transition: transform .2s, box-shadow .2s` sur les cartes et les boutons, avec un léger `translateY(-3px)` au survol.
- **Organisation :** classes en français, nommées par rôle (`.carte`, `.bouton-principal`, `.formule-populaire`), et styles regroupés par composant dans `style.css`.

## 5. UX / UI

- **Cohérence :** mêmes couleurs, mêmes polices, mêmes boutons et même structure sur les 4 pages.
- **Navigation simple :** le menu est présent sur toutes les pages et la page en cours est mise en évidence (couleur orange et soulignement).
- **Boutons clairs :** deux niveaux, `.bouton-principal` (orange plein) pour l'action principale et `.bouton-secondaire` (contour) pour l'action secondaire.
- **Lisibilité :** bon contraste du texte principal, interlignes confortables (`line-height` de 1,5 à 1,7), largeur de texte limitée pour ne pas fatiguer la lecture.
- **Parcours visiteur :** Accueil, puis Programmes, puis Contact : chaque page a un bouton qui pousse vers l'étape suivante.

## 6. SEO (référencement)

Améliorations appliquées :

1. **`title` et `meta description` uniques par page**, avec le mot-clé « salle de sport à Casablanca » et le nom de la page.
2. **Un seul `h1` par page**, avec des titres hiérarchisés ensuite.
3. **Balises sémantiques et attributs `alt`** descriptifs sur toutes les images de contenu.
4. **`<html lang="fr">`** pour indiquer la langue aux moteurs de recherche.
5. **Liens internes explicites :** textes de liens clairs (« Voir les programmes », « Cours d'essai gratuit »).

## 7. Validation W3C

- Validateur HTML : https://validator.w3.org/
- Validateur CSS : https://jigsaw.w3.org/css-validator/

## 8. Git et déploiement

**Commandes utilisées :**

```bash
git init
git add .
git commit -m "Ajout de la page Accueil"
git branch -M main
git remote add origin <url-du-depot>
git push -u origin main
```

**Bonnes pratiques appliquées :** commits fréquents avec des messages clairs (une fonctionnalité par commit, par exemple « Ajout de la page Programmes »).

**Déploiement sur GitHub Pages :**
1. Dépôt GitHub, onglet **Settings**, menu **Pages**.
2. Source : branche `main`, dossier `/ (root)`.
3. Après quelques minutes, le site est disponible à l'adresse `https://rostomilyass.github.io/projet-fitness2.0/`.
4. Vérification dans une fenêtre de navigation privée.

## 9. Difficultés rencontrées et solutions

Un text-align: center écrit pour la page contact (.contacternous-contenu h2, p) centrait tous les paragraphes du site, car le p seul n'était pas limité à cette page. J'ai corrigé le problème en limitant chaque sélecteur : .contacternous-contenu h2, .contacternous-contenu p.

Après le passage en multipage, certains liens pointaient vers contact.html et #contact, qui n'existaient plus. Je les ai remplacés par contacternous.html.

Le formulaire de contact était difficile à maintenir à cause des styles inline et des marges fixes. J'ai créé des classes CSS dédiées et une mise en page flexbox en deux colonnes.

Le contraste de l'orange sur fond blanc était insuffisant. J'ai utilisé un orange plus foncé pour le petit texte et les boutons.

La mise en page se cassait sur petit écran. J'ai ajouté des media queries et fait passer les blocs en colonne.

## 10. Compétences acquises

- Découper un one pager en plusieurs pages et concevoir une arborescence.
- Écrire du HTML5 sémantique et accessible.
- Appliquer des bonnes pratiques SEO de base.
- Valider son code avec les outils du W3C.
- Utiliser Git et GitHub, et publier un site avec GitHub Pages.

