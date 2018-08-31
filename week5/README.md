# Semaine 5 - Javascript

[Instructions pour les professeurs](./teachers.md)

# Préparation

- Si vous avez réussi la trame principale la semaine dernière, ouvrir le fichier `index.html` dans le dossier utilisé la dernière fois
- Sinon, ouvrir le fichier `index.html` dans le dossier `week5`

* Dans la barre de tâches utilisez `Fichier > Ouvrir un dossier`
* Rechercher le dossier que vous venez de créer et cliquer sur le dossier ci-dessus puis cliquer sur `Ouvrir`

# Smooth scrolling

- Avant la balise de fermeture `body`, créer une balise `script`
  - Avec l'attribut `src` pour valeur le chemin relatif du fichier `smooth-scroll.min.js` dans le dossier `js`
- A la suite, créer une autre balise `script`
  - A l'intérieur, écrire le code suivant que l'on peut trouver sur la [documentation](https://github.com/cferdinandi/smooth-scroll#3-initialize-smooth-scroll) de la librairie Javascript

```js
const scroll = new SmoothScroll('a[href*="#"]');
```

## A savoir

- Il faut toujours regarder la documentation et utiliser le code de la documentation tel quel avant de faire des ajustement si nécessaire

## Vérification

Avant de passer à l'étape suivante, cliquer sur les menus de la navigation pour voir si le passage d'un lien à un autre est animé.

# Galerie d'images

Aller sur la [documentation](http://idangero.us/swiper/api/)

Dans le fichier `index.html` dans la section galerie

- Englober les 3 images avec une `div` de classe `swiper-container`
  - A l'intérieur, rajouter une autre `div` de classe `swiper-wrapper` qui englobe les 3 images
- Englober chaque image avec une balise `div` de classe `swiper-slide`
- Dans la `div.swiper-container` mais en dehors de la `div.swiper-wrapper` ajouter la `div.swiper-pagination`

Dans la dernière balise `script` créée

- Ajouter ce code à la suite du premier

```html
<script>
    const scroll = new SmoothScroll('a[href*="#"]');

    const mySwiper = new Swiper('.swiper-container', {
            speed: 400,
            pagination: {
                el: '.swiper-pagination',
                type: 'bullets',
                clickable: true
            }
        });
</script>
```

## Vérification

Pour passer à l'étape suivante, regarder s'il y a des ronds bleus cliquables pour naviguer à travers les images

# Faire un fichier Javascript indépendant

- Créer un fichier `scripts.js` dans le dossier `js`
- Couper/coller le contenu de la balise `script` de la page HTML dans le fichier `scripts.js`
- Ajouter l'attribut `src` avec le chemin de ce nouveau fichier dans la balise `script` qui est maintenant vide

## A savoir

- Il est commun de mettre le code dans un fichier différent quand le code Javascript sera utilisé dans plusieurs pages.

## Vérification

Pour passer à l'étape suivante, regarder si tout fonctionne comme avant

# Premier pas du développeur/programmeur

Le formateur va faire un mini session de live coding pour vous montrer les bases pour créer votre propre interaction en Javascript qui ne peut être reproduit avec un plugin.

Voici le code que vous allez reproduire ensemble

```html
<script src="./js/jquery-3.3.1.min.js"></script>
<script>
    jQuery(() => {
            jQuery('select').on('change', (e) => {
                const value = e.target.value;
                const subscribeBtn = $('form button');

                if (value !== '') {
                    subscribeBtn.attr('disabled', false);
                } else {
                    subscribeBtn.attr('disabled', true);
                }
            })
        });
</script>
```

# Bonus

## Bonus #1 : Modal

Aller sur la [documentation](https://getbootstrap.com/docs/4.1/components/modal/#live-demo) de Bootstrap

- Créer un bouton login dans la barre de navigation si ce n'est pas déjà fait.
- Rendre ce bouton cliquable pour faire apparaître une modal