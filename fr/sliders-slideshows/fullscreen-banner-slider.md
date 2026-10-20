---
title: "Fullscreen Banner Slider - Manuel Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Fullscreen Banner Slider par MyPresta.eu."
sidebar:
  label: "Fullscreen Banner Slider - Manuel Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Fullscreen Banner Slider sur MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/fullscreen-banner-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/sliders-slideshows/fullscreen-banner-slider/)
>
> ---


# Fullscreen Banner Slider

## 1. Exigences et compatibilité

- **Versions PrestaShop supportées** : PrestaShop 1.5.x, 1.6.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du module "Fullscreen Banner Slider" dans votre Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal où vous pourrez gérer tous les aspects de votre slider.

La configuration du module est gérée via la méthode `getContent()` dans le fichier principal du module, présentant un formulaire de configuration PrestaShop standard.

#### **Paramètres généraux**

-   **Ce que fait ce paramètre :** Ces paramètres contrôlent le comportement général et l'apparence de votre slider plein écran.
-   **Effet de la modification de ce paramètre :** L'ajustement de ces valeurs aura un impact direct sur la façon dont le slider est affiché à vos clients, sa taille, sa vitesse et s'il est actif.

| Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- |
| **Activer le slider plein écran** | OUI | **Objectif :** Active ou désactive la fonctionnalité complète du slider.   **Effet :**   *Lorsqu'activé :* Le slider plein écran apparaîtra aux nouveaux visiteurs.   *Lorsqu'désactivé :* Le slider ne sera pas affiché sur votre boutique.   **Recommandé :** OUI, pour activer la fonctionnalité. |
| **Largeur du slider** | 100% | **Objectif :** Définit la largeur du slider.   **Effet :**   *Défini à 100% (recommandé) :* Le slider s'étendra sur toute la largeur de la fenêtre du navigateur.   *Défini à une valeur fixe en pixels (par exemple, 1200px) :* Le slider aura une largeur fixe, laissant potentiellement un espace vide sur des écrans très larges.   **Recommandé :** 100% pour une véritable expérience plein écran. |
| **Hauteur du slider** | 100% | **Objectif :** Définit la hauteur du slider.   **Effet :**   *Défini à 100% (recommandé) :* Le slider s'étendra sur toute la hauteur de la fenêtre du navigateur.   *Défini à une valeur fixe en pixels (par exemple, 800px) :* Le slider aura une hauteur fixe, laissant potentiellement un espace vide sur des écrans très hauts ou très courts.   **Recommandé :** 100% pour une véritable expérience plein écran. |
| **Type d'animation** | (Menu déroulant avec diverses options) | **Objectif :** Sélectionne l'effet de transition visuel entre les bannières.   **Effet :** Chaque option offre un style d'animation différent (par exemple, fondu, glissement, cube, etc.). Expérimentez pour en trouver un qui correspond à votre marque.   **Recommandé :** Choisissez une animation fluide et pas trop distrayante. "Fondu" ou "Glissement" sont souvent de bons points de départ. |
| **Vitesse d'animation (ms)** | 800 | **Objectif :** Contrôle la vitesse à laquelle la transition entre les bannières se produit, en millisecondes (1000ms = 1 seconde).   **Effet :**   *Valeur plus élevée (par exemple, 1500) :* Transitions plus lentes et plus progressives.   *Valeur plus faible (par exemple, 400) :* Transitions plus rapides et plus vives.   **Recommandé :** 800-1000ms pour une sensation équilibrée et professionnelle. |
| **Intervalle entre les diapositives (ms)** | 3000 | **Objectif :** Définit la durée pendant laquelle chaque bannière est affichée avant de passer à la suivante, en millisecondes.   **Effet :**   *Valeur plus élevée (par exemple, 5000) :* Les bannières restent plus longtemps à l'écran, donnant aux visiteurs plus de temps pour lire/voir.   *Valeur plus faible (par exemple, 2000) :* Les bannières changent plus rapidement, créant une sensation dynamique.   **Recommandé :** 3000-5000ms, selon la complexité du contenu de votre bannière. |
| **Afficher les flèches de navigation** | OUI | **Objectif :** Détermine si les flèches "suivant" et "précédent" sont visibles pour la navigation manuelle des diapositives.   **Effet :**   *Lorsqu'activé :* Les flèches apparaissent sur les côtés du slider, permettant aux utilisateurs de cliquer sur les bannières.   *Lorsqu'désactivé :* Les bannières ne changent automatiquement qu'en fonction de l'intervalle.   **Recommandé :** OUI, pour un meilleur contrôle utilisateur. |
| **Afficher les points de pagination** | OUI | **Objectif :** Détermine si de petits points (ou vignettes) représentant chaque diapositive sont visibles, généralement en bas du slider.   **Effet :**   *Lorsqu'activé :* Les points apparaissent, permettant aux utilisateurs de voir combien de diapositives il y a et de passer à une diapositive spécifique.   *Lorsqu'désactivé :* Aucun indicateur visuel du nombre de diapositives ou de navigation directe.   **Recommandé :** OUI, pour une meilleure orientation et navigation de l'utilisateur. |
| **Lecture automatique du slider** | OUI | **Objectif :** Contrôle si le slider défile automatiquement les bannières.   **Effet :**   *Lorsqu'activé :* Les bannières changeront automatiquement après l'intervalle défini.   *Lorsqu'désactivé :* Les bannières ne changeront que si l'utilisateur clique sur les flèches de navigation ou les points de pagination.   **Recommandé :** OUI, pour s'assurer que tous vos messages sont vus. |
| **Texte du bouton de fermeture** | Fermer | **Objectif :** Vous permet de personnaliser le texte affiché sur le bouton qui ferme le slider plein écran.   **Effet :** Modifie le texte sur le bouton.   **Recommandé :** "Fermer", "Passer" ou "Continuer vers la boutique". |
| **Expiration du cookie (jours)** | 7 | **Objectif :** Définit la durée pendant laquelle le module se souvient qu'un utilisateur a vu le slider, l'empêchant de s'afficher à nouveau.   **Effet :**   *Défini à 7 jours :* Le slider réapparaîtra pour le même utilisateur après 7 jours.   *Défini à 0 :* Le slider apparaîtra à chaque visite (non recommandé pour l'expérience utilisateur).   *Défini à un nombre élevé (par exemple, 365) :* Le slider n'apparaîtra qu'une fois par an pour les visiteurs récurrents.   **Recommandé :** 7 jours est un bon équilibre, vous permettant de réengager les visiteurs récurrents avec de nouvelles offres périodiquement sans être intrusif. |

#### **Gestion des bannières**

Cette section vous permet d'ajouter, de modifier et de supprimer les bannières individuelles qui seront affichées dans votre slider.

-   **Ce que fait ce paramètre :** Chaque entrée ici représente une image (bannière) dans votre slider. Vous pouvez télécharger l'image, la lier à une page spécifique et définir son ordre d'affichage.
-   **Effet de la modification de ce paramètre :**
    -   *Ajouter une nouvelle bannière :* Introduit une nouvelle diapositive dans votre rotation.
    -   *Modifier une bannière :* Met à jour son image, son lien ou sa position.
    -   *Supprimer une bannière :* La supprime du slider.

Pour chaque bannière, vous trouverez généralement des champs tels que :

-   **Image de la bannière :** Téléchargez le fichier image pour votre diapositive. Assurez-vous que les images sont en haute résolution et optimisées pour le web afin de maintenir des temps de chargement rapides.
-   **Lien de la bannière (URL) :** L'adresse web (URL) vers laquelle les clients seront dirigés s'ils cliquent sur cette bannière. Laissez vide si la bannière est purement informative.
-   **Ordre d'affichage :** Une valeur numérique qui détermine la séquence des bannières. Les bannières avec des numéros inférieurs apparaissent en premier.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|
| Configuration du module | Activer le slider plein écran | OUI | Active/désactive la fonctionnalité complète du slider. |
| Configuration du module | Largeur du slider | 100% | Définit la largeur du slider (par exemple, 100% pour la pleine largeur). |
| Configuration du module | Hauteur du slider | 100% | Définit la hauteur du slider (par exemple, 100% pour la pleine hauteur). |
| Configuration du module | Type d'animation | (Divers) | Choisit l'effet de transition visuel entre les diapositives. |
| Configuration du module | Vitesse d'animation (ms) | 800 | Contrôle la vitesse des transitions de diapositives. |
| Configuration du module | Intervalle entre les diapositives (ms) | 3000 | Définit la durée d'affichage de chaque bannière. |
| Configuration du module | Afficher les flèches de navigation | OUI | Affiche/masque les flèches pour la navigation manuelle des diapositives. |
| Configuration du module | Afficher les points de pagination | OUI | Affiche/masque les points/vignettes pour l'accès direct aux diapositives. |
| Configuration du module | Lecture automatique du slider | OUI | Active/désactive la progression automatique des diapositives. |
| Configuration du module | Texte du bouton de fermeture | Fermer | Personnalise le texte sur le bouton de fermeture du slider. |
| Configuration du module | Expiration du cookie (jours) | 7 | Détermine combien de temps un utilisateur ne verra pas le slider après l'avoir fermé. |
| Configuration du module | Image de la bannière | (Télécharger) | Télécharge l'image pour une diapositive individuelle. |
| Configuration du module | Lien de la bannière (URL) | (Vide) | Définit l'URL de destination lorsqu'une bannière est cliquée. |
| Configuration du module | Ordre d'affichage | (Nombre) | Définit la séquence dans laquelle les bannières apparaissent. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le slider n'apparaît pas sur ma boutique. Que dois-je faire ?**
R :

1.  **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que "Fullscreen Banner Slider" est installé et activé.
2.  **Configuration :** Vérifiez que "Activer le slider plein écran" est réglé sur OUI dans la configuration du module.
3.  **Expiration du cookie :** Si vous avez déjà vu le slider, cela peut être dû au cookie. Essayez de vider les cookies de votre navigateur ou d'ouvrir votre boutique dans une fenêtre de navigation privée/incognito pour simuler un premier visiteur.
4.  **Cache :** Videz le cache de votre PrestaShop sous **Paramètres avancés > Performances**. Videz également le cache de votre navigateur.
5.  **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, les thèmes personnalisés peuvent parfois interférer. Basculez temporairement vers le thème PrestaShop par défaut pour voir si le slider apparaît. Si c'est le cas, votre thème pourrait nécessiter un petit ajustement (contactez le développeur de votre thème ou un webmaster).

**Q : Mes images de bannière semblent floues ou étirées. Comment puis-je résoudre ce problème ?**
R : Cela se produit généralement si vos images téléchargées ne sont pas d'une résolution suffisamment élevée ou ont des rapports d'aspect incorrects pour un affichage plein écran.

1.  **Qualité de l'image :** Utilisez toujours des images haute résolution.
2.  **Rapport d'aspect :** Bien que le module s'adapte, essayez d'utiliser des images larges et relativement courtes, adaptées à une bannière plein écran (par exemple, 1920x1080 pixels ou des formats larges similaires). Évitez les images très hautes ou étroites.
3.  **Optimisation :** Assurez-vous que vos images sont optimisées pour le web (compressées) afin d'éviter des temps de chargement lents, même si elles sont en haute résolution.

**Q : Puis-je avoir différents sliders pour différentes pages ou groupes de clients ?**
R : Cette version spécifique du module Fullscreen Banner Slider est conçue pour un affichage unique, à l'échelle du site, qui apparaît une fois par session/cookie de visiteur. Elle n'offre pas d'options de ciblage avancées pour des pages ou des groupes de clients spécifiques. Si vous avez besoin d'une telle fonctionnalité, vous pourriez avoir besoin d'un module de gestion de bannières plus avancé ou d'un développement personnalisé.

**Q : Comment traduire le texte du bouton "Fermer" dans d'autres langues ?**
R :

1.  Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2.  Sélectionnez "Traductions des modules installés" comme Type de traduction.
3.  Choisissez votre thème.
4.  Sélectionnez la langue que vous souhaitez traduire.
5.  Recherchez le module "Fullscreen Banner Slider" dans la liste. Vous devriez y trouver le champ "Texte du bouton de fermeture" à traduire. Enregistrez vos modifications.

**Q : Le slider apparaît, mais les animations ne fonctionnent pas ou la mise en page est incorrecte.**
R :

1.  **Conflits JavaScript :** Cela est souvent dû à des conflits avec le JavaScript d'autres modules ou le JavaScript de votre thème. Vérifiez la console de développement de votre navigateur (touche F12) pour toute erreur JavaScript.
2.  **Conflits CSS :** Similaire au JS, le CSS de votre thème pourrait annuler les styles du module.
3.  **Réinstallation du module :** Parfois, une nouvelle réinstallation peut résoudre des problèmes inattendus. Désinstallez le module (sans supprimer les données si vous y êtes invité), puis réinstallez-le.
    Si les erreurs persistent, consultez un webmaster ou contactez le support MyPresta.eu avec les détails de la console de développement de votre navigateur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Fullscreen Banner Slider (`fullscreenslider`) est un module PrestaShop standard principalement implémenté dans son fichier PHP principal, `ajax_fullscreenslider.php`. Il utilise la classe `Module` de PrestaShop pour l'installation, la désinstallation et la configuration (`getContent()`). L'affichage en front-office est géré en s'accrochant à `displayHeader` et en rendant un template Smarty. La fonctionnalité du slider elle-même repose sur des plugins jQuery externes (`jquery.skitter.js`, `jquery.easing.1.3.js`) pour les animations et `noconflict.js` pour assurer la compatibilité jQuery. Les valeurs de configuration sont stockées dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office dédiés. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou instance d'`ObjectModel` dans le répertoire `classes/`. Toutes les données (images de bannière, liens, ordre) sont gérées directement via les paramètres de configuration du module, généralement sérialisées et stockées dans `ps_configuration`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript, principalement pour la fonctionnalité principale et les animations du slider. Ceux-ci sont généralement chargés en front-office.

-   `fullscreenslider/js/jquery.easing.1.3.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Fournit des fonctions d'assouplissement supplémentaires pour les animations jQuery, permettant des effets de transition plus diversifiés et fluides au-delà des options linéaires ou swing par défaut. C'est une dépendance pour `jquery.skitter.js`.
-   `fullscreenslider/js/jquery.skitter.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** C'est le plugin jQuery principal responsable de la fonctionnalité du slider. Il gère le chargement des images, les transitions d'animation, la navigation (flèches, pagination), la lecture automatique et la liaison d'événements pour l'interaction utilisateur. Il initialise le slider en fonction des paramètres de configuration passés par le module.
-   `fullscreenslider/js/noconflict.js`
    -   **Portée :** Front-office.
    -   **Responsabilité :** Ce script est crucial pour assurer la compatibilité lorsque plusieurs bibliothèques JavaScript (en particulier différentes versions de jQuery) sont chargées sur la même page. Il enveloppe généralement le code jQuery dans une expression de fonction immédiatement invoquée (IIFE) qui passe `jQuery` comme argument, lui permettant d'être aliasé en `$` localement sans entrer en conflit avec d'autres bibliothèques qui pourraient également utiliser `$`.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut un fichier CSS principal pour styliser le slider.

-   `fullscreenslider/css/skitter.styles.css`
    -   **Portée :** Style client en front-office.
    -   **Responsabilité :** Contient toutes les règles CSS nécessaires pour styliser le slider plein écran, y compris son conteneur, les flèches de navigation, les points de pagination et les effets visuels du type d'animation choisi. Il définit l'apparence par défaut du slider.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :**
        -   `.box_skitter` (conteneur principal du slider)
        -   `.box_skitter ul` (liste des diapositives)
        -   `.box_skitter ul li` (diapositive individuelle)
        -   `.box_skitter .info_slide` (légendes/informations de la diapositive, si utilisées)
        -   `.box_skitter .prev_button`, `.box_skitter .next_button` (flèches de navigation)
        -   `.box_skitter .info_slide_dots`, `.box_skitter .info_slide_thumb` (éléments de pagination)
        -   Classes spécifiques pour les types d'animation (par exemple, `.cube`, `.fade`, etc.)

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates Smarty pour rendre son contenu en front-office.

-   **Templates de hook (`views/templates/hook/`)** :

    -   `fullscreenslider/header.tpl`
        -   **Hook :** `displayHeader` (ou similaire, selon l'implémentation de la méthode `hook` du module).
        -   **Objectif :** Ce template est probablement responsable de l'injection des fichiers CSS et JavaScript nécessaires dans la section `<head>` du HTML, et potentiellement de la structure HTML initiale du conteneur du slider, qui sera ensuite remplie et animée par le JavaScript. Il pourrait également contenir la logique pour vérifier le cookie qui détermine si le slider doit être affiché.
    -   `fullscreenslider/top.tpl`
        -   **Hook :** Ce template est probablement rendu dans le hook `displayTop` ou directement inclus par `header.tpl` pour afficher la structure HTML principale du slider plein écran lui-même.
        -   **Objectif :** Il contient les éléments `div` et la structure `ul/li` que `jquery.skitter.js` s'attend à trouver pour initialiser le slider. Il itère sur les bannières configurées, affichant chaque image avec son lien associé. Il inclut également le HTML pour le bouton de fermeture.
-   **Templates d'administration (`views/templates/admin/`)** : Ce module ne semble pas utiliser de templates d'administration dédiés, car la configuration est gérée directement dans `getContent()`.
-   **Templates front-office (`views/templates/front/`)** : Ce module ne semble pas utiliser de templates de page front-office autonomes dédiés.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne crée pas de tables SQL personnalisées.
    -   Les paramètres de configuration (y compris les données sérialisées pour les bannières comme les chemins d'image, les liens et l'ordre) sont stockés dans la table `ps_configuration`. Les clés suivent généralement le modèle `FULLSCREENSLIDER_SETTING_NAME`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS et JavaScript du module, et potentiellement la structure HTML initiale du slider, ainsi que la logique de vérification des cookies. |
| `displayTop` (ou similaire) | Exécuté dans la section supérieure de la page du front-office, souvent juste en dessous de l'en-tête. | Rend la structure HTML principale du slider plein écran, y compris les images de bannière et les éléments de navigation. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Fullscreen Banner Slider, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec toute question ou problème concernant la fonctionnalité et la compatibilité du module.
