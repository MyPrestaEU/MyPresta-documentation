---
title: "Prestashop Slider - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Prestashop Slider par MyPresta.eu."
sidebar:
  label: "Prestashop Slider - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Prestashop Slider sur MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/prestashop-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/sliders-slideshows/prestashop-slider/)
>
> ---


# Prestashop Slider

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et préinstallées sur la plupart des environnements d'hébergement web.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est le panneau de contrôle principal de votre Prestashop Slider. Ici, vous définirez l'apparence, la convivialité et le contenu de vos sliders.

#### **Paramètres généraux**

- **Ce que fait ce paramètre :** Ces paramètres contrôlent le comportement général et l'apparence de votre slider.
- **Effet de la modification de ce paramètre :**
  - *Largeur du slider :* Définit la largeur du slider. Peut être une valeur fixe en pixels ou un pourcentage pour la réactivité.
  - *Hauteur du slider :* Définit la hauteur du slider.
  - *Type d'animation :* Sélectionne l'un des 40 effets de transition disponibles entre les diapositives.
  - *Vitesse d'animation :* Contrôle la rapidité de la transition entre les diapositives.
  - *Intervalle de diapositive :* Définit la durée d'affichage de chaque diapositive avant de passer automatiquement à la suivante.
  - *Flèches de navigation :* Active/désactive les flèches gauche/droite pour la navigation manuelle des diapositives.
  - *Points/Puces de navigation :* Active/désactive les petits points généralement situés en bas du slider pour la sélection directe des diapositives.
  - *Miniatures :* Active/désactive les petites images d'aperçu de chaque diapositive, souvent affichées sous le slider principal.
  - *Aperçu des miniatures :* Si les miniatures sont activées, ce paramètre contrôle si un aperçu plus grand apparaît au survol d'une miniature.
  - *Affichage des légendes :* Contrôle si et comment les légendes textuelles associées à chaque diapositive sont affichées.
- **Valeur recommandée :**
  - *Largeur du slider :* `100%` pour un slider pleine largeur et réactif, ou une valeur en pixels spécifique comme `1140px` pour correspondre à la zone de contenu principale de votre thème.
  - *Hauteur du slider :* Commencez par `400px` et ajustez en fonction du rapport d'aspect de votre image et de votre design.
  - *Type d'animation :* Expérimentez ! `fade` ou `slice` sont de bons points de départ pour un look épuré.
  - *Vitesse d'animation :* `800` (millisecondes) pour une transition fluide.
  - *Intervalle de diapositive :* `5000` (5 secondes) est un bon équilibre pour que les utilisateurs puissent lire le contenu sans se sentir pressés.
  - *Flèches de navigation :* `OUI` pour un meilleur contrôle utilisateur.
  - *Points/Puces de navigation :* `OUI` pour un aperçu et une navigation faciles.
  - *Miniatures :* `NON` initialement, activez si vous avez de nombreuses diapositives et souhaitez un index visuel.
  - *Aperçu des miniatures :* `OUI` si les miniatures sont activées.
  - *Affichage des légendes :* `OUI` si vous prévoyez d'ajouter du texte à vos diapositives.
- **Scénario/exemple pour le marchand :** Vous souhaitez une bannière pleine largeur sur votre page d'accueil qui alterne entre trois nouvelles gammes de produits. Vous définiriez la largeur à `100%`, choisiriez une animation `fade` et définiriez un intervalle de `5 secondes`. Vous activeriez les flèches de navigation et les points pour que les clients puissent naviguer manuellement s'ils le souhaitent.

#### **Section de gestion des diapositives**

- **Ce que fait ce paramètre :** Cette section vous permet d'ajouter, de modifier et de supprimer des diapositives individuelles de votre slider. Chaque diapositive se compose d'une image et de paramètres associés.
- **Effet de la modification de ce paramètre :**
  - *Ajout d'une nouvelle diapositive :* Une nouvelle image sera ajoutée à la rotation de votre slider. Vous téléchargerez une image, définirez son lien, sa légende et potentiellement une animation unique.
  - *Modification d'une diapositive existante :* Vous pouvez modifier l'image, son lien de destination, le texte de la légende ou le type d'animation individuel pour cette diapositive spécifique.
  - *Suppression d'une diapositive :* La diapositive sélectionnée sera supprimée de votre slider.
  - *Réorganisation des diapositives :* Vous pouvez faire glisser et déposer des diapositives pour modifier l'ordre dans lequel elles apparaissent dans la rotation.
- **Valeur recommandée :** Utilisez toujours des images de haute qualité, optimisées et de taille et de rapport d'aspect cohérents pour un aspect professionnel.
- **Scénario/exemple pour le marchand :** Vous lancez une nouvelle collection d'été. Vous ajouteriez trois diapositives : une pour les robes, une pour les maillots de bain et une pour les accessoires. Chaque diapositive présenterait une image principale, une légende comme « Achetez les robes d'été maintenant ! » et un lien direct vers la page de catégorie respective. Vous pourriez donner à la diapositive des maillots de bain une animation « cube » pour une touche ludique, tandis que les autres utiliseraient « fade ».

#### **Sélection du Hook**

- **Ce que fait ce paramètre :** Cela vous permet de choisir où le slider sera affiché dans votre boutique PrestaShop.
- **Effet de la modification de ce paramètre :** En sélectionnant un hook (par exemple, `displayHeader`, `displayLeftColumn`), le module injectera le code du slider dans cette zone spécifique de votre thème.
- **Valeur recommandée :**
  - Pour une bannière proéminente et pleine largeur : `displayHeader` ou un hook personnalisé fourni par votre thème pour les bannières supérieures.
  - Pour un slider plus petit et contextuel : `displayLeftColumn` ou `displayRightColumn`.
  - Pour les sliders spécifiques aux produits : `displayProductExtraContent` ou `displayProductButtons`.
- **Scénario/exemple pour le marchand :** Vous souhaitez que votre slider promotionnel principal apparaisse juste en dessous du menu principal de votre site web. Vous sélectionneriez le hook `displayHeader` (ou un hook similaire spécifique au thème si disponible). Si vous vouliez un slider plus petit affichant des « produits connexes » sur le côté, vous choisiriez `displayLeftColumn`.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Largeur du slider | `100%` / `1140px` | Définit la taille horizontale du slider. |
| Configuration du module | Hauteur du slider | `400px` | Définit la taille verticale du slider. |
| Configuration du module | Type d'animation | `fade` / `slice` | Définit la transition visuelle entre les diapositives (40 options). |
| Configuration du module | Vitesse d'animation | `800` (ms) | Vitesse à laquelle la transition d'animation se produit. |
| Configuration du module | Intervalle de diapositive | `5000` (ms) | Durée pendant laquelle chaque diapositive est visible avant de changer. |
| Configuration du module | Flèches de navigation | `OUI` | Affiche les flèches gauche/droite pour la navigation manuelle. |
| Configuration du module | Points/Puces de navigation | `OUI` | Affiche des points/puces pour la sélection directe des diapositives. |
| Configuration du module | Miniatures | `NON` | Affiche de petites images d'aperçu de chaque diapositive. |
| Configuration du module | Aperçu des miniatures | `OUI` | Affiche un aperçu plus grand au survol de la miniature (si activé). |
| Configuration du module | Affichage des légendes | `OUI` | Contrôle la visibilité des légendes textuelles sur les diapositives. |
| Configuration du module | Ajouter/Modifier une diapositive | N/A | Télécharger l'image, définir le lien, la légende et l'animation individuelle. |
| Configuration du module | Sélection du Hook | `displayHeader` | Détermine où le slider apparaît dans votre boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mon slider n'apparaît pas après la configuration. Que dois-je faire ?**
R :

1. **Vérifiez la sélection du hook :** Retournez à la configuration du module et assurez-vous d'avoir sélectionné au moins un hook (par exemple, `displayHeader`).
2. **Videz le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).
3. **Vérifiez les conflits :** Désactivez temporairement les autres modules qui pourraient utiliser le même hook ou modifier les mêmes zones de page (en particulier les autres modules de slider).
4. **Compatibilité du thème :** Certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si le problème persiste, contactez le support MyPresta.eu avec les détails de votre thème.

**Q : Mes images sont floues ou étirées dans le slider.**
R : Cela signifie généralement que vos images n'ont pas les bonnes dimensions ou la bonne résolution pour les paramètres de votre slider.

1. **Dimensions cohérentes :** Assurez-vous que toutes les images téléchargées pour vos diapositives ont la même largeur et la même hauteur.
2. **Haute résolution :** Téléchargez des images avec une résolution suffisante. Si votre slider a une largeur de `1140px`, vos images doivent avoir au moins `1140px` de large.
3. **Rapport d'aspect :** Faites correspondre le rapport d'aspect de vos images à la largeur et à la hauteur configurées du slider. Si votre slider est de `1140x400px`, essayez d'utiliser des images avec un rapport d'aspect similaire de 114:40.

**Q : Comment traduire les légendes de mes diapositives dans différentes langues ?**
R : Le module devrait prendre en charge le système de traduction standard de PrestaShop.

1. Allez dans **International > Traductions**.
2. Sélectionnez « Traductions des modules installés », votre thème et la langue dans laquelle vous souhaitez traduire.
3. Trouvez le module « Prestashop Slider » dans la liste. Vous devriez pouvoir modifier les légendes de chaque diapositive directement à cet endroit. Si ce n'est pas le cas, le module pourrait stocker les légendes directement dans la base de données, vous obligeant à modifier chaque diapositive pour chaque langue dans la configuration du module.

**Q : Le slider s'affiche correctement sur ordinateur mais est cassé sur mobile.**
R :

1. **Vérifiez la réactivité :** Le module est conçu pour être réactif. Assurez-vous que votre thème lui-même est réactif.
2. **Conflits CSS :** Un autre module ou le CSS de votre thème pourrait annuler les styles réactifs du slider. Utilisez les outils de développement de votre navigateur pour inspecter le slider sur mobile et rechercher les règles CSS conflictuelles.
3. **Taille de l'image :** Des images très grandes peuvent parfois causer des problèmes sur mobile. Assurez-vous que les images sont optimisées.

**Q : Puis-je avoir plusieurs sliders sur différentes pages ?**
R : La configuration actuelle du module gère généralement une instance de slider principale avec son ensemble de diapositives. Si vous avez besoin de plusieurs sliders *distincts* avec des contenus et des paramètres différents sur différentes pages, vous devrez peut-être dupliquer le module (si votre thème le permet) ou utiliser une solution de slider plus avancée. Pour ce module, vous configurerez un slider et choisirez son emplacement via des hooks.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une plongée approfondie dans la structure technique du module Prestashop Slider, destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module `Prestashop Slider` (`pslider`) est un module PrestaShop standard qui utilise principalement la classe `Module`. Il gère sa configuration et ses données de diapositives directement dans la table `ps_configuration`. L'affichage en front-office est géré par des templates Smarty rendus via le système de hooks de PrestaShop, injectant des ressources JavaScript et CSS pour la fonctionnalité du slider. Le module utilise le plugin jQuery `Skitter` pour ses capacités d'animation.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit pas de classes personnalisées étendant `ObjectModel`. Toutes les données de configuration et de diapositives sont stockées sous forme de tableaux sérialisés dans la table `ps_configuration`, gérées directement par la classe `Configuration`.

### 4.4 Ressources JavaScript (`views/js/`)

Le module s'appuie sur le plugin jQuery Skitter pour sa fonctionnalité de slider.

- `pslider/js/jquery.easing.1.3.js` :
  - **Portée :** Front-office.
  - **Objectif :** Fournit des fonctions d'assouplissement avancées pour les animations jQuery, améliorant la fluidité visuelle des transitions utilisées par le plugin Skitter.
- `pslider/js/jquery.skitter.js` :
  - **Portée :** Front-office.
  - **Objectif :** C'est le plugin de slider Skitter principal. Il initialise le slider, gère les transitions de diapositives, la navigation et la réactivité. Il lit les options de configuration (type d'animation, vitesse, intervalle, etc.) à partir des paramètres du module et les applique à l'instance du slider.
- `pslider/js/noconflict.js` :
  - **Portée :** Front-office.
  - **Objectif :** Garantit que jQuery fonctionne en mode `noConflict()`, empêchant les conflits avec d'autres bibliothèques JavaScript (comme Prototype.js, que PrestaShop 1.6 et les versions antérieures utilisaient parfois) qui pourraient également utiliser l'alias `$`. Ceci est crucial pour la compatibilité.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut un seul fichier CSS pour styliser le slider Skitter.

- `pslider/css/skitter.styles.css` :
  - **Portée :** Style client du Front-office.
  - **Objectif :** Contient tous les styles visuels par défaut du slider Skitter, y compris :
    - La mise en page du conteneur du slider (`.box_skitter`).
    - Le style des éléments de navigation (flèches, points, miniatures).
    - L'apparence par défaut des légendes.
    - Les ajustements réactifs.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :**
    - `.box_skitter` : Conteneur principal du slider.
    - `.box_skitter ul` : Liste des diapositives.
    - `.box_skitter .info_slide` : Conteneur de la légende.
    - `.box_skitter .nav_cont` : Conteneur de navigation.
    - `.box_skitter .prev_button`, `.box_skitter .next_button` : Flèches de navigation.
    - `.box_skitter .info_slide_dots` : Points de navigation.
    - `.box_skitter .box_thumbs` : Conteneur des miniatures.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise les templates Smarty pour rendre son contenu en front-office et certaines parties de sa configuration en back-office.

- **Templates de hook (`views/templates/hook/`)** :

  - `pslider/header.tpl` : Ce template est probablement destiné à être accroché à `displayHeader` ou à un hook similaire en haut de page. Il contient la structure HTML principale du slider et inclut souvent le code d'initialisation JavaScript nécessaire pour le plugin Skitter.
  - `pslider/top.tpl` : Similaire à `header.tpl`, celui-ci pourrait être utilisé pour un autre hook de niveau supérieur, potentiellement `displayTop` ou un autre hook de bannière spécifique au thème. Il contiendrait également le HTML et l'initialisation JS du slider.
  - `pslider/views/templates/hook/left-column.tpl` : Ce template est spécifiquement conçu pour être placé dans le hook `displayLeftColumn`. Il contiendrait une instance plus petite, potentiellement différente, du slider ou une mise en page modifiée adaptée à une barre latérale.
- **Templates d'administration (`views/templates/admin/`)** :

  - `pslider/views/templates/front/form.tpl` : Bien qu'il se trouve dans `views/templates/front/`, ce fichier est en fait utilisé pour le formulaire de configuration du module dans le Back Office. Il définit la structure HTML des champs de paramètres (largeur, hauteur, animation, gestion des diapositives, etc.) avec lesquels le marchand interagit. Ceci est rendu par la méthode `getContent()` dans `ajax_pslider.php`.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Le module ne crée pas de tables SQL personnalisées.
  - Tous les paramètres de configuration et les données des diapositives (chemins d'image, liens, légendes, types d'animation individuels) sont stockés sous forme de tableaux sérialisés dans la table `ps_configuration`. Les noms de clés suivraient généralement un modèle comme `PSLIDER_WIDTH`, `PSLIDER_SLIDES`, etc.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de la page front-office, ou tout en haut du `<body>`. | Injecte les ressources CSS et JavaScript, et potentiellement la structure HTML principale du slider. |
| `displayTop` | Rendu en haut du contenu de la page, généralement au-dessus de la zone de contenu principale mais en dessous de l'en-tête. | Affiche la bannière principale du slider. |
| `displayLeftColumn` | Rendu dans la barre latérale gauche de la page front-office. | Affiche un slider spécifique à la barre latérale. |
| `displayRightColumn` | Rendu dans la barre latérale droite de la page front-office. | Affiche un slider spécifique à la barre latérale. |
| `displayFooter` | Rendu dans la section du pied de page de la page front-office. | Affiche un slider spécifique au pied de page. |
| `displayProductExtraContent` | Rendu sur la page produit, généralement en dessous des informations principales du produit. | Affiche des sliders liés au produit (par exemple, vues alternatives, fonctionnalités). |
| `displayProductButtons` | Rendu près du bouton « Ajouter au panier » sur la page produit. | Pourrait être utilisé pour de petits sliders contextuels liés au produit. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses ressources multimédias. | Permet au module d'enregistrer ses fichiers JS et CSS de manière conditionnelle. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module Prestashop Slider, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
