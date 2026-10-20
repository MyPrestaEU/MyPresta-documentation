---
title: "Faire défiler vers le bas - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Faire défiler vers le bas par MyPresta.eu."
sidebar:
  label: "Faire défiler vers le bas - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Scroll to bottom sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-bottom.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/scroll-to-bottom/)
>
> ---


# Faire défiler vers le bas

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique pour le module « Faire défiler vers le bas ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Faire défiler vers le bas », puis en cliquant sur le bouton « Configurer ».

#### Paramètres et options

- **Couleur du bouton (st\_color)**

  - **Ce que fait ce paramètre :** Cela vous permet de définir la couleur du bouton « Faire défiler vers le bas ». Vous pouvez utiliser des noms de couleurs HTML standard (comme `red`, `blue`, `green`) ou des codes de couleurs hexadécimaux (comme `#FF0000` pour le rouge, `#0000FF` pour le bleu).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une couleur spécifique (par exemple, `#007bff`) :* Le bouton s'affichera dans cette couleur exacte sur votre front office.
    - *Lorsqu'il est laissé vide ou invalide :* Le bouton reviendra probablement à une couleur par défaut définie par le CSS du module, qui pourrait ne pas correspondre à votre marque.
  - **Valeur recommandée :** Choisissez une couleur qui complète le design de votre boutique et qui est clairement visible sur votre arrière-plan, mais pas trop distrayante. Utilisez la couleur principale ou secondaire de votre marque.
  - **Scénario / exemple pour le marchand :** Si votre marque utilise beaucoup de bleu foncé, le réglage de cette valeur sur `#000080` (bleu marine) permettrait au bouton de s'intégrer joliment tout en restant fonctionnel.
- **Position X du bouton (st\_x)**

  - **Ce que fait ce paramètre :** Cela contrôle la position horizontale du bouton sur l'écran. Il détermine la distance par rapport au bord droit de la fenêtre du navigateur où le bouton apparaîtra. La valeur est généralement en pixels.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une valeur inférieure (par exemple, `20`) :* Le bouton sera plus proche du bord droit de l'écran.
    - *Lorsqu'il est défini sur une valeur supérieure (par exemple, `80`) :* Le bouton sera plus éloigné du bord droit, se déplaçant vers le centre de l'écran.
  - **Valeur recommandée :** `20` ou `30` pixels est un placement courant et discret. Cela le maintient hors de la zone de contenu principale mais toujours facilement accessible.
  - **Scénario / exemple pour le marchand :** Si vous avez d'autres éléments fixes sur le côté droit de votre écran (comme un widget de chat), vous devrez peut-être augmenter cette valeur à `50px` pour éviter que le bouton « Faire défiler vers le bas » ne se chevauche.
- **Position Y du bouton (st\_y)**

  - **Ce que fait ce paramètre :** Cela contrôle la position verticale du bouton sur l'écran. Il détermine la distance par rapport au bord supérieur de la fenêtre du navigateur où le bouton apparaîtra. La valeur est généralement en pixels.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une valeur inférieure (par exemple, `20`) :* Le bouton sera plus proche du bord supérieur de l'écran.
    - *Lorsqu'il est défini sur une valeur supérieure (par exemple, `80`) :* Le bouton sera plus bas par rapport au bord supérieur.
  - **Valeur recommandée :** `20` ou `30` pixels est un bon point de départ. Cela le place dans le coin supérieur droit sans être trop haut ou trop bas.
  - **Scénario / exemple pour le marchand :** Si l'en-tête de votre boutique est très haut ou si vous avez un bouton « Faire défiler vers le haut » également dans le coin supérieur droit, vous pourriez ajuster cela à `60px` ou `70px` pour vous assurer que les deux boutons ont suffisamment d'espace et ne se chevauchent pas.
- **Opacité du bouton (st\_o)**

  - **Ce que fait ce paramètre :** Cela contrôle la transparence du bouton. Les valeurs d'opacité vont de `0` (complètement transparent/invisible) à `1` (complètement opaque/solide). Vous pouvez utiliser des valeurs décimales comme `0.5` pour 50 % de transparence.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur `1` :* Le bouton sera entièrement visible et solide.
    - *Lorsqu'il est défini sur `0.5` :* Le bouton sera semi-transparent, permettant au contenu d'arrière-plan de transparaître.
    - *Lorsqu'il est défini sur `0` :* Le bouton sera invisible (bien que toujours cliquable si vous savez où il se trouve).
  - **Valeur recommandée :** `0.8` ou `0.9` est souvent un bon équilibre. Cela rend le bouton légèrement moins intrusif tout en étant clairement visible. `1` est également parfaitement acceptable si vous voulez qu'il ressorte davantage.
  - **Scénario / exemple pour le marchand :** Si vous trouvez le bouton trop proéminent ou distrayant, réduire son opacité à `0.7` peut le faire s'intégrer plus subtilement dans le design de votre boutique sans perdre sa fonctionnalité.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Couleur du bouton (st\_color) | `#007bff` (exemple) | Définit la couleur du bouton. Affecte la visibilité et la cohérence de la marque. |
| Configuration du module | Position X du bouton (st\_x) | `20` | Distance horizontale par rapport au bord droit. Empêche le chevauchement avec d'autres éléments. |
| Configuration du module | Position Y du bouton (st\_y) | `20` | Distance verticale par rapport au bord supérieur. Positionne clairement le bouton. |
| Configuration du module | Opacité du bouton (st\_o) | `0.8` | Transparence du bouton. Contrôle son caractère intrusif ou subtil. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

-   **Q : Le bouton n'apparaît pas sur ma boutique.**
    -   **R :** Tout d'abord, assurez-vous que le module est installé et activé dans **Modules > Gestionnaire de modules**. Ensuite, vérifiez la page de configuration du module pour vous assurer que tous les paramètres sont enregistrés. S'il n'apparaît toujours pas, essayez de vider votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**). Parfois, les thèmes personnalisés peuvent également interférer ; passez temporairement au thème PrestaShop par défaut pour écarter cette possibilité.
-   **Q : Le bouton s'affiche, mais il est au mauvais endroit ou a l'air étrange.**
    -   **R :** Allez à la page de configuration du module. Ajustez les paramètres « Position X » et « Position Y » pour déplacer le bouton horizontalement et verticalement. Expérimentez avec différentes valeurs jusqu'à ce qu'il soit à un emplacement satisfaisant. Pour les problèmes d'apparence, vérifiez les paramètres « Couleur » et « Opacité ». S'il a toujours l'air bizarre, le CSS de votre thème pourrait être en train de remplacer les styles du module.
-   **Q : L'animation de défilement n'est pas fluide ou ne fonctionne pas.**
    -   **R :** Ce module utilise JavaScript pour l'effet de défilement fluide. Assurez-vous qu'il n'y a pas d'erreurs JavaScript sur votre site (vous pouvez vérifier la console de développement de votre navigateur pour les erreurs). Les conflits avec d'autres modules ou le JavaScript de thème personnalisé peuvent parfois empêcher l'animation de fonctionner correctement. Vider le cache est une bonne première étape.
-   **Q : Puis-je changer l'icône du bouton ?**
    -   **R :** La version actuelle du module n'offre pas de paramètre direct pour changer l'icône depuis le back office. Cela nécessiterait des modifications CSS ou de template personnalisées (voir le Guide du développeur pour plus de détails techniques).
-   **Q : Ce module affecte-t-il les performances ou le référencement de ma boutique ?**
    -   **R :** Ce module est très léger, ajoutant un minimum de CSS et de JavaScript. Il devrait avoir un impact négligeable sur la vitesse de chargement de votre boutique ou sur le référencement. La fonctionnalité est purement destinée à l'expérience utilisateur et ne modifie pas le contenu d'une manière qui affecterait l'indexation par les moteurs de recherche.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Faire défiler vers le bas » est une fonctionnalité front-office simple implémentée comme un module PrestaShop standard. Il utilise principalement le système de hooks de PrestaShop pour injecter son CSS, son JavaScript et la structure HTML du bouton dans le front office. La configuration est gérée via la méthode `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`. Il n'y a pas de contrôleurs personnalisés, d'ObjectModels ou d'interactions complexes avec la base de données.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. La fonctionnalité front-office du module est injectée directement via des hooks.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration est gérée dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. Le module ne définit aucune classe ou ObjetModèle personnalisé. Toute la logique est contenue dans `scrollbottom.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `scrollbottom/scrollbottom.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Ce script est responsable de la fonctionnalité principale du bouton « Faire défiler vers le bas ».
        -   Il écoute probablement la préparation du DOM.
        -   Il attache un écouteur d'événements de clic à l'élément du bouton « Faire défiler vers le bas ».
        -   Lorsqu'il est cliqué, il utilise la méthode `window.scrollTo()` ou `element.scrollIntoView()` de JavaScript, souvent avec `behavior: 'smooth'`, pour animer le défilement vers le bas de la page (spécifiquement, la hauteur de défilement maximale de l'élément `body` ou `html`).
        -   Il peut également gérer la visibilité du bouton, le faisant apparaître ou disparaître en fonction de la position de défilement de l'utilisateur (par exemple, ne s'afficher que lorsque l'utilisateur a fait défiler d'une certaine quantité).

### 4.5 Feuilles de style CSS (`views/css/`)

-   `scrollbottom/scrollbottom.css`
    -   **Portée :** Style client du front-office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style définit l'apparence visuelle et le positionnement du bouton « Faire défiler vers le bas ».
        -   Elle ciblera probablement un ID ou une classe spécifique pour le bouton (par exemple, `#scrollbottom_button`).
        -   Elle définit des propriétés telles que `position: fixed`, `right`, `top`, `z-index`, `background-color`, `color`, `padding`, `border-radius`, `cursor`, et potentiellement `display: none` initialement, avec JavaScript contrôlant sa visibilité.
        -   Elle peut également inclure des styles pour l'icône de flèche à l'intérieur du bouton (par exemple, en utilisant une icône de police ou une image d'arrière-plan).
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème :** Les développeurs peuvent inspecter le HTML généré pour trouver l'ID/la classe exacte du bouton (par exemple, `#scrollbottom_button`) et remplacer ses styles dans le fichier `custom.css` de leur thème ou un fichier équivalent pour obtenir un aspect personnalisé.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :

    -   `scrollbottom/adv.tpl` : Ce template est probablement utilisé pour afficher une publicité ou un contenu promotionnel lié à MyPresta.eu, souvent injecté dans un hook comme `displayAdminHome` ou similaire, mais non directement lié à la fonctionnalité du bouton front-office.
    -   `scrollbottom/footer.tpl` : C'est le template principal pour le bouton front-office.
        -   **Hooké dans :** `displayFooter` ou `footer` (selon la version de PrestaShop et le thème).
        -   **Sorties :** La structure HTML du bouton « Faire défiler vers le bas », y compris son ID/classe, l'icône de flèche, et potentiellement des styles en ligne ou des attributs de données dérivés des paramètres de configuration du module (couleur, position, opacité).
-   **Templates d'administration (`views/templates/admin/`)** : Aucun.
-   **Templates Front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   Les paramètres de configuration sont stockés dans la table `ps_configuration` en utilisant des clés comme `ST_COLOR`, `ST_X`, `ST_Y`, `ST_O`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` du front office. | Utilisé pour enregistrer et inclure les fichiers CSS (`scrollbottom.css`) et JavaScript (`scrollbottom.js`) du module, garantissant qu'ils sont chargés avant le contenu de la page. |
| `header` | Alias de `displayHeader` dans certains contextes. | Identique à `displayHeader`. |
| `displayFooter` | À la fin de la section `<body>`, avant la balise de fermeture `</body>`. | Utilisé pour rendre le template `footer.tpl`, qui contient la structure HTML du bouton « Faire défiler vers le bas ». |
| `footer` | Alias de `displayFooter` dans certains contextes. | Identique à `displayFooter`. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour accéder aux dernières versions du module « Faire défiler vers le bas », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
