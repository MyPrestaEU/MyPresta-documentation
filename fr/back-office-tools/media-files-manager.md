---
title: "Gestionnaire de médias / fichiers - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Gestionnaire de médias / fichiers par MyPresta.eu."
sidebar:
  label: "Gestionnaire de médias / fichiers - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Media / Files Manager sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/media-files-manager.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/media-files-manager/)
>
> ---


# Gestionnaire de médias / fichiers

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Le module nécessite des permissions d'écriture sur les répertoires qu'il gère, ce qui est standard pour les installations PrestaShop.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, vous serez dirigé vers la page de configuration du module. Cette page sert principalement à intégrer le gestionnaire de fichiers dans votre back office PrestaShop et à gérer ses paramètres principaux.

L'écran de configuration principal affichera directement l'interface du gestionnaire de fichiers. Cette interface est un explorateur de fichiers complet, similaire à ce que vous verriez sur votre ordinateur, mais opérant sur les fichiers de votre serveur.

**Zones clés et fonctionnalités de l'interface du gestionnaire de fichiers :**

1.  **Panneau de navigation (Barre latérale gauche) :**

    *   **Ce que cela fait :** Affiche une structure arborescente des répertoires de votre serveur, commençant généralement par le dossier racine de votre PrestaShop. Vous pouvez cliquer sur les dossiers pour naviguer à travers eux.
    *   **Effet de l'utilisation :** Vous permet de passer rapidement d'une partie à l'autre de votre installation PrestaShop (par exemple, `img/p` pour les images de produits, `themes/yourtheme/css` pour les feuilles de style).
    *   **Valeur recommandée :** Utilisez-le pour naviguer vers le dossier spécifique où vous souhaitez gérer les fichiers.
2.  **Zone de liste des fichiers (Panneau principal) :**

    *   **Ce que cela fait :** Affiche le contenu (fichiers et sous-dossiers) du dossier actuellement sélectionné. Vous verrez les noms de fichiers, les tailles, les types et les dates de modification.
    *   **Effet de l'utilisation :** C'est ici que vous effectuerez la plupart de vos opérations sur les fichiers.
    *   **Valeur recommandée :** Familiarisez-vous avec les icônes et les informations présentées pour chaque fichier.
3.  **Barre d'outils (Haut de la zone de liste des fichiers) :**

    *   **Ce que cela fait :** Contient divers boutons et outils pour les opérations sur les fichiers. Les outils courants incluent :
        *   **Télécharger :** Téléchargez des fichiers de votre ordinateur vers le dossier serveur actuel.
        *   **Nouveau dossier :** Créez un nouveau répertoire.
        *   **Nouveau fichier :** Créez un nouveau fichier vide (par exemple, un fichier `.txt`, `.html` ou `.css`).
        *   **Copier, Couper, Coller :** Manipulation standard des fichiers.
        *   **Renommer :** Changez le nom d'un fichier ou d'un dossier.
        *   **Supprimer :** Supprimez des fichiers ou des dossiers (à utiliser avec une extrême prudence !).
        *   **Modifier :** Ouvrez un éditeur de texte pour les fichiers texte sélectionnés (par exemple, `.php`, `.css`, `.js`, `.html`).
        *   **Aperçu :** Affichez directement des images ou d'autres types de fichiers pris en charge.
        *   **Rechercher :** Trouvez des fichiers dans le répertoire actuel ou de manière récursive.
        *   **Options d'affichage :** Changez la façon dont les fichiers sont affichés (liste, icônes, etc.).
    *   **Effet de l'utilisation de ces outils :** Manipule directement les fichiers et dossiers sur votre serveur.
    *   **Valeur recommandée :** Vérifiez toujours vos sélections avant d'effectuer des actions comme « Supprimer » ou « Renommer ».
4.  **Menu contextuel (Clic droit) :**

    *   **Ce que cela fait :** Un clic droit sur un fichier ou un dossier affiche souvent un menu contextuel avec un accès rapide aux opérations courantes comme « Ouvrir », « Modifier », « Renommer », « Supprimer », « Télécharger », « Obtenir des informations », etc.
    *   **Effet de l'utilisation :** Offre un moyen plus rapide d'effectuer des actions sur des éléments individuels.
    *   **Valeur recommandée :** Explorez les options du clic droit pour différents types de fichiers.

**Paramètres spécifiques (le cas échéant, basés sur `mypresta_updates`, `update_`, `updatev_`) :**

La méthode `getContent()` du module affiche principalement l'interface du gestionnaire de fichiers elle-même. Les clés de configuration `mypresta_updates`, `update_` et `updatev_` sont des clés internes standard utilisées par les modules MyPresta.eu pour gérer les notifications de mise à jour et les vérifications de version. Ce ne sont pas des paramètres avec lesquels vous interagissez directement en tant que marchand.

-   **Ce que font ces paramètres :** Ce sont des indicateurs internes qui aident le module à communiquer avec le serveur de mise à jour de MyPresta.eu pour vérifier les nouvelles versions et afficher des notifications dans votre back office PrestaShop si une mise à jour est disponible.
-   **Effet de la modification de ces paramètres :** Vous ne pouvez pas les modifier directement. Ils sont gérés automatiquement par le module. S'ils devaient être modifiés manuellement (ce qui n'est pas recommandé), cela pourrait affecter la capacité du module à vous informer des nouvelles versions.
-   **Valeur recommandée :** Laissez-les tels quels. Ils sont destinés à la gestion interne du module.
-   **Scénario / exemple pour le marchand :** Vous n'avez pas à vous en soucier. Le module vous informera automatiquement si une nouvelle version est publiée, vous invitant à la télécharger et à l'installer depuis votre compte MyPresta.eu.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module n'introduit aucun écran d'administration dédié supplémentaire ni de contrôleurs personnalisés au-delà de sa page de configuration principale. L'intégralité de la fonctionnalité de gestion de fichiers est intégrée directement dans l'interface de configuration du module.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue              | Paramètre / Option                                | Défaut / Recommandé | Objectif et impact                                                              |
| :----------------------- | :------------------------------------------------ | :------------------ | :------------------------------------------------------------------------------ |
| Page de configuration du module | **Panneau de navigation**                         | N/A                 | Parcourir les répertoires du serveur.                                           |
| Page de configuration du module | **Zone de liste des fichiers**                    | N/A                 | Afficher et interagir avec les fichiers/dossiers.                               |
| Page de configuration du module | **Barre d'outils (Télécharger, Nouveau dossier, Modifier, Supprimer, etc.)** | N/A                 | Effectuer des opérations sur les fichiers (télécharger, créer, modifier, supprimer). |
| Page de configuration du module | **Menu contextuel (Clic droit)**                  | N/A                 | Accès rapide aux opérations sur les fichiers.                                   |
| Page de configuration du module | `mypresta_updates`                                | Interne             | Indicateur interne pour les notifications de mise à jour.                       |
| Page de configuration du module | `update_`                                         | Interne             | Indicateur interne pour les notifications de mise à jour.                       |
| Page de configuration du module | `updatev_`                                        | Interne             | Indicateur interne pour les notifications de mise à jour.                       |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai téléchargé une image, mais elle n'apparaît pas sur ma page produit.**
R :

-   **Vérifiez le chemin :** Assurez-vous d'avoir téléchargé l'image dans le répertoire correct attendu par PrestaShop (généralement `img/p/` suivi de sous-dossiers).
-   **Videz le cache :** Parfois, le cache de PrestaShop (ou le cache de votre navigateur) peut empêcher les nouvelles images de s'afficher immédiatement. Allez dans **Paramètres avancés > Performances** dans votre back office et cliquez sur « Vider le cache ». Essayez également de vider le cache de votre navigateur.
-   **Permissions :** Assurez-vous que le dossier où vous avez téléchargé l'image a les bonnes permissions d'écriture (généralement 755 ou 775). Bien que le module gère généralement cela, les configurations de serveur peuvent parfois être strictes.

**Q : J'ai modifié un fichier CSS, mais le design de ma boutique n'a pas changé.**
R :

-   **Videz le cache :** C'est la raison la plus courante. Allez dans **Paramètres avancés > Performances** et videz le cache de PrestaShop. Videz également le cache de votre navigateur (Ctrl+F5 ou Cmd+R force généralement un rafraîchissement complet).
-   **Fichier correct :** Vérifiez que vous avez modifié le bon fichier CSS que votre thème charge réellement. Certains thèmes utilisent du CSS compilé ou plusieurs feuilles de style.
-   **Erreurs de syntaxe :** Si vous avez introduit une erreur de syntaxe dans votre CSS, cela pourrait empêcher la feuille de style de se charger correctement. Utilisez les outils de développement de votre navigateur (F12) pour vérifier les erreurs CSS.

**Q : J'ai accidentellement supprimé un fichier/dossier. Puis-je le récupérer ?**
R :

-   **Restaurez immédiatement à partir d'une sauvegarde :** C'est pourquoi les sauvegardes régulières sont cruciales. Si vous avez une sauvegarde récente des fichiers de votre serveur, restaurez l'élément supprimé à partir de celle-ci.
-   **Contactez votre hébergeur :** Certains hébergeurs conservent des sauvegardes quotidiennes et pourraient être en mesure de restaurer des fichiers individuels pour vous.
-   **Attention :** Le module lui-même n'a pas de fonction « corbeille » ou « annuler ». La suppression est permanente.

**Q : Le gestionnaire de fichiers semble cassé ou ne se charge pas correctement.**
R :

-   **Vérifiez la console du navigateur :** Ouvrez les outils de développement de votre navigateur (F12) et recherchez les erreurs dans l'onglet « Console ». Cela peut indiquer des conflits JavaScript ou des problèmes côté serveur.
-   **Conflits de modules :** Essayez de désactiver d'autres modules récemment installés pour voir s'il y a un conflit.
-   **Journaux d'erreurs du serveur :** Vérifiez les journaux d'erreurs PHP de votre serveur pour toute erreur connexe.
-   **Permissions :** Assurez-vous que les propres fichiers et dossiers du module ont les bonnes permissions de lecture/écriture.

**Q : Puis-je restreindre l'accès à certains dossiers pour différents utilisateurs administrateurs ?**
R :

-   Ce module, dans sa version actuelle, fournit une interface de gestion de fichiers unique et à accès complet. Le système de permissions natif de PrestaShop pour les modules accorde généralement un accès complet ou aucun accès à la configuration du module. Les permissions granulaires au niveau des dossiers pour différents utilisateurs du back office ne sont pas une fonctionnalité intégrée de ce module spécifique. Vous auriez besoin d'un développement personnalisé pour implémenter une telle fonctionnalité.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Gestionnaire de médias / fichiers » (`fmpro`) est construit autour du populaire gestionnaire de fichiers open-source **elFinder**. Il intègre elFinder directement dans le back office de PrestaShop, principalement via la méthode `getContent()` du module. Cela signifie que la logique de gestion de fichiers et l'interface utilisateur sont gérées par le robuste backend JavaScript et PHP d'elFinder, le module PrestaShop agissant comme un wrapper et un point d'entrée.

Le module lui-même est un module PrestaShop standard, étendant `Module`. Il n'introduit pas de tables de base de données personnalisées (au-delà de `ps_configuration` pour ses propres paramètres internes) ou de structures `ObjectModel` complexes. Sa fonction principale est d'instancier et de configurer la bibliothèque elFinder dans le contexte d'administration de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office personnalisés au sens traditionnel de PrestaShop (c'est-à-dire des fichiers dans `controllers/front/` ou `controllers/admin/`).
La bibliothèque elFinder elle-même possède son propre connecteur backend (généralement un script PHP) qui gère les opérations sur les fichiers. Ce connecteur est probablement intégré ou appelé directement depuis le fichier principal du module `fmpro.php` ou un script PHP séparé dans le répertoire `fmpro/php/`, agissant comme le gestionnaire côté serveur pour les requêtes AJAX d'elFinder.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe ou modèle personnalisé dans un répertoire `classes/`. La logique principale de gestion des fichiers est gérée par la bibliothèque elFinder intégrée.

### 4.4 Actifs JavaScript (`views/js/`)

Le module s'appuie fortement sur JavaScript pour son interface front-end, principalement la bibliothèque elFinder. Tous les fichiers JS sont situés dans `fmpro/js/`.

-   `fmpro/js/elfinder.full.js` : Il s'agit du fichier principal de la bibliothèque elFinder, contenant toutes les fonctionnalités de base pour l'interface utilisateur du gestionnaire de fichiers, les interactions et la communication AJAX avec le backend. C'est un script complet qui alimente toute l'interface.
-   `fmpro/js/extras/editors.default.js` : Fournit la fonctionnalité d'éditeur de texte par défaut dans elFinder, permettant aux utilisateurs de modifier directement les fichiers texte.
-   `fmpro/js/extras/quicklook.googledocs.js` : Améliore la fonction « aperçu rapide » en s'intégrant à Google Docs pour prévisualiser certains types de documents.
-   `fmpro/js/i18n/elfinder.*.js` : Une vaste collection de fichiers d'internationalisation (i18n), fournissant des traductions pour l'interface elFinder dans différentes langues (par exemple, `elfinder.fr.js` pour le français, `elfinder.es.js` pour l'espagnol). Ceux-ci sont chargés en fonction du paramètre de langue de l'utilisateur.
-   `fmpro/js/i18n/help/*.html.js` : Contient du contenu d'aide localisé pour l'interface elFinder, intégré sous forme de chaînes JavaScript.
-   `fmpro/js/proxy/elFinderSupportVer1.js` : Probablement une couche de compatibilité ou un script proxy pour les anciennes versions d'elFinder ou des configurations de serveur spécifiques.
-   `fmpro/js/worker/calcfilehash.js` : Un script de web worker pour calculer les hachages de fichiers, potentiellement utilisé pour les vérifications d'intégrité ou la mise en cache.
-   `fmpro/js/worker/quicklook.tiff.js` : Un script de web worker spécifiquement pour la gestion des aperçus d'images TIFF.
-   `fmpro/js/worker/quicklook.unzip.js` : Un script de web worker pour la gestion des aperçus ou de la liste de contenu des fichiers ZIP.

**Notes du développeur :**

-   La bibliothèque elFinder est autonome. Les développeurs étendant le module interagiraient principalement avec l'API d'elFinder s'ils avaient besoin de personnaliser son comportement ou de l'intégrer à d'autres composants.
-   Pour le style, le CSS personnalisé est généralement préféré à la modification de ces fichiers JS principaux.
-   Pour la localisation, assurez-vous que le fichier `elfinder.LANG.js` correct est chargé en fonction de la langue du back office de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut des fichiers CSS pour styliser l'interface elFinder. Ceux-ci sont situés dans `fmpro/css/`.

-   `fmpro/css/elfinder.full.css` : Il s'agit de la feuille de style principale pour l'interface elFinder, définissant la mise en page, les icônes, les couleurs et l'apparence visuelle globale du gestionnaire de fichiers.
-   `fmpro/css/theme.css` : Ce fichier contient probablement un style supplémentaire ou des remplacements pour intégrer elFinder plus facilement au thème du back office de PrestaShop, ou pour fournir des ajustements de thème spécifiques pour elFinder lui-même.

**Notes du développeur :**

-   Pour personnaliser l'apparence du gestionnaire de fichiers, les développeurs doivent créer leur propre fichier CSS et le charger *après* `elfinder.full.css` et `theme.css` pour remplacer des styles spécifiques.
-   Les sélecteurs de classe CSS clés sont généralement préfixés par `elfinder-` (par exemple, `.elfinder-navbar`, `.elfinder-cwd-wrapper`).

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module ne liste explicitement aucun fichier `.tpl` dans un répertoire `views/templates/` dans l'inventaire fourni. Cela suggère que l'interface elFinder est rendue directement via JavaScript et HTML générés dans la méthode `getContent()` du fichier principal `fmpro.php`, ou que le propre mécanisme de templating d'elFinder est utilisé en interne, sans exposer les fichiers `.tpl` dans la structure `views/templates/` du module.

La méthode `getContent()` produira probablement le conteneur HTML nécessaire (`<div>`) où le JavaScript elFinder initialisera et rendra le gestionnaire de fichiers.

### 4.7 Schéma de base de données et carte des hooks

**Tables de base de données** :
Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration internes (comme `mypresta_updates`, `update_`, `updatev_`) dans la table standard `ps_configuration` de PrestaShop.

-   `ps_configuration` :
    -   `name` : `MYPRESTA_UPDATES_FMPRO` (ou similaire, pour les vérifications de mise à jour)
    -   `name` : `UPDATE_FMPRO` (ou similaire, pour les vérifications de mise à jour)
    -   `name` : `UPDATEV_FMPRO` (ou similaire, pour les vérifications de mise à jour)

**Table des hooks enregistrés** :
La fonction principale du module est de fournir un outil administratif, il n'enregistre donc généralement pas beaucoup de hooks front-office. La description du module mentionne « Hooks Front-Office : Header, Columns, Product, ou Footer » mais il s'agit probablement d'une déclaration générique pour les modules MyPresta.eu et non spécifique à l'implémentation réelle de ce module, car il s'agit d'un outil d'administration.

Compte tenu de sa nature d'outil d'administration, le module interagirait principalement avec les hooks back-office, le cas échéant, pour ajouter des éléments de menu ou s'intégrer dans des pages d'administration existantes. Cependant, les informations fournies ne listent explicitement aucun hook enregistré. Le point d'intégration le plus courant pour un tel module est directement via sa méthode `getContent()`, qui est accessible en cliquant sur « Configurer » dans le Gestionnaire de modules.

S'il devait enregistrer des hooks, les plus courants pour les outils d'administration pourraient inclure :

-   `displayBackOfficeHeader` : Pour inclure ses actifs CSS/JS dans le back office.
-   `displayAdminProductsExtra` : (Moins probable pour un gestionnaire de fichiers général, mais possible pour des téléchargements de fichiers spécifiques liés aux produits).
-   `actionAdminControllerSetMedia` : Pour charger les actifs de sa page de configuration.

Compte tenu de la conception du module, son point d'entrée principal est sa page de configuration, où l'instance elFinder est initialisée.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « Gestionnaire de médias / fichiers », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité du module et son intégration avec votre boutique PrestaShop.
