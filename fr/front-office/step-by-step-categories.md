---
title: "Pas à pas - catégories - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pas à pas - catégories par MyPresta.eu."
sidebar:
  label: "Pas à pas - catégories - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Step by step - categories sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/step-by-step-categories/)
>
> ---


# Pas à pas - catégories

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence de serveur particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à l'écran de configuration principal pour « Pas à pas - catégories ». C'est ici que vous contrôlez le comportement et l'apparence du module sur votre boutique.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple marchand |
| --- | --- | --- | --- | --- |
| **Afficher le bloc dans l'en-tête** | Contrôle si la navigation par catégorie pas à pas apparaît dans la section d'en-tête de votre boutique. | *Lorsque activé :* Les listes déroulantes de catégories seront visibles en haut de votre site web, souvent près du logo ou de la navigation principale. Cela offre un accès immédiat au filtrage par catégorie. *Lorsque désactivé :* Le bloc n'apparaîtra pas dans l'en-tête. | **OUI** (si vous souhaitez une navigation proéminente) | Vous voulez que les clients trouvent facilement des produits depuis n'importe quelle page, donc le placer dans l'en-tête le rend toujours accessible. |
| **Afficher le bloc dans la colonne de gauche** | Contrôle si la navigation par catégorie pas à pas apparaît dans la barre latérale gauche de votre boutique. | *Lorsque activé :* Les listes déroulantes de catégories seront visibles dans la colonne de gauche de votre site web (si votre thème prend en charge une colonne de gauche). C'est un placement traditionnel pour les filtres de catégorie. *Lorsque désactivé :* Le bloc n'apparaîtra pas dans la colonne de gauche. | **OUI** (si votre thème a une colonne de gauche et que vous souhaitez une navigation latérale) | Votre thème a une barre latérale gauche, et vous préférez y organiser les éléments de navigation, de manière similaire à une arborescence de catégories standard. |
| **Afficher le bloc dans la colonne de droite** | Contrôle si la navigation par catégorie pas à pas apparaît dans la barre latérale droite de votre boutique. | *Lorsque activé :* Les listes déroulantes de catégories seront visibles dans la colonne de droite de votre site web (si votre thème prend en charge une colonne de droite). *Lorsque désactivé :* Le bloc n'apparaîtra pas dans la colonne de droite. | **NON** (sauf si votre thème utilise spécifiquement une colonne de droite pour la navigation) | Votre thème utilise la colonne de droite pour des informations supplémentaires, et vous souhaitez y placer la navigation par catégorie au lieu de la gauche. |
| **Afficher le bloc dans le pied de page** | Contrôle si la navigation par catégorie pas à pas apparaît dans la section de pied de page de votre boutique. | *Lorsque activé :* Les listes déroulantes de catégories seront visibles en bas de votre site web. C'est moins courant pour la navigation principale, mais peut être utile pour un accès secondaire. *Lorsque désactivé :* Le bloc n'apparaîtra pas dans le pied de page. | **NON** (sauf pour des raisons de conception spécifiques) | Vous avez un en-tête et des colonnes très minimalistes, et vous souhaitez offrir une navigation par catégorie dans le pied de page comme alternative pour les utilisateurs qui défilent vers le bas. |
| **Afficher le bloc sur la page produit** | Contrôle si la navigation par catégorie pas à pas apparaît sur les pages de produits individuelles. | *Lorsque activé :* Les listes déroulantes de catégories seront visibles sur les pages de détails des produits. Cela peut aider les clients à explorer d'autres catégories ou produits connexes. *Lorsque désactivé :* Le bloc n'apparaîtra pas sur les pages de produits. | **NON** (sauf si vous en avez un besoin spécifique ici) | Vous souhaitez encourager les clients qui consultent un produit à passer facilement à d'autres catégories sans quitter la page produit, peut-être pour comparer des articles. |
| **Afficher le bouton « Aller »** | Détermine si un bouton « Aller » ou « Rechercher » est affiché à côté de la dernière liste déroulante de catégories. | *Lorsque activé :* Un bouton apparaîtra. Les clients doivent cliquer sur ce bouton pour être redirigés vers la page de la catégorie sélectionnée. *Lorsque désactivé :* Les clients sont automatiquement redirigés vers la page de la catégorie sélectionnée dès qu'ils effectuent la sélection finale dans la dernière liste déroulante. | **OUI** (pour plus de contrôle) | Vous voulez que les clients confirment leur sélection de catégorie avant d'être redirigés, leur donnant une chance de revoir leur choix. |
| **Nombre de listes déroulantes** | Définit le nombre maximum de niveaux de catégories (profondeur) qui seront affichés sous forme de listes déroulantes. | *Lorsque défini sur 1 :* Seules les catégories de niveau supérieur apparaîtront dans une seule liste déroulante. *Lorsque défini sur 3 :* Jusqu'à trois niveaux de catégories (par exemple, Catégorie principale > Sous-catégorie 1 > Sous-catégorie 2) seront affichés dans des listes déroulantes séparées. | **3** (ou en fonction de la profondeur de vos catégories) | Votre boutique a des catégories imbriquées jusqu'à 3 ou 4 niveaux de profondeur, et vous voulez que les clients puissent descendre efficacement. |
| **Catégorie racine** | Spécifie le point de départ de la navigation par catégorie. Seules les catégories au sein de cette racine seront affichées. | *Lorsque défini sur « Accueil » :* Toutes les catégories à partir du tout début de votre catalogue seront disponibles. *Lorsque défini sur « Électronique » :* Seules les catégories sous « Électronique » (par exemple, « Ordinateurs portables », « Smartphones ») seront affichées dans les listes déroulantes. | **Accueil** (sauf si vous souhaitez restreindre la navigation) | Vous ne souhaitez offrir une navigation pas à pas que pour une partie spécifique de votre catalogue, comme « Vêtements », et exclure d'autres sections comme « Maison et Jardin ». |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher le bloc dans l'en-tête | OUI | Affiche les listes déroulantes de catégories dans l'en-tête de la boutique pour une navigation proéminente. |
| Configuration du module | Afficher le bloc dans la colonne de gauche | OUI | Affiche les listes déroulantes de catégories dans la barre latérale gauche pour une navigation traditionnelle. |
| Configuration du module | Afficher le bloc dans la colonne de droite | NON | Affiche les listes déroulantes de catégories dans la barre latérale droite. |
| Configuration du module | Afficher le bloc dans le pied de page | NON | Affiche les listes déroulantes de catégories dans le pied de page de la boutique. |
| Configuration du module | Afficher le bloc sur la page produit | NON | Affiche les listes déroulantes de catégories sur les pages de détails des produits. |
| Configuration du module | Afficher le bouton « Aller » | OUI | Demande aux clients de cliquer sur un bouton pour naviguer vers la catégorie sélectionnée. |
| Configuration du module | Nombre de listes déroulantes | 3 | Définit la profondeur maximale des niveaux de catégories affichés. |
| Configuration du module | Catégorie racine | Accueil | Définit le point de départ de la navigation par catégorie. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Le module est installé, mais je ne vois pas les listes déroulantes sur ma boutique.**
R1 :

- **Vérifier la configuration :** Allez dans **Modules > Gestionnaire de modules > Pas à pas - catégories > Configurer**. Assurez-vous qu'au moins une option « Afficher le bloc dans... » (par exemple, « Afficher le bloc dans l'en-tête », « Afficher le bloc dans la colonne de gauche ») est définie sur **OUI**.
- **Vider le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).
- **Compatibilité du thème :** Certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si vider le cache ne résout pas le problème, essayez de passer temporairement au thème PrestaShop par défaut pour voir si le module apparaît. Si c'est le cas, votre thème pourrait remplacer les positions de hook standard.

**Q2 : Les listes déroulantes apparaissent, mais elles ne se mettent pas à jour lorsque je sélectionne une catégorie.**
R2 :

- **Problèmes AJAX :** Cela indique généralement une erreur JavaScript. Ouvrez la console de développement de votre navigateur (F12) et vérifiez s'il y a des erreurs dans l'onglet « Console ».
- **JavaScript en conflit :** Un autre module ou le JavaScript de votre thème pourrait interférer. Essayez de désactiver d'autres modules front-office un par un pour identifier les conflits.
- **Fichiers du module :** Assurez-vous que tous les fichiers du module ont été téléchargés correctement et ne sont pas corrompus. Re-télécharger le module pourrait résoudre ce problème.

**Q3 : Comment modifier le style (couleurs, polices, taille) des listes déroulantes ?**
R3 :

- Le module utilise du CSS standard. Vous aurez besoin de connaissances CSS de base ou d'un webmaster.
- Les fichiers CSS du module (par exemple, `sbs-block.css`, `sbs-header.css`) définissent les styles par défaut.
- **Meilleure pratique :** NE MODIFIEZ PAS directement les fichiers CSS du module, car vos modifications seront perdues lors des mises à jour. Utilisez plutôt le fichier CSS personnalisé de votre thème (souvent trouvé dans `themes/votreetheme/assets/css/custom.css` ou similaire) pour remplacer les styles du module. Utilisez l'inspecteur de votre navigateur (F12) pour identifier les classes CSS utilisées par les listes déroulantes.

**Q4 : Mes catégories sont très profondes, mais je ne vois que quelques listes déroulantes.**
R4 :

- **Paramètre « Nombre de listes déroulantes » :** Allez dans **Modules > Gestionnaire de modules > Pas à pas - catégories > Configurer** et ajustez le paramètre « Nombre de listes déroulantes ». Augmentez cette valeur pour qu'elle corresponde à la profondeur maximale des catégories que vous souhaitez afficher. N'oubliez pas qu'afficher trop de listes déroulantes pourrait encombrer l'interface.

**Q5 : Le module affiche des catégories que je ne veux pas inclure dans la navigation pas à pas.**
R5 :

- **Paramètre « Catégorie racine » :** Dans la configuration du module, utilisez le paramètre « Catégorie racine ». Sélectionnez une catégorie parente spécifique à partir de laquelle vous souhaitez que la navigation pas à pas commence. Seules les catégories et sous-catégories sous la racine choisie seront affichées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Pas à pas - catégories » est principalement une fonctionnalité front-office tirant parti de l'architecture des modules de PrestaShop. Il utilise une classe `Module` standard pour l'installation et la configuration, et des classes `ModuleFrontController` pour gérer les requêtes AJAX de chargement dynamique des catégories. Il n'introduit pas de classes `ObjectModel` personnalisées ni de tables de base de données, s'appuyant sur l'objet `Category` natif de PrestaShop pour les données. Le module utilise fortement les templates Smarty pour le rendu et JavaScript pour la fonctionnalité AJAX interactive.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :
  - `controllers/front/ajaxload.php`
    - Nom de la classe : `StepbystepAjaxloadModuleFrontController`
    - Classe parente : `ModuleFrontController`
    - Responsabilité : Ce contrôleur est le cœur de la fonctionnalité AJAX. Il répond aux requêtes du JavaScript front-office pour récupérer les sous-catégories en fonction d'un ID de catégorie parente. Il renvoie généralement des données JSON contenant les noms et ID des catégories pour peupler les listes déroulantes suivantes.
  - `controllers/front/index.php`
    - Nom de la classe : `StepbystepIndexModuleFrontController`
    - Classe parente : `ModuleFrontController`
    - Responsabilité : Ce contrôleur sert probablement de point d'entrée par défaut ou de repli pour le routage front-office du module, bien que sa fonction principale puisse être minimale étant donné la nature pilotée par AJAX. Il pourrait gérer la logique d'affichage initiale ou la redirection si le module devait avoir une page dédiée.
  - `controllers/front/tree.php`
    - Nom de la classe : `StepbystepTreeModuleFrontController`
    - Classe parente : `ModuleFrontController`
    - Responsabilité : Ce contrôleur pourrait être responsable du rendu d'une structure d'arborescence de catégories complète, potentiellement pour le débogage ou une méthode d'affichage alternative, bien que la fonctionnalité principale du module soit les listes déroulantes. Il pourrait également être utilisé pour générer les données initiales de la première liste déroulante.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne contient aucune classe personnalisée dans le répertoire `classes/`. Il utilise directement la classe `Category` de PrestaShop et d'autres fonctions d'aide pour récupérer les données de catégorie.

### 4.4 Actifs JavaScript (`views/js/`)

- `stepbystep/js/advajax.js`
  - Portée : Front-office
  - C'est le fichier JavaScript principal responsable du comportement interactif du module.
  - Il lie les écouteurs d'événements aux éléments `<select>` des listes déroulantes de catégories.
  - Lorsqu'une sélection est effectuée dans une liste déroulante, il déclenche une requête AJAX (probablement vers `ajaxload.php`) pour récupérer le niveau suivant de sous-catégories.
  - Il crée et peuple dynamiquement les listes déroulantes suivantes avec les données reçues.
  - Il gère la redirection vers la page de catégorie finale lorsqu'une sélection est effectuée ou que le bouton « Aller » est cliqué.
  - Il gère la visibilité et l'état des listes déroulantes en fonction de l'interaction de l'utilisateur et de la configuration du module (par exemple, « Nombre de listes déroulantes »).

### 4.5 Feuilles de style CSS (`views/css/`)

- `stepbystep/css/sbs-block.css`
  - Portée : Style client Front-office
  - Style l'apparence générale du bloc de catégories pas à pas, y compris le rembourrage, les marges et la mise en page globale lorsqu'il est placé dans des colonnes ou d'autres positions de type bloc.
  - Sélecteurs clés : `.sbs-block`, `.sbs-category-select-wrapper`
- `stepbystep/css/sbs-header.css`
  - Portée : Style client Front-office
  - Style spécifiquement le module lorsqu'il est accroché à la position `displayHeader`, en l'ajustant potentiellement pour les mises en page d'en-tête (par exemple, affichage en ligne, largeurs spécifiques).
  - Sélecteurs clés : `.sbs-header-container`
- `stepbystep/css/sbs-top.css`
  - Portée : Style client Front-office
  - Style probablement le module lorsqu'il est accroché à `displayTop` ou à des positions similaires en haut de page, similaire à `sbs-header.css` mais pour des contextes visuels différents.
  - Sélecteurs clés : `.sbs-top-container`
- `stepbystep/css.css`
  - Portée : Style client Front-office
  - Une feuille de style générale qui pourrait contenir des styles communs applicables à tous les emplacements ou des styles de secours.
  - Sélecteurs clés : `.sbs-select`, `.sbs-go-button`

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :

  - `block.tpl` : Ce template est probablement utilisé lorsque le module est accroché à `displayLeftColumn` ou `displayRightColumn`. Il rend les listes déroulantes pas à pas dans une structure de bloc PrestaShop standard.
  - `blockSbs.tpl` : Il pourrait s'agir d'un template de bloc alternatif ou plus générique, potentiellement utilisé pour d'autres hooks de colonne ou des placements personnalisés spécifiques.
  - `displaySearch.tpl` : Ce template pourrait être destiné à l'intégration près d'une barre de recherche ou dans le cadre d'un hook lié à la recherche, fournissant les listes déroulantes comme outil d'affinage de la recherche.
  - `header.tpl` : Ce template est utilisé lorsque le module est accroché à `displayHeader`. Il rend les listes déroulantes dans la section d'en-tête de la boutique.
  - `top.tpl` : Ce template est utilisé lorsque le module est accroché à `displayTop`. Similaire à `header.tpl`, mais pour le hook `displayTop`, qui est souvent utilisé pour la barre de navigation principale.
- **Templates d'administration (`views/templates/admin/`)** : Aucun identifié. La configuration est gérée directement dans `getContent()`.
- **Templates Front-office (`views/templates/front/`)** : Aucun identifié comme pages autonomes.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Le module ne crée aucune table SQL personnalisée. Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop en utilisant des clés comme `STEPMYSTEP_HEADER`, `STEPMYSTEP_LEFT`, `STEPMYSTEP_RIGHT`, `STEPMYSTEP_FOOTER`, `STEPMYSTEP_PRODUCT`, `STEPMYSTEP_GO_BUTTON`, `STEPMYSTEP_DROPDOWNS`, `STEPMYSTEP_ROOT_CATEGORY`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` du HTML, ou tout en haut du `<body>` avant tout autre contenu. | Injecte les actifs CSS/JS et potentiellement la structure HTML du module si configuré pour l'affichage dans l'en-tête. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche de la boutique. | Affiche les listes déroulantes de catégories pas à pas dans la colonne de gauche. |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite de la boutique. | Affiche les listes déroulantes de catégories pas à pas dans la colonne de droite. |
| `displayFooter` | Rend le contenu dans la section de pied de page de la boutique. | Affiche les listes déroulantes de catégories pas à pas dans le pied de page. |
| `displayProductAdditionalInfo` (ou hook de page produit similaire) | Rend le contenu sur la page produit, souvent sous la description du produit ou dans un bloc spécifique. | Affiche les listes déroulantes de catégories pas à pas sur les pages produit. |
| `displayTop` | Rend le contenu dans la section supérieure de la page, généralement au-dessus ou dans la navigation principale. | Affiche les listes déroulantes de catégories pas à pas dans la barre supérieure. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Pas à pas - catégories », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
