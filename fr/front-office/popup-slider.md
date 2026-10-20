---
title: "Popup Slider - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Popup Slider par MyPresta.eu."
sidebar:
  label: "Popup Slider - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Popup Slider sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/popup-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/popup-slider/)
>
> ---


# Popup Slider

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module Popup Slider, où vous définirez l'apparence et le comportement de votre popup.

#### Paramètres généraux

-   **Largeur de la popup (px) :**
    *   **Ce que fait ce paramètre :** Définit la largeur de la fenêtre contextuelle en pixels.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une valeur spécifique (par exemple, 800) :* La popup apparaîtra exactement de 800 pixels de large sur les écrans de bureau.
        *   *Lorsqu'il est défini sur une valeur différente :* La popup se redimensionnera en conséquence.
    *   **Valeur recommandée :** 800px (ou ajustez en fonction de la taille de vos images et de votre design).
    *   **Scénario/exemple pour le marchand :** Si vos images de slider font 800px de large, définir ce paramètre à 800px garantit qu'elles s'adaptent parfaitement sans problèmes de mise à l'échelle.
-   **Hauteur de la popup (px) :**
    *   **Ce que fait ce paramètre :** Définit la hauteur de la fenêtre contextuelle en pixels.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une valeur spécifique (par exemple, 500) :* La popup apparaîtra exactement de 500 pixels de haut.
        *   *Lorsqu'il est défini sur une valeur différente :* La popup se redimensionnera en conséquence.
    *   **Valeur recommandée :** 500px (ou ajustez en fonction de la taille de vos images et de votre design).
    *   **Scénario/exemple pour le marchand :** Si vos images de slider font 500px de haut, définir ce paramètre à 500px garantit qu'elles s'adaptent parfaitement.
-   **Couleur de fond de la popup :**
    *   **Ce que fait ce paramètre :** Définit la couleur de fond de la fenêtre contextuelle elle-même (la zone derrière les images de votre slider). Vous pouvez utiliser un sélecteur de couleurs pour choisir.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur spécifique (par exemple, #FFFFFF pour le blanc) :* Le fond de la popup affichera cette couleur.
        *   *Lorsqu'il est défini sur une couleur différente :* La couleur de fond change.
    *   **Valeur recommandée :** #FFFFFF (blanc) ou une couleur qui complète le design de votre boutique.
    *   **Scénario/exemple pour le marchand :** Si votre boutique a un thème sombre, vous pourriez choisir un gris clair (#F5F5F5) pour le fond de la popup afin de faire ressortir le contenu.
-   **Couleur de la bordure de la popup :**
    *   **Ce que fait ce paramètre :** Définit la couleur de la bordure autour de la fenêtre contextuelle.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur spécifique (par exemple, #CCCCCC pour le gris clair) :* La popup aura une bordure de cette couleur.
        *   *Lorsqu'il est défini sur une couleur différente :* La couleur de la bordure change.
    *   **Valeur recommandée :** #CCCCCC (gris clair) ou une couleur qui correspond à votre marque.
    *   **Scénario/exemple pour le marchand :** Une bordure subtile peut aider à définir la popup par rapport à un arrière-plan chargé.
-   **Largeur de la bordure de la popup (px) :**
    *   **Ce que fait ce paramètre :** Définit l'épaisseur de la bordure de la popup en pixels.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 1 :* La bordure aura 1 pixel d'épaisseur.
        *   *Lorsqu'il est défini sur 0 :* Aucune bordure ne sera visible.
    *   **Valeur recommandée :** 1px ou 0px.
    *   **Scénario/exemple pour le marchand :** Une bordure de 0px peut créer un aspect plus homogène et moderne si votre design ne nécessite pas de bordure visible.
-   **Rayon de la bordure de la popup (px) :**
    *   **Ce que fait ce paramètre :** Contrôle l'arrondi des coins de la popup. Une valeur plus élevée signifie des coins plus arrondis.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 0 :* La popup aura des coins nets et carrés.
        *   *Lorsqu'il est défini sur 10 :* Les coins seront légèrement arrondis.
    *   **Valeur recommandée :** 5px ou 0px.
    *   **Scénario/exemple pour le marchand :** Les coins arrondis peuvent donner à votre popup une esthétique plus douce et moderne.
-   **Ombre de la popup :**
    *   **Ce que fait ce paramètre :** Ajoute un effet d'ombre autour de la popup, la faisant apparaître comme flottant au-dessus de la page.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (OUI) :* Une ombre subtile apparaîtra autour de la popup.
        *   *Lorsqu'il est désactivé (NON) :* La popup n'aura pas d'ombre.
    *   **Valeur recommandée :** OUI.
    *   **Scénario/exemple pour le marchand :** Une ombre aide la popup à se démarquer du contenu d'arrière-plan, améliorant la visibilité et la profondeur perçue.
-   **Couleur de l'incrustation de la popup :**
    *   **Ce que fait ce paramètre :** Définit la couleur de l'incrustation semi-transparente qui couvre le reste du contenu de votre boutique lorsque la popup est active.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une couleur spécifique (par exemple, #000000 pour le noir) :* L'incrustation aura cette couleur.
    *   **Valeur recommandée :** #000000 (noir).
    *   **Scénario/exemple pour le marchand :** Une incrustation sombre aide à concentrer l'attention du visiteur uniquement sur le contenu de la popup.
-   **Opacité de l'incrustation de la popup (0-1) :**
    *   **Ce que fait ce paramètre :** Contrôle la transparence de l'incrustation. 0 est entièrement transparent, 1 est entièrement opaque.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 0.5 :* L'incrustation sera 50% transparente, permettant de voir une partie du contenu de la boutique en arrière-plan.
        *   *Lorsqu'il est défini sur 0.8 :* L'incrustation sera 80% opaque, rendant le contenu d'arrière-plan très estompé.
    *   **Valeur recommandée :** 0.7 ou 0.8.
    *   **Scénario/exemple pour le marchand :** Une opacité plus élevée garantit que la popup est la principale cible, tandis qu'une opacité plus faible pourrait être utilisée si vous souhaitez subtilement faire allusion au contenu derrière la popup.
-   **Temps de réaffichage de la popup (heures) :**
    *   **Ce que fait ce paramètre :** Détermine le nombre d'heures qui doivent s'écouler avant que la popup ne soit à nouveau affichée au même visiteur après qu'il l'ait fermée.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 0 :* La popup apparaîtra chaque fois que le visiteur charge une page (non recommandé pour l'expérience utilisateur).
        *   *Lorsqu'il est défini sur 24 :* La popup réapparaîtra après 24 heures.
        *   *Lorsqu'il est défini sur un nombre très élevé (par exemple, 8760 pour 1 an) :* La popup ne s'affichera effectivement qu'une seule fois par visiteur.
    *   **Valeur recommandée :** 24 (pour les promotions quotidiennes) ou 168 (pour les promotions hebdomadaires) ou un nombre très élevé comme 8760 (pour une fois par an ou effectivement une seule fois).
    *   **Scénario/exemple pour le marchand :** Si vous proposez des offres quotidiennes, définir ce paramètre à 24 heures garantit que les visiteurs voient la nouvelle offre chaque jour. Si vous ne souhaitez afficher un message de bienvenue qu'une seule fois, définissez-le sur un nombre très élevé.
-   **Afficher le bouton de fermeture :**
    *   **Ce que fait ce paramètre :** Active ou désactive la visibilité du bouton de fermeture « X » sur la popup.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (OUI) :* Un bouton de fermeture sera visible, permettant aux visiteurs de fermer facilement la popup.
        *   *Lorsqu'il est désactivé (NON) :* Aucun bouton de fermeture ne sera affiché. Les visiteurs devront cliquer en dehors de la popup ou naviguer ailleurs pour la fermer.
    *   **Valeur recommandée :** OUI.
    *   **Scénario/exemple pour le marchand :** Fournissez toujours un moyen clair aux utilisateurs de fermer la popup pour éviter la frustration et améliorer l'expérience utilisateur.
-   **Fermer au clic sur l'incrustation :**
    *   **Ce que fait ce paramètre :** Détermine si un clic sur l'incrustation semi-transparente (en dehors du contenu de la popup) fermera la popup.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (OUI) :* Un clic sur l'incrustation fermera la popup.
        *   *Lorsqu'il est désactivé (NON) :* Seul le bouton de fermeture (si activé) ou la navigation ailleurs fermera la popup.
    *   **Valeur recommandée :** OUI.
    *   **Scénario/exemple pour le marchand :** Cela offre un moyen intuitif et courant aux utilisateurs de fermer les popups, améliorant l'utilisabilité.

#### Configuration des images du slider

Cette section vous permet d'ajouter, de modifier et de gérer les images qui apparaîtront dans votre slider de popup. Vous pouvez ajouter un nombre illimité d'images.

Pour chaque emplacement d'image, vous trouverez généralement :

-   **Champ de téléchargement d'image :**
    *   **Ce que fait ce paramètre :** Vous permet de télécharger un fichier image depuis votre ordinateur pour l'afficher dans le slider.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une image est téléchargée :* Elle remplace toute image existante dans cet emplacement ou en ajoute une nouvelle au slider.
    *   **Valeur recommandée :** Utilisez des images de haute qualité, optimisées, qui correspondent au rapport d'aspect de la largeur/hauteur de votre popup.
    *   **Scénario/exemple pour le marchand :** Téléchargez votre dernière photo de produit, une bannière pour une vente ou un graphique faisant la promotion d'une nouvelle fonctionnalité.
-   **Lien de l'image (URL) :**
    *   **Ce que fait ce paramètre :** Spécifie l'URL vers laquelle les visiteurs seront redirigés lorsqu'ils cliqueront sur cette image spécifique du slider.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une URL est saisie :* Cliquer sur l'image mènera le visiteur à cette page.
        *   *Lorsqu'il est laissé vide :* L'image ne sera pas cliquable.
    *   **Valeur recommandée :** Toujours lier à des pages pertinentes (produit, catégorie, article de blog, page de contact).
    *   **Scénario/exemple pour le marchand :** Liez une bannière « Nouveautés » à votre page de catégorie de nouveaux produits, ou une bannière « Soldes d'été » à votre page de destination des soldes.
-   **Titre/Texte alternatif de l'image :**
    *   **Ce que fait ce paramètre :** Fournit une description textuelle de l'image. Ce texte est important pour le référencement (moteurs de recherche) et l'accessibilité (lecteurs d'écran pour les utilisateurs malvoyants).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'un texte est saisi :* Ce texte sera utilisé par les moteurs de recherche pour comprendre le contenu de l'image et par les lecteurs d'écran pour décrire l'image.
    *   **Valeur recommandée :** Une phrase concise et descriptive qui décrit précisément le contenu de l'image et inclut des mots-clés pertinents.
    *   **Scénario/exemple pour le marchand :** Pour une image d'une nouvelle robe, utilisez « Nouvelle robe de la collection d'été - Achetez maintenant ».
-   **Bouton Supprimer l'image :**
    *   **Ce que fait ce paramètre :** Supprime l'image sélectionnée du slider.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est cliqué :* L'image et ses paramètres associés sont supprimés de la configuration du slider.
    *   **Valeur recommandée :** Utilisez ceci pour supprimer les promotions ou images obsolètes.
    *   **Scénario/exemple pour le marchand :** Après la fin d'une vente, supprimez l'image de la bannière faisant la promotion de cette vente.
-   **Bouton Ajouter une nouvelle image :**
    *   **Ce que fait ce paramètre :** Ajoute un nouvel emplacement vide pour que vous puissiez télécharger une autre image dans le slider.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est cliqué :* Un nouvel ensemble de champs de téléchargement d'image, de lien et de titre apparaît.
    *   **Valeur recommandée :** Utilisez ceci pour étendre le contenu de votre slider.
    *   **Scénario/exemple pour le marchand :** Ajoutez une nouvelle diapositive pour une promotion de vacances à venir.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Largeur de la popup (px) | 800 | Définit la largeur de la fenêtre contextuelle. |
| Configuration du module | Hauteur de la popup (px) | 500 | Définit la hauteur de la fenêtre contextuelle. |
| Configuration du module | Couleur de fond de la popup | #FFFFFF | Couleur de fond de la zone de contenu de la popup. |
| Configuration du module | Couleur de la bordure de la popup | #CCCCCC | Couleur de la bordure autour de la popup. |
| Configuration du module | Largeur de la bordure de la popup (px) | 1 | Épaisseur de la bordure de la popup. |
| Configuration du module | Rayon de la bordure de la popup (px) | 5 | Arrondi des coins de la popup. |
| Configuration du module | Ombre de la popup | OUI | Ajoute un effet d'ombre pour la profondeur. |
| Configuration du module | Couleur de l'incrustation de la popup | #000000 | Couleur de l'incrustation de fond semi-transparente. |
| Configuration du module | Opacité de l'incrustation de la popup (0-1) | 0.7 | Niveau de transparence de l'incrustation. |
| Configuration du module | Temps de réaffichage de la popup (heures) | 24 | Durée avant que la popup ne s'affiche à nouveau à un visiteur. |
| Configuration du module | Afficher le bouton de fermeture | OUI | Affiche un bouton « X » pour fermer la popup. |
| Configuration du module | Fermer au clic sur l'incrustation | OUI | Permet de fermer la popup en cliquant en dehors d'elle. |
| Configuration du module | Champ de téléchargement d'image | N/A | Télécharge une image pour une diapositive. |
| Configuration du module | Lien de l'image (URL) | N/A | URL vers laquelle naviguer en cliquant sur l'image de la diapositive. |
| Configuration du module | Titre/Texte alternatif de l'image | N/A | Texte descriptif pour le référencement et l'accessibilité. |
| Configuration du module | Bouton Supprimer l'image | N/A | Supprime une diapositive du slider. |
| Configuration du module | Bouton Ajouter une nouvelle image | N/A | Ajoute un nouvel emplacement de diapositive vide. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q1 : Ma popup ne s'affiche pas du tout. Que dois-je vérifier ?**
R1 :

-   **Module activé :** Tout d'abord, assurez-vous que le module est activé dans **Modules > Gestionnaire de modules**.
-   **Configuration enregistrée :** Assurez-vous d'avoir enregistré vos paramètres de configuration après avoir effectué des modifications.
-   **Images ajoutées :** Avez-vous téléchargé au moins une image dans la configuration du slider ? Le slider n'apparaîtra pas s'il n'y a pas d'images.
-   **Cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**) et le cache de votre navigateur. Parfois, d'anciens fichiers mis en cache empêchent le chargement du nouveau contenu du module.
-   **Temps de réaffichage :** Si vous avez déjà visité votre site, le « Temps de réaffichage de la popup » pourrait l'empêcher de s'afficher à nouveau. Essayez d'ouvrir votre boutique dans une fenêtre de navigation privée/incognito pour simuler un nouveau visiteur.

**Q2 : Ma popup a l'air étrange ou n'est pas centrée correctement sur mon thème personnalisé.**
R2 :

-   **Conflits de thème :** Les thèmes personnalisés ont parfois des styles CSS conflictuels.
-   **Paramètres de largeur/hauteur :** Vérifiez à nouveau vos paramètres de « Largeur de la popup » et de « Hauteur de la popup » dans la configuration du module. Assurez-vous qu'ils sont appropriés pour vos images et les tailles d'écran.
-   **Assistance développeur :** Si le problème persiste, il pourrait nécessiter un petit ajustement CSS par un développeur web familier avec votre thème. Ils peuvent inspecter les éléments et appliquer des styles personnalisés pour résoudre les conflits.

**Q3 : Les images de mon slider sont floues ou déformées.**
R3 :

-   **Qualité de l'image :** Assurez-vous que les images que vous téléchargez sont en haute résolution et non pixelisées.
-   **Rapport d'aspect :** Les images doivent idéalement correspondre au rapport d'aspect (rapport largeur/hauteur) que vous avez défini pour votre « Largeur de la popup » et votre « Hauteur de la popup ». Si vos images ont un rapport différent, elles pourraient être étirées ou compressées pour s'adapter.
-   **Optimisation de l'image :** Bien qu'une haute résolution soit bonne, des fichiers de taille excessivement grande peuvent ralentir votre site. Optimisez vos images pour une utilisation web (par exemple, compressez-les) avant de les télécharger.

**Q4 : Puis-je avoir différentes popups pour différentes pages ou groupes de clients ?**
R4 : Le module Popup Slider, dans sa version actuelle, affiche une seule popup globale à tous les visiteurs en fonction de la logique de réaffichage. Il ne prend pas en charge nativement différentes popups pour des pages ou des groupes de clients spécifiques. Pour une telle fonctionnalité avancée, vous auriez généralement besoin d'un module plus complexe ou d'un développement personnalisé.

**Q5 : Comment traduire le texte du module (par exemple, le texte du bouton de fermeture, s'il y en a un) ?**
R5 : Bien que ce module utilise principalement des images, tous les éléments de texte par défaut seraient traduisibles via le système de traduction de PrestaShop :

-   Naviguez vers **International > Traductions**.
-   Sélectionnez « Traductions des modules installés ».
-   Choisissez votre thème, votre langue, puis recherchez « Popup Slider » dans la liste des modules.
-   Vous pouvez ensuite modifier toutes les chaînes traduisibles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse technique approfondie de l'architecture du module Popup Slider, destinée aux développeurs et aux webmasters.

### 4.1 Aperçu de l'architecture

Le module Popup Slider (`popupslider/cz.php`) est un module PrestaShop classique 1.4-1.6, utilisant principalement la classe `Module` pour sa fonctionnalité principale. Il s'intègre au front-office via un hook (généralement `displayHeader` ou `displayFooter` implicitement, bien que la documentation mentionne `Header, Columns, Product, or Footer` comme zones d'affichage potentielles, le template fourni `header.tpl` suggère que `displayHeader` est le point d'intégration principal). La configuration est gérée via la méthode `getContent()`, stockant les paramètres dans `ps_configuration`. L'interaction front-office est gérée en injectant du JavaScript et du CSS, qui ensuite affiche le slider à l'aide de la bibliothèque bxSlider.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ni aucune instance d'`ObjectModel`. Toutes les données de configuration sont stockées directement dans la table `ps_configuration` à l'aide des méthodes standard `Configuration::get()` et `Configuration::updateValue()`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module repose fortement sur JavaScript pour sa fonctionnalité front-office, spécifiquement pour le comportement de la popup et du slider.

-   **`popupslider/jscolor/jscolor.js`** :
    *   **Portée :** Back-office (utilisé dans la page de configuration du module).
    *   **Responsabilité :** Fournit une fonctionnalité de sélecteur de couleurs JavaScript pour le formulaire de configuration du module, permettant aux marchands de sélectionner facilement les couleurs pour le fond, la bordure et l'incrustation de la popup.
    *   **Détails :** Il s'agit d'une bibliothèque tierce intégrée pour l'amélioration de l'interface utilisateur dans le panneau d'administration.
-   **`popupslider/js/bxslider.js`** :
    *   **Portée :** Front-office.
    *   **Responsabilité :** C'est la bibliothèque principale pour le slider d'images animé dans la popup. Elle gère les transitions, les contrôles de navigation (flèches, points) et le comportement réactif du diaporama.
    *   **Détails :** Un slider de contenu jQuery largement utilisé. Le module initialise ce slider sur les images dans la popup.
-   **`popupslider/js/script.js`** :
    *   **Portée :** Front-office.
    *   **Responsabilité :** Ce script personnalisé orchestre l'apparence et le comportement de la popup.
        *   **Gestion des cookies :** Vérifie un cookie pour déterminer si l'utilisateur est un nouveau visiteur ou si le temps de réaffichage s'est écoulé.
        *   **Affichage de la popup :** Déclenche l'affichage de l'incrustation de la popup et du contenu du slider.
        *   **Gestion des événements :** Lie les événements pour fermer la popup (par exemple, en cliquant sur le bouton de fermeture, en cliquant sur l'incrustation).
        *   **Initialisation de bxSlider :** Initialise le `bxslider.js` sur l'élément DOM approprié contenant les images du slider.
    *   **Détails :** Ce script est crucial pour la logique d'affichage « intelligente » du module et l'interaction utilisateur.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module ne liste pas explicitement de fichiers CSS personnalisés dans l'inventaire fourni. Cependant, il est très probable que la bibliothèque `bxslider.js` inclue son propre CSS (par exemple, `jquery.bxslider.css` ou similaire) qui serait chargé, et le `header.tpl` ou `cz.php` du module pourrait injecter des styles en ligne basés sur les paramètres de configuration (couleurs, dimensions).

Si des fichiers CSS étaient présents, ils auraient généralement :

-   **Portée :** Front-office (pour le style de la popup et du slider).
-   **Composants d'interface utilisateur principaux :** Styliser le conteneur de la popup, l'incrustation, le bouton de fermeture, la navigation du slider (flèches, points) et les images de diapositives individuelles.
-   **Sélecteurs de classe CSS clés :** Les développeurs devraient rechercher des classes comme `.popupslider-overlay`, `.popupslider-container`, `.popupslider-close`, `.bx-wrapper`, `.bx-viewport`, `.bx-controls`, etc., à surcharger dans le `custom.css` de leur thème ou dans un thème enfant.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    *   **`popupslider/header.tpl`** :
        *   **Hook :** Probablement `displayHeader` (ou similaire, étant donné le nom). Ce template est responsable du rendu de la structure HTML de l'incrustation de la popup, du conteneur de la popup et du slider d'images lui-même.
        *   **Sortie :** Il génère les éléments `div` nécessaires pour l'incrustation, la boîte principale de la popup, le bouton de fermeture et la liste `ul` que `bxslider.js` transformera en un diaporama interactif. Il inclut également probablement des styles en ligne dérivés des paramètres de configuration du module (largeur, hauteur, couleurs, etc.) et inclut les actifs JavaScript et CSS nécessaires.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Ce module ne crée pas de tables de base de données personnalisées. Tous les paramètres de configuration sont stockés dans la table standard `ps_configuration` de PrestaShop.
    *   **Clés de configuration (Exemples) :**
        *   `POPUP_SLIDER_WIDTH`
        *   `POPUP_SLIDER_HEIGHT`
        *   `POPUP_SLIDER_BG_COLOR`
        *   `POPUP_SLIDER_BORDER_COLOR`
        *   `POPUP_SLIDER_BORDER_WIDTH`
        *   `POPUP_SLIDER_BORDER_RADIUS`
        *   `POPUP_SLIDER_SHADOW`
        *   `POPUP_SLIDER_OVERLAY_COLOR`
        *   `POPUP_SLIDER_OVERLAY_OPACITY`
        *   `POPUP_SLIDER_REDISPLAY_TIME`
        *   `POPUP_SLIDER_SHOW_CLOSE_BTN`
        *   `POPUP_SLIDER_CLOSE_ON_OVERLAY_CLICK`
        *   `POPUP_SLIDER_IMAGE_X` (où X est un ID incrémentiel pour chaque image, stockant l'URL, le lien, le texte alternatif).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Utilisé pour injecter les fichiers CSS et JavaScript du module, et potentiellement la structure HTML initiale de la popup (bien que la popup elle-même soit généralement masquée jusqu'à ce qu'elle soit déclenchée par JS). |
| `displayFooter` (Potentiel) | Exécuté à la fin de la section `<body>` de chaque page du front-office. | Pourrait être utilisé comme alternative à `displayHeader` pour injecter le HTML et le JS de la popup, souvent préféré pour les performances car il ne bloque pas le rendu de la page. |
| `displayRightColumn` (Potentiel) | Exécuté dans la colonne de droite du front-office. | Bien que mentionné dans la description du marchand, il est peu probable qu'une popup pleine page soit rendue ici. Plus probable pour une petite bannière ou un déclencheur. |
| `displayLeftColumn` (Potentiel) | Exécuté dans la colonne de gauche du front-office. | Similaire à `displayRightColumn`, peu probable pour une popup pleine page. |
| `displayProductButtons` (Potentiel) | Exécuté sur la page produit, près du bouton d'ajout au panier. | Peu probable pour une popup globale, mais pourrait être utilisé pour une popup spécifique au produit si le module avait de telles fonctionnalités avancées. |

Compte tenu du fichier `header.tpl`, `displayHeader` est le hook le plus probable pour injecter les actifs du module et la structure initiale de la popup.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Popup Slider, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à fournir une assistance et à garantir le fonctionnement optimal de votre module.

-   **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
-   **Contact support MyPresta.eu :** <https://mypresta.eu/contact>
