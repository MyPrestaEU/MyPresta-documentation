---
title: "Slider des produits récemment vendus - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Slider des produits récemment vendus' par MyPresta.eu."
sidebar:
  label: "Slider des produits récemment vendus - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Recently sold products slider sur MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/recently-sold-products-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/sliders-slideshows/recently-sold-products-slider/)
>
> ---


# Slider des produits récemment vendus

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et sont suffisantes pour ce module.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Slider des produits récemment vendus ». Ici, vous pouvez personnaliser l'apparence, le comportement et le contenu de votre slider de produits.

#### **Couleur d'arrière-plan (rsps\_c\_bg)**

- **Ce que fait ce paramètre :** Il contrôle la couleur d'arrière-plan de l'ensemble du bloc du slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une couleur est définie (par exemple, #FFFFFF pour le blanc) :* L'arrière-plan du slider s'affichera dans cette couleur spécifique, l'aidant à se fondre ou à se démarquer de votre thème.
  - *Lorsqu'il est laissé vide ou invalide :* Le slider pourrait hériter des styles d'arrière-plan de votre thème, ou par défaut, avoir un arrière-plan transparent.
- **Valeur recommandée :** Choisissez une couleur qui complète le design de votre boutique. Souvent, une couleur subtile ou une couleur qui correspond à votre en-tête/pied de page est préférable.
- **Scénario/exemple pour le marchand :** Si votre boutique a un en-tête sombre, le régler sur un gris foncé ou noir pourrait donner au slider un aspect intégré. Si vous voulez qu'il ressorte, une couleur contrastante pourrait fonctionner.

#### **Couleur de la bordure (rsps\_c\_border)**

- **Ce que fait ce paramètre :** Définit la couleur de la bordure autour de l'ensemble du bloc du slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une couleur est définie (par exemple, #CCCCCC pour le gris clair) :* Une bordure de cette couleur apparaîtra autour du slider.
  - *Lorsqu'il est laissé vide ou invalide :* Aucune bordure explicite ne sera appliquée par le module, bien que votre thème puisse toujours en ajouter une.
- **Valeur recommandée :** Souvent, une bordure subtile qui correspond aux autres bordures de votre thème ou une bordure transparente est préférable.
- **Scénario/exemple pour le marchand :** Si votre site utilise de fines bordures grises pour d'autres éléments, le régler sur le même gris maintiendra la cohérence.

#### **Couleur de la police (rsps\_c\_font)**

- **Ce que fait ce paramètre :** Définit la couleur du texte (noms de produits) affiché dans le slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une couleur est définie (par exemple, #333333 pour le gris foncé) :* Les noms de produits apparaîtront dans la couleur choisie.
  - *Lorsqu'il est laissé vide ou invalide :* La couleur du texte pourrait par défaut être la couleur de police générale de votre thème.
- **Valeur recommandée :** Choisissez une couleur qui offre un bon contraste avec la couleur d'arrière-plan du slider pour une meilleure lisibilité.
- **Scénario/exemple pour le marchand :** Si l'arrière-plan de votre slider est sombre, une couleur de police claire (comme le blanc ou le gris clair) sera nécessaire pour la lisibilité.

#### **Rembourrage du slider (rsps\_s\_padding)**

- **Ce que fait ce paramètre :** Contrôle l'espacement interne (rembourrage) entre le contenu (texte) et les bords du bloc du slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une valeur est définie (par exemple, « 10px ») :* Le texte aura 10 pixels d'espace de tous les côtés par rapport à la bordure du slider.
  - *Lorsqu'il est défini sur « 0px » ou vide :* Le texte sera directement contre les bords du slider.
- **Valeur recommandée :** « 5px » ou « 10px » pour donner de l'espace au texte et améliorer l'esthétique.
- **Scénario/exemple pour le marchand :** Si votre texte semble trop serré, augmenter le rembourrage ajoutera plus d'espace autour de lui, le rendant plus propre.

#### **Taille de la police du slider (rsps\_s\_font)**

- **Ce que fait ce paramètre :** Détermine la taille de la police utilisée pour les noms de produits dans le slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une valeur est définie (par exemple, « 14px ») :* Le texte sera affiché à cette taille de pixel spécifique.
  - *Lorsqu'il est laissé vide ou invalide :* La taille de la police pourrait par défaut être la taille de police générale de votre thème.
- **Valeur recommandée :** « 14px » ou « 16px » pour une bonne lisibilité sans être trop grand ou trop petit.
- **Scénario/exemple pour le marchand :** Si le slider est dans un emplacement proéminent comme l'en-tête, une police légèrement plus grande pourrait être appropriée. Pour une barre latérale, une police plus petite pourrait mieux convenir.

#### **Bordure du slider (rsps\_s\_border)**

- **Ce que fait ce paramètre :** Définit l'épaisseur et le style de la bordure autour du *contenu interne* du slider (la zone de texte défilante elle-même), distincte de la bordure globale du bloc.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une valeur est définie (par exemple, « 1px solid #CCCCCC ») :* Une bordure solide gris clair de 1 pixel apparaîtra autour du texte défilant.
  - *Lorsqu'il est laissé vide ou invalide :* Aucune bordure interne explicite ne sera appliquée.
- **Valeur recommandée :** « 0px » ou « none » si vous ne voulez que la bordure du bloc extérieur. Si vous voulez une séparation subtile, « 1px solid #EEEEEE » peut fonctionner.
- **Scénario/exemple pour le marchand :** Vous pourriez l'utiliser pour créer une boîte visuelle distincte pour le texte défilant dans la zone plus grande du slider.

#### **Direction du mouvement (rsps\_m\_dir)**

- **Ce que fait ce paramètre :** Contrôle la direction dans laquelle les noms de produits défilent dans le slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « left » :* Le texte défilera de droite à gauche.
  - *Lorsqu'il est défini sur « right » :* Le texte défilera de gauche à droite.
- **Valeur recommandée :** « left » est une direction de lecture courante et naturelle pour le texte défilant.
- **Scénario/exemple pour le marchand :** La plupart des utilisateurs sont habitués au texte défilant vers la gauche, donc s'en tenir à « left » offre souvent la meilleure expérience utilisateur.

#### **Délai de mouvement (rsps\_m\_delay)**

- **Ce que fait ce paramètre :** Détermine la vitesse de l'animation de défilement. Ceci est généralement mesuré en millisecondes.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une valeur inférieure est définie (par exemple, « 50 ») :* Le texte défilera plus rapidement.
  - *Lorsqu'une valeur supérieure est définie (par exemple, « 100 ») :* Le texte défilera plus lentement.
- **Valeur recommandée :** « 70 » à « 100 » offre une vitesse fluide et lisible sans être trop rapide ou trop lente.
- **Scénario/exemple pour le marchand :** Si le texte est trop rapide, les clients ne peuvent pas le lire. S'il est trop lent, il pourrait ne pas attirer l'attention. Expérimentez pour trouver un équilibre.

#### **Position du slider (rsps\_position)**

- **Ce que fait ce paramètre :** Vous permet de sélectionner le hook PrestaShop où le slider sera affiché dans votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur `displayHome` :* Le slider apparaîtra sur la page d'accueil de votre boutique.
  - *Lorsqu'il est défini sur `displayHeader` :* Le slider apparaîtra dans la section d'en-tête de toutes les pages.
  - *Lorsqu'il est défini sur `displayFooter` :* Le slider apparaîtra dans la section de pied de page de toutes les pages.
  - *Autres options (par exemple, `displayLeftColumn`, `displayRightColumn`, `displayTop`) :* Le slider apparaîtra dans la colonne ou la section supérieure respective.
- **Valeur recommandée :** `displayHeader` ou `displayHome` pour une visibilité maximale, ou `displayFooter` pour une approche plus subtile.
- **Scénario/exemple pour le marchand :** Si vous voulez que chaque visiteur voie immédiatement les ventes récentes, choisissez `displayHeader`. Si vous voulez qu'il fasse partie du contenu de votre page d'accueil, choisissez `displayHome`.

#### **Nombre de produits (rsps\_nb)**

- **Ce que fait ce paramètre :** Spécifie combien de produits récemment vendus doivent être récupérés et affichés dans le slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un nombre inférieur est défini (par exemple, « 5 ») :* Seules les 5 ventes les plus récentes seront affichées.
  - *Lorsqu'un nombre supérieur est défini (par exemple, « 20 ») :* Jusqu'à 20 ventes récentes seront incluses dans la liste défilante.
- **Valeur recommandée :** « 10 » à « 15 » pour assurer une bonne variété de produits sans rendre la liste excessivement longue.
- **Scénario/exemple pour le marchand :** Si votre boutique a de nombreuses ventes, un nombre plus élevé fournit plus de preuve sociale. Si les ventes sont moins fréquentes, un nombre inférieur pourrait être suffisant.

#### **Trier par (rsps\_order)**

- **Ce que fait ce paramètre :** Détermine les critères de tri pour les produits affichés dans le slider.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « date\_add » :* Les produits seront triés par la date à laquelle ils ont été ajoutés à la commande (les plus récents en premier).
  - *Lorsqu'il est défini sur « product\_name » :* Les produits seront triés par ordre alphabétique par nom.
  - *Lorsqu'il est défini sur « price » :* Les produits seront triés par prix.
- **Valeur recommandée :** « date\_add » pour afficher véritablement les articles « récemment vendus ».
- **Scénario/exemple pour le marchand :** Pour refléter avec précision les achats récents, le tri par `date_add` est le choix le plus logique.

#### **Diversité (rsps\_diversity)**

- **Ce que fait ce paramètre :** Ce paramètre contrôle si le slider doit afficher des produits uniques ou permettre au même produit d'apparaître plusieurs fois s'il a été vendu récemment.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (par exemple, « Oui » ou « 1 ») :* Si le même produit a été vendu plusieurs fois, il n'apparaîtra qu'une seule fois dans la liste des produits à afficher, garantissant une plus grande variété d'articles.
  - *Lorsqu'il est désactivé (par exemple, « Non » ou « 0 ») :* Le même produit pourrait apparaître plusieurs fois dans le slider s'il faisait partie de plusieurs commandes récentes.
- **Valeur recommandée :** « Oui » (ou « 1 ») pour présenter une gamme plus large de votre catalogue et éviter que le slider ne devienne répétitif.
- **Scénario/exemple pour le marchand :** Si vous vendez un article très populaire, la désactivation de la diversité pourrait signifier que le slider n'affiche que cet article à plusieurs reprises. L'activation garantit que d'autres produits ont une chance d'être vus.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Couleur d'arrière-plan** (rsps\_c\_bg) | `#FFFFFF` (Blanc) | Définit la couleur d'arrière-plan du bloc du slider. |
| Configuration du module | **Couleur de la bordure** (rsps\_c\_border) | `#CCCCCC` (Gris clair) | Définit la couleur de la bordure autour du bloc du slider. |
| Configuration du module | **Couleur de la police** (rsps\_c\_font) | `#333333` (Gris foncé) | Définit la couleur du texte des noms de produits. |
| Configuration du module | **Rembourrage du slider** (rsps\_s\_padding) | `10px` | Espacement interne autour du texte dans le slider. |
| Configuration du module | **Taille de la police du slider** (rsps\_s\_font) | `14px` | Taille de la police pour les noms de produits. |
| Configuration du module | **Bordure du slider** (rsps\_s\_border) | `0px` | Bordure autour de la zone de texte défilante elle-même. |
| Configuration du module | **Direction du mouvement** (rsps\_m\_dir) | `left` | Direction de l'animation de défilement (gauche ou droite). |
| Configuration du module | **Délai de mouvement** (rsps\_m\_delay) | `70` | Vitesse de l'animation de défilement (plus faible = plus rapide). |
| Configuration du module | **Position du slider** (rsps\_position) | `displayHeader` | Hook PrestaShop où le slider sera affiché. |
| Configuration du module | **Nombre de produits** (rsps\_nb) | `10` | Nombre maximum de produits récemment vendus à afficher. |
| Configuration du module | **Trier par** (rsps\_order) | `date_add` | Critères de tri pour les produits affichés. |
| Configuration du module | **Diversité** (rsps\_diversity) | `Oui` (1) | Assure l'affichage de produits uniques (évite la répétition). |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré le module, mais le slider n'apparaît pas sur ma boutique.**
**R1 :**

-   **Vérifier la position du hook :** Allez dans **Design > Positions** dans votre Back Office PrestaShop. Recherchez le hook que vous avez sélectionné dans le paramètre « Position du slider » du module (par exemple, `displayHeader`, `displayHome`). Assurez-vous que le module « Slider des produits récemment vendus » est listé et activé dans ce hook. Si ce n'est pas le cas, vous devrez peut-être « Greffer un module » au bon hook.
-   **Vider le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite.
-   **Module activé :** Vérifiez que le module est activé dans **Modules > Gestionnaire de modules**.
-   **Ventes récentes :** Assurez-vous que vous avez réellement des ventes récentes dans votre boutique. Le module s'appuie sur les données de commande existantes.

**Q2 : Le slider s'affiche, mais les couleurs ou les tailles de police ne sont pas celles que j'ai définies.**
**R2 :**

-   **Vider le cache :** C'est la raison la plus courante des problèmes de style. Videz le cache de votre PrestaShop (**Paramètres avancés > Performances**) et le cache de votre navigateur (Ctrl+F5 ou Cmd+R).
-   **Surcharges de thème :** Votre thème PrestaShop peut avoir son propre CSS qui surcharge les styles du module. Vous devrez peut-être inspecter l'élément à l'aide des outils de développement de votre navigateur (F12) pour voir quelles règles CSS sont appliquées. S'il s'agit d'un conflit de thème, vous devrez peut-être ajouter du CSS personnalisé à votre thème pour forcer les styles du module.
-   **Saisie correcte :** Assurez-vous d'utiliser des codes de couleur CSS valides (par exemple, `#RRGGBB` ou `rgba(R,G,B,A)`) et des valeurs en pixels (par exemple, `14px`) dans la configuration du module.

**Q3 : Le texte défile trop vite/lentement, ou il est difficile à lire.**
**R3 :**

-   **Délai de mouvement :** Ajustez le paramètre « Délai de mouvement ». Un nombre plus élevé le rend plus lent, un nombre plus faible le rend plus rapide. Expérimentez jusqu'à ce que vous trouviez une vitesse de lecture confortable.
-   **Taille de police et contraste :** Assurez-vous que votre « Taille de police du slider » est adéquate et que votre « Couleur de police » a un bon contraste avec votre « Couleur d'arrière-plan ».
-   **Nombre de produits :** Si vous avez trop de produits et une vitesse très rapide, cela pourrait être accablant. Réduisez le « Nombre de produits » ou ralentissez le « Délai de mouvement ».

**Q4 : Puis-je traduire le texte « Quelqu'un vient d'acheter… » dans d'autres langues ?**
**R4 :** Oui, les modules PrestaShop sont généralement traduisibles.

-   Allez dans **International > Traductions** dans votre Back Office.
-   Sélectionnez « Traductions des modules installés » pour le « Type de traduction ».
-   Choisissez votre thème.
-   Sélectionnez la langue que vous souhaitez traduire.
-   Recherchez le module « Slider des produits récemment vendus » dans la liste et vous devriez pouvoir modifier les chaînes traduisibles.

**Q5 : Le slider s'affiche correctement sur ordinateur de bureau mais est cassé ou mal formaté sur mobile.**
**R5 :**

-   **Vider le cache :** Commencez toujours par vider le cache de PrestaShop et du navigateur.
-   **Réactivité du thème :** Bien que le module lui-même soit conçu pour être réactif, des conflits avec le CSS réactif spécifique de votre thème peuvent survenir.
-   **Vérifier le rembourrage/les bordures :** Un rembourrage ou des bordures excessifs peuvent pousser le contenu hors de vue sur les petits écrans. Essayez de réduire temporairement le « Rembourrage du slider » ou la « Bordure du slider » pour voir si cela résout le problème.
-   **Inspecter sur mobile :** Utilisez les outils de développement de votre navigateur (F12) et passez en mode mobile, ou testez directement sur un appareil mobile, pour diagnostiquer les problèmes de mise en page spécifiques. Un CSS personnalisé pourrait être nécessaire dans votre thème pour s'adapter au mobile si un conflit existe.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Slider des produits récemment vendus » pour les développeurs, les webmasters et les agences techniques.

### 4.1 Aperçu de l'architecture

Le module « Slider des produits récemment vendus » (`recentlysoldproducts`) suit une architecture de module PrestaShop standard. C'est un module à fichier unique (`recentlysoldproducts.php`) qui étend `Module`, gérant sa propre installation, désinstallation, configuration (`getContent()`) et affichage front-office via des hooks. Il utilise la classe `Configuration` de PrestaShop pour le stockage des paramètres et Smarty pour le templating. La fonctionnalité front-office est principalement pilotée par JavaScript pour l'animation de défilement et le style.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office dédiés. Toute la configuration est gérée dans la méthode `getContent()` du fichier de module principal, et le rendu front-office est géré directement via les hooks PrestaShop.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient **pas** de classes personnalisées ou de définitions `ObjectModel` dans un répertoire `classes/`. Il interroge directement la base de données PrestaShop pour les informations de commande et de produit dans le fichier de module principal.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`recentlysoldproducts/jscolor/jscolor.js`**

    -   **Portée :** Back-office (utilisé dans `getContent()` pour les sélecteurs de couleur).
    -   **Description :** Il s'agit d'une bibliothèque JavaScript tierce qui fournit une interface de sélecteur de couleur conviviale pour les champs de saisie. Elle est intégrée au formulaire de configuration du module pour permettre aux marchands de sélectionner facilement les couleurs pour l'arrière-plan, la bordure et la police du slider. Elle fonctionne généralement en ajoutant une classe (par exemple, `jscolor`) à un champ de saisie, qui le transforme ensuite en sélecteur de couleur.
-   **`recentlysoldproducts/js/script.js`**

    -   **Portée :** Front-office.
    -   **Description :** Ce fichier contient probablement la logique principale de l'animation de défilement du slider. Il devrait typiquement :
        -   Sélectionner l'élément conteneur du slider (par exemple, par ID ou classe).
        -   Initialiser les variables pour la direction du mouvement, la vitesse et le contenu.
        -   Implémenter une boucle d'animation de défilement continue, potentiellement en utilisant `setInterval` ou `requestAnimationFrame`.
        -   Gérer le clonage d'éléments pour créer un effet de boucle infinie.
        -   S'adapter à la réactivité ou aux pauses au survol.
-   **`recentlysoldproducts/recentlysoldproducts.js`**

    -   **Portée :** Front-office.
    -   **Description :** Ce fichier pourrait contenir du JavaScript front-office supplémentaire spécifique à l'initialisation ou à l'interaction du module. Il pourrait être responsable de :
        -   Charger le contenu du slider dynamiquement (bien que dans ce module, il soit probablement rendu par Smarty).
        -   Mettre en place des écouteurs d'événements (par exemple, pour mettre en pause le slider au survol de la souris).
        -   Assurer que le slider s'initialise correctement après que le DOM est prêt.
        -   Potentiellement gérer AJAX si le module devait récupérer des données de manière asynchrone (bien que non explicitement indiqué par la structure du module).

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`recentlysoldproducts/css.css`**

    -   **Portée :** Front-office.
    -   **Description :** Il s'agit probablement de la feuille de style principale pour l'affichage front-office du slider. Elle définirait :
        -   La mise en page et le positionnement du conteneur du slider.
        -   Le style de base des éléments de texte défilants (par exemple, `font-size`, `color`, `padding`).
        -   Les styles pour l'arrière-plan et les bordures basés sur la configuration du module.
        -   Potentiellement des ajustements réactifs pour différentes tailles d'écran.
        -   Sélecteurs clés : `.recentlysoldproducts_block`, `.recentlysoldproducts_item`, etc.
-   **`recentlysoldproducts/recentlysoldproducts.css`**

    -   **Portée :** Front-office.
    -   **Description :** Ce fichier pourrait contenir des règles de style supplémentaires ou spécifiques, potentiellement pour des effets visuels plus avancés ou pour remplacer les styles de thème par défaut. Compte tenu du nom, il pourrait également s'agir d'un fichier redondant ou hérité, ou contenir un style plus spécifique pour le mécanisme de défilement lui-même, distinct du style général du bloc dans `css.css`. Les développeurs doivent vérifier les règles qui se chevauchent et les conflits potentiels.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **`recentlysoldproducts/views/front/rsps.tpl`**
    -   **Portée :** Front-office (template de hook).
    -   **Description :** C'est le fichier de template principal responsable du rendu de la structure HTML du slider des produits récemment vendus.
    -   **Rendu dans les hooks :** `rightColumn`, `displayrightColumn`, `home`, `top`, `displayleftColumn`, `footer`, `displayhome`, `displayheader`, `displaytop`, `displayfooter`, `header`, `leftColumn`.
    -   **Contenu :** Il reçoit des données (par exemple, une liste de produits récemment vendus, les paramètres de configuration du module) des méthodes `hookDisplay*` dans `recentlysoldproducts.php`. Il itère ensuite sur la liste des produits pour générer le texte défilant, en appliquant des styles ou des classes en ligne basés sur les paramètres de configuration du module (couleurs, tailles de police, rembourrage, etc.). Il contiendra le wrapper HTML principal pour le slider et les entrées de produits individuelles.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données :**

    -   Ce module ne crée aucune table de base de données personnalisée.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop. Les clés utilisées sont :
        -   `RSPS_C_BG`
        -   `RSPS_C_BORDER`
        -   `RSPS_C_FONT`
        -   `RSPS_S_PADDING`
        -   `RSPS_S_FONT`
        -   `RSPS_S_BORDER`
        -   `RSPS_M_DIR`
        -   `RSPS_M_DELAY`
        -   `RSPS_POSITION`
        -   `RSPS_NB`
        -   `RSPS_ORDER`
        -   `RSPS_DIVERSITY`
    -   Il interroge les tables PrestaShop existantes, principalement `ps_orders`, `ps_order_detail`, `ps_product_lang` et `ps_product` pour récupérer les informations sur les produits récemment vendus.
-   **Table des hooks enregistrés :**

| Nom du hook | Moment et emplacement d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Enregistre les actifs CSS/JS et potentiellement rend un élément caché pour l'initialisation JS. |
| `header` | Alias de `displayHeader` dans les anciennes versions de PrestaShop. | Identique à `displayHeader`. |
| `displayHome` | Sur la page d'accueil, généralement dans la zone de contenu principale. | Rend le bloc du slider sur la page d'accueil de la boutique. |
| `home` | Alias de `displayHome` dans les anciennes versions de PrestaShop. | Identique à `displayHome`. |
| `displayTop` | Dans la section supérieure de la page, souvent sous l'en-tête. | Rend le bloc du slider dans la zone de contenu supérieure. |
| `top` | Alias de `displayTop` dans les anciennes versions de PrestaShop. | Identique à `displayTop`. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages applicables. | Rend le bloc du slider dans la colonne de gauche. |
| `leftColumn` | Alias de `displayLeftColumn` dans les anciennes versions de PrestaShop. | Identique à `displayLeftColumn`. |
| `displayRightColumn` | Dans la barre latérale droite des pages applicables. | Rend le bloc du slider dans la colonne de droite. |
| `rightColumn` | Alias de `displayRightColumn` dans les anciennes versions de PrestaShop. | Identique à `displayRightColumn`. |
| `displayFooter` | Dans la section de pied de page de chaque page. | Rend le bloc du slider dans le pied de page. |
| `footer` | Alias de `displayFooter` dans les anciennes versions de PrestaShop. | Identique à `displayFooter`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Slider des produits récemment vendus », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
