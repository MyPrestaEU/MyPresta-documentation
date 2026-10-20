---
title: "Blocs de contenu de page produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Blocs de contenu de page produit' par MyPresta.eu."
sidebar:
  label: "Blocs de contenu de page produit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product page content blocks sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-content-blocks.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-page-content-blocks/)
>
> ---


# Blocs de contenu de page produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et ce module n'introduit pas d'exigences spécifiques supplémentaires au-delà de cela.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module « Blocs de contenu de page produit » fonctionne principalement via un onglet dédié sur la page d'édition de chaque produit, plutôt qu'un seul écran de configuration global. Cependant, il existe une page de configuration principale du module pour la configuration initiale et un contrôleur AJAX pour la gestion des blocs.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Lorsque vous installez le module pour la première fois et cliquez sur « Configurer », vous serez redirigé vers sa page de configuration principale. Cette page gère généralement la configuration initiale ou les paramètres globaux, le cas échéant.

-   **Ce que fait ce paramètre :** Cette page sert de point d'entrée pour le module. Bien que la fonctionnalité principale de création de blocs soit effectuée sur les pages produit, cet écran peut offrir des paramètres généraux ou un aperçu rapide.
-   **Effet de la modification de ce paramètre :** Tout paramètre ici s'appliquerait globalement au comportement du module sur toutes les pages produit, comme l'activation/désactivation complète du module ou la définition de comportements par défaut.
-   **Valeur recommandée :** Suivez les instructions à l'écran. S'il n'y a pas de paramètres spécifiques, cette page confirmera simplement que le module est installé et prêt à l'emploi.
-   **Scénario/exemple pour le marchand :** Vous pourriez trouver ici un interrupteur pour « Activer/Désactiver le module » qui désactiverait tous les blocs de contenu personnalisés dans votre boutique sans désinstaller le module.

### 2.2 Écrans d'administration dédiés et vues du contrôleur

L'interaction principale avec ce module se fait sur la page d'édition du produit.

#### 2.2.1 Page d'édition du produit (Catalogue > Produits > Modifier un produit)

Après l'installation du module, lorsque vous modifiez un produit dans votre back-office PrestaShop, vous trouverez un nouvel onglet dédié aux « Blocs de contenu de page produit » (ou un nom similaire).

-   **Nom de l'écran et emplacement du menu :** **Catalogue > Produits > [Sélectionner/Modifier un produit] > Onglet « Blocs de contenu de page produit »**
-   **Actions et paramètres disponibles :**

    -   **Ajouter un nouveau bloc :** Vous verrez généralement un bouton comme « Ajouter un nouveau bloc » ou une interface similaire pour créer un nouveau bloc de contenu pour le produit actuel.
        -   **Ce que fait ce paramètre :** Vous permet de définir un nouveau contenu.
        -   **Effet de la modification de ce paramètre :** Un nouveau bloc de contenu sera créé et stocké pour ce produit spécifique.
        -   **Scénario/exemple pour le marchand :** Vous souhaitez ajouter un tutoriel vidéo pour un produit complexe. Vous cliquez sur « Ajouter un nouveau bloc ».
    -   **Éditeur de contenu :** Pour chaque bloc, vous disposerez d'un éditeur de texte enrichi (WYSIWYG) où vous pourrez saisir du texte, des images, des vidéos ou même du HTML personnalisé.
        -   **Ce que fait ce paramètre :** Définit le contenu réel qui sera affiché.
        -   **Effet de la modification de ce paramètre :** Le contenu que vous saisissez ici sera rendu sur le front-office.
        -   **Scénario/exemple pour le marchand :** Vous tapez « Regardez notre vidéo de déballage ! » et intégrez un lien vidéo YouTube.
    -   **Sélection du hook :** Une liste déroulante ou une liste de hooks PrestaShop disponibles (`displayHeader`, `displayFooterProduct`, `displayRightColumnProduct`, etc.).
        -   **Ce que fait ce paramètre :** Détermine la position exacte où votre bloc de contenu apparaîtra sur la page produit.
        -   **Effet de la modification de ce paramètre :** Le bloc sera rendu à la position du hook sélectionné.
        -   **Valeur recommandée :** Choisissez le hook qui correspond le mieux à l'objectif du contenu. Pour les détails spécifiques au produit, `displayProductAdditionalInfo` ou `displayFooterProduct` sont courants. Pour les éléments de confiance, `displayReassurance`.
        -   **Scénario/exemple pour le marchand :** Vous souhaitez qu'un badge de confiance apparaisse près du bouton d'ajout au panier, vous sélectionnez donc `displayReassurance`.
    -   **Statut du bloc (Activé/Désactivé) :** Un interrupteur pour activer ou désactiver le bloc.
        -   **Ce que fait ce paramètre :** Contrôle si le bloc est visible sur le front-office.
        -   **Effet de la modification de ce paramètre :**
            -   *Lorsqu'il est activé :* Le bloc apparaîtra sur la page produit.
            -   *Lorsqu'il est désactivé :* Le bloc sera masqué mais non supprimé, vous permettant de le réactiver ultérieurement.
        -   **Valeur recommandée :** Activez les blocs que vous souhaitez afficher, désactivez ceux que vous souhaitez masquer temporairement.
        -   **Scénario/exemple pour le marchand :** Vous avez un bloc de promotion saisonnière que vous souhaitez masquer après la fin de la saison, mais que vous pourriez réutiliser l'année prochaine.
    -   **Ordre/Position :** Souvent une interface de glisser-déposer ou un champ de saisie pour définir l'ordre d'affichage si plusieurs blocs se trouvent dans le même hook.
        -   **Ce que fait ce paramètre :** Détermine la séquence des blocs au sein d'un même hook.
        -   **Effet de la modification de ce paramètre :** Les blocs apparaîtront dans l'ordre spécifié.
        -   **Scénario/exemple pour le marchand :** Vous avez trois badges de confiance dans `displayReassurance` et souhaitez que le badge « Livraison gratuite » apparaisse en premier.
    -   **Modification/Suppression de blocs :** Boutons pour modifier les blocs existants ou les supprimer entièrement.
        -   **Ce que fait ce paramètre :** Vous permet de mettre à jour le contenu, le hook ou le statut, ou de supprimer définitivement un bloc.
        -   **Effet de la modification de ce paramètre :** Met à jour ou supprime le bloc de la page produit.
        -   **Scénario/exemple pour le marchand :** Une description de produit a changé, vous modifiez donc le contenu d'un bloc associé.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  Naviguez vers **Catalogue > Produits** et sélectionnez le produit que vous souhaitez améliorer.
    2.  Cliquez sur l'onglet « Blocs de contenu de page produit ».
    3.  Cliquez sur « Ajouter un nouveau bloc » pour créer une nouvelle section de contenu.
    4.  Saisissez votre contenu à l'aide de l'éditeur de texte enrichi.
    5.  Sélectionnez le hook approprié pour l'emplacement où vous souhaitez que le contenu apparaisse.
    6.  Assurez-vous que le bloc est activé.
    7.  Enregistrez vos modifications pour le produit.
    8.  Répétez l'opération pour d'autres produits si nécessaire. Vérifiez régulièrement vos pages produit pour vous assurer que les blocs s'affichent comme prévu.

#### 2.2.2 AdminMegablocksAjaxController (megablocks/controllers/admin/AdminMegablocksAjax.php)

Ce contrôleur n'est pas directement accessible par les marchands via un élément de menu. Au lieu de cela, il gère les opérations en arrière-plan (requêtes AJAX) lorsque vous interagissez avec l'onglet « Blocs de contenu de page produit » sur la page d'édition du produit. Par exemple, lorsque vous enregistrez un nouveau bloc, modifiez un bloc existant ou modifiez son ordre, ce contrôleur traite ces requêtes sans nécessiter un rechargement complet de la page.

-   **Nom de l'écran et emplacement du menu :** Non directement accessible. Il fonctionne en arrière-plan sur la page d'édition du produit.
-   **Actions et paramètres disponibles :** Il gère la création, la mise à jour, la suppression et le réordonnancement des blocs de contenu pour les produits individuels.
-   **Effet des modifications :** Garantit que vos modifications apportées aux blocs de contenu sur la page d'édition du produit sont enregistrées dans la base de données et reflétées sur le front-office.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vous interagissez implicitement avec ce contrôleur en utilisant l'onglet « Blocs de contenu de page produit » sur la page d'édition du produit. Aucune interaction directe n'est requise.

#### 2.2.3 index.php (megablocks/controllers/admin/index.php)

Ce fichier est une pratique PrestaShop standard pour sécuriser les répertoires des contrôleurs d'administration et contient généralement uniquement une instruction `die('Access Denied');`. Il ne représente pas un écran fonctionnel ou une zone de configuration pour le marchand.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | (Paramètres globaux, le cas échéant) | (Selon les valeurs par défaut du module) | Configuration initiale, activation/désactivation globale ou comportement général du module. |
| **Page d'édition du produit (Onglet)** | Ajouter un nouveau bloc | N/A | Crée un nouveau bloc de contenu pour le produit actuel. |
| | Éditeur de contenu | Vide | Définit le contenu HTML/texte du bloc. |
| | Sélection du hook | Varie (par exemple, `displayFooterProduct`) | Détermine la position d'affichage sur la page produit. |
| | Statut du bloc | Activé | Contrôle la visibilité du bloc sur le front-office. |
| | Ordre/Position | 1 (ou le suivant disponible) | Définit la séquence d'affichage des blocs au sein d'un hook. |
| | Modifier/Supprimer le bloc | N/A | Modifie ou supprime les blocs de contenu existants. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon nouveau bloc de contenu n'apparaît pas sur la page produit. Que dois-je faire ?**
**R1 :**

1.  **Vérifier le statut du bloc :** Allez sur la page d'édition du produit, naviguez vers l'onglet « Blocs de contenu de page produit » et assurez-vous que le bloc que vous avez créé est défini sur « Activé ».
2.  **Vider le cache :** PrestaShop utilise la mise en cache pour accélérer votre boutique. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » si disponible).
3.  **Vérifier la sélection du hook :** Vérifiez à nouveau que vous avez sélectionné un hook qui est réellement rendu par votre thème sur la page produit. Certains thèmes peuvent ne pas utiliser tous les hooks PrestaShop standard.
4.  **Compatibilité du thème :** Si votre thème est fortement personnalisé, il peut remplacer les emplacements de hook standard. Contactez le développeur de votre thème ou un webmaster pour confirmer la structure des hooks du thème.

**Q2 : Le bloc de contenu semble étrange ou non stylisé sur ma page produit.**
**R2 :**

1.  **Vérifiez votre contenu :** Si vous avez ajouté du HTML personnalisé ou copié du contenu d'une autre source, il peut contenir des styles conflictuels. Essayez de coller votre contenu dans un éditeur de texte brut d'abord pour supprimer tout formatage caché, puis recollez-le dans l'éditeur du module.
2.  **CSS du module :** Le module inclut un CSS de base. Si votre thème a un style très spécifique, il peut remplacer ou entrer en conflit avec les styles du module.
3.  **Style de thème personnalisé :** Pour un style avancé, vous pourriez avoir besoin d'un webmaster pour ajouter des règles CSS personnalisées à la feuille de style de votre thème afin que le bloc corresponde au design de votre boutique. Ils peuvent cibler les éléments HTML spécifiques générés par le module.

**Q3 : Puis-je utiliser ce module pour les boutiques multilingues ?**
**R3 :** Oui, généralement, les blocs de contenu créés avec ce module prendront en charge la fonctionnalité multilingue de PrestaShop. Lors de l'édition d'un bloc, vous devriez voir des onglets de langue (par exemple, Anglais, Français, Espagnol) à côté de l'éditeur de contenu. Vous pouvez saisir un contenu différent pour chaque langue, garantissant que vos blocs sont localisés pour vos clients internationaux.

**Q4 : Je souhaite afficher le même bloc sur plusieurs pages produit. Dois-je le créer à plusieurs reprises ?**
**R4 :** Ce module est conçu pour le contenu *spécifique au produit*. Si vous avez besoin du *même* bloc de contenu sur de nombreux produits, vous devrez actuellement le créer pour chaque produit. Pour un contenu véritablement global qui apparaît sur *toutes* les pages produit (ou toutes les pages d'un certain type), un autre type de module (par exemple, un module de bloc HTML personnalisé qui se hooke globalement) pourrait être plus efficace. Cependant, la force de ce module est sa capacité à adapter le contenu par produit.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Blocs de contenu de page produit » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module « Blocs de contenu de page produit » (`megablocks`) suit une architecture de module PrestaShop standard, tirant principalement parti de la classe `Module` pour l'installation et l'enregistrement des hooks. Sa fonctionnalité principale tourne autour de la gestion des blocs de contenu spécifiques aux produits, qui sont stockés dans une table de base de données personnalisée. Le module étend la fonctionnalité du back-office de PrestaShop en injectant un onglet personnalisé dans la page d'édition du produit, géré par un contrôleur AJAX. L'affichage du front-office est réalisé en se hookant à divers hooks `display*` sur la page produit et en rendant des templates Smarty spécifiques.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Ce module ne contient aucun contrôleur front-office dédié. Tout le rendu du contenu front-office est géré directement via des hooks enregistrés dans le fichier principal du module `index.php`, qui rend ensuite des templates spécifiques.
-   **Contrôleurs d'administration Back-Office** :

    -   `megablocks/controllers/admin/AdminMegablocksAjax.php`
        -   **Nom de la classe et classe parente** : `AdminMegablocksAjaxController` étendant `ModuleAdminController`.
        -   **Responsabilité** : Ce contrôleur gère toutes les requêtes AJAX provenant de l'onglet « Blocs de contenu de page produit » sur la page d'édition du produit. Il est responsable de :
            -   La création de nouveaux blocs de contenu.
            -   La mise à jour des blocs de contenu existants (contenu, hook, statut, position).
            -   La suppression des blocs de contenu.
            -   La récupération des données des blocs de contenu pour un produit spécifique.
            -   Il n'a pas d'entrée de menu directe mais est invoqué via des appels JavaScript depuis la page d'édition du produit.
    -   `megablocks/controllers/admin/index.php`
        -   **Nom de la classe et classe parente** : Pas un contrôleur fonctionnel.
        -   **Responsabilité** : Il s'agit d'un fichier de sécurité, standard dans les répertoires d'administration de PrestaShop, contenant `die('Access Denied');` pour empêcher l'affichage direct du répertoire ou l'accès.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela implique que la gestion des données du module (par exemple, la sauvegarde et la récupération des blocs de contenu) est probablement gérée directement dans le fichier principal `megablocks/index.php`, potentiellement en utilisant `Db::getInstance()` pour des interactions directes avec la base de données ou une simple structure de tableau pour la configuration. Si une table de base de données personnalisée est utilisée, son schéma et ses méthodes d'interaction seraient définis dans le fichier principal du module.

### 4.4 Actifs JavaScript (`views/js/`)

-   `megablocks/js/script.js`
    -   **Portée** : Probablement front-office.
    -   **Détails** : Ce script contiendrait toute logique côté client requise pour l'affichage front-office des blocs de contenu. Cela pourrait inclure des animations simples, des ajustements réactifs ou des interactions si les blocs contiennent des éléments dynamiques.
-   `megablocks/views/admin/megablocks.js`
    -   **Portée** : Back-office (Page d'édition du produit).
    -   **Détails** : Il s'agit du fichier JavaScript principal pour la gestion des blocs de contenu dans le back-office. Il est responsable de :
        -   L'initialisation de l'onglet « Blocs de contenu de page produit » sur la page d'édition du produit.
        -   La gestion des événements de clic pour les boutons « Ajouter un nouveau bloc », « Modifier » et « Supprimer ».
        -   La gestion de l'éditeur de texte enrichi (par exemple, l'intégration de TinyMCE ou CKEditor) pour la saisie de contenu.
        -   L'envoi de requêtes AJAX à `AdminMegablocksAjaxController` pour la création, la mise à jour et la suppression de blocs.
        -   La mise à jour dynamique de l'interface utilisateur en fonction des réponses AJAX (par exemple, l'ajout d'un nouveau bloc à la liste, la suppression d'un bloc supprimé).
        -   L'implémentation de la fonctionnalité de glisser-déposer pour le réordonnancement des blocs.
-   `megablocks/views/fancybox/script.js`
    -   **Portée** : Back-office (Page d'édition du produit).
    -   **Détails** : Ce script s'intègre probablement à ou implémente une « Fancybox » (ou une bibliothèque modale/lightbox similaire) pour afficher les formulaires « Ajouter un nouveau bloc » ou « Modifier un bloc » dans une fenêtre contextuelle. Il gérerait l'ouverture/fermeture de la modale, le chargement du contenu et la soumission des données du formulaire.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `megablocks/views/admin/megablocks.css`
    -   **Portée** : Style des formulaires d'administration du back-office.
    -   **Détails** : Contient des règles CSS spécifiques pour styliser l'onglet « Blocs de contenu de page produit », la liste des blocs, les formulaires d'ajout/édition et tout élément d'interface utilisateur personnalisé dans le back-office de PrestaShop.
    -   **Sélecteurs de classe CSS clés** : Les développeurs peuvent inspecter le HTML généré sur la page d'édition du produit pour identifier des classes spécifiques (par exemple, `.megablocks-list`, `.megablock-item`, `.megablock-form`) à remplacer ou à étendre dans leur thème d'administration personnalisé ou leurs overrides de module.
-   `megablocks/views/css/milligram.css`
    -   **Portée** : Potentiellement à la fois front-office et back-office, ou spécifiquement pour les formulaires modaux.
    -   **Détails** : Milligram est un framework CSS minimaliste. Son inclusion suggère que le module pourrait l'utiliser pour un style de base et propre de ses blocs de contenu générés sur le front-office, ou pour les formulaires modaux dans le back-office (par exemple, le contenu Fancybox). Il fournit une base légère pour la typographie, les formulaires et la mise en page en grille.
    -   **Sélecteurs de classe CSS clés** : Les classes Milligram standard (par exemple, `.container`, `.row`, `.column`, `.button`, `.input`) seraient présentes. Les développeurs peuvent les remplacer ou ajouter des styles plus spécifiques dans le CSS de leur thème.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/front/`)** : Ces templates sont inclus dynamiquement par le module lorsqu'un bloc de contenu est configuré pour un hook spécifique. Chaque fichier `megablock-*.tpl` sert probablement de wrapper ou de template standard pour le rendu du contenu d'un seul bloc. Le contenu réel (HTML) défini par le marchand est généralement passé comme variable Smarty et rendu directement.

    -   `megablocks/views/front/megablock-actionProductOutOfStock.tpl` : Rend le contenu lorsqu'un produit est en rupture de stock.
    -   `megablocks/views/front/megablock-displayAfterProductThumbs.tpl` : Rend le contenu après les images/miniatures du produit.
    -   `megablocks/views/front/megablock-displayBeforeBodyClosingTag.tpl` : Rend le contenu juste avant la balise `</body>`.
    -   `megablocks/views/front/megablock-displayFooter.tpl` : Rend le contenu dans le pied de page général du site.
    -   `megablocks/views/front/megablock-displayFooterBefore.tpl` : Rend le contenu avant le pied de page général du site.
    -   `megablocks/views/front/megablock-displayFooterProduct.tpl` : Rend le contenu dans la zone de pied de page spécifique au produit.
    -   `megablocks/views/front/megablock-displayHeader.tpl` : Rend le contenu dans l'en-tête général du site.
    -   `megablocks/views/front/megablock-displayLeftColumnProduct.tpl` : Rend le contenu dans la colonne de gauche de la page produit.
    -   `megablocks/views/front/megablock-displayNav1.tpl` : Rend le contenu dans la première zone de navigation.
    -   `megablocks/views/front/megablock-displayNav2.tpl` : Rend le contenu dans la deuxième zone de navigation.
    -   `megablocks/views/front/megablock-displayProductAdditionalInfo.tpl` : Rend le contenu dans la section des informations supplémentaires du produit.
    -   `megablocks/views/front/megablock-displayProductPriceBlock.tpl` : Rend le contenu près du bloc de prix du produit.
    -   `megablocks/views/front/megablock-displayReassurance.tpl` : Rend le contenu dans le bloc de réassurance (par exemple, badges de confiance).
    -   `megablocks/views/front/megablock-displayRightColumnProduct.tpl` : Rend le contenu dans la colonne de droite de la page produit.
    -   `megablocks/views/front/megablock-displayTop.tpl` : Rend le contenu dans la section supérieure de la page.
-   **Templates d'administration (`views/templates/admin/`)** :

    -   `megablocks/views/admin/li_megablock.tpl` : Ce template est probablement utilisé pour rendre un seul élément dans la liste des blocs de contenu sur la page d'édition du produit. Il afficherait le titre du bloc, le hook sélectionné, le statut et les boutons d'édition/suppression.
    -   `megablocks/views/admin/tabs.tpl` : Ce template définit probablement la structure de l'onglet « Blocs de contenu de page produit » lui-même, y compris le bouton « Ajouter un nouveau bloc » et le conteneur pour la liste des blocs.
-   **Templates Fancybox (`views/fancybox/`)** : Ces templates sont utilisés pour les formulaires modaux (Fancybox) dans le back-office.

    -   `megablocks/views/fancybox/edit.tpl` : Le template de formulaire pour modifier un bloc de contenu existant.
    -   `megablocks/views/fancybox/heading.tpl` : Un template pour l'en-tête ou le titre de la modale Fancybox.
    -   `megablocks/views/fancybox/new.tpl` : Le template de formulaire pour créer un nouveau bloc de contenu.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module crée probablement une table de base de données personnalisée, par exemple, `ps_megablocks` (ou similaire), pour stocker les blocs de contenu.
    -   Cette table contiendrait généralement des champs tels que :
        -   `id_megablock` : Clé primaire.
        -   `id_product` : Clé étrangère liée à `ps_product`.
        -   `hook_name` : Le nom du hook PrestaShop où le bloc est affiché (par exemple, `displayFooterProduct`).
        -   `position` : L'ordre du bloc dans son hook.
        -   `active` : Booléen (0 ou 1) pour le statut du bloc.
        -   `content` : Le contenu HTML réel du bloc (probablement un champ `TEXT` ou `LONGTEXT`).
        -   `content_lang` : Si le contenu est multilingue, il peut s'agir d'une table séparée (`ps_megablocks_lang`) ou géré via des données sérialisées dans `content`.
    -   Les enregistrements de configuration sont stockés dans `ps_configuration` pour les paramètres globaux du module (par exemple, `MEGABLOCKS_ENABLED`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :--- | :--- | :--- |
| `displayHeader` | Rend le contenu dans la section `<head>` du document HTML. | N/A | Principalement pour inclure du CSS, du JavaScript, des balises meta ou d'autres éléments qui affectent le comportement technique de la page ou le style global. |
| `displayNav1` | Rend le contenu dans la première zone de navigation. | N/A | Généralement pour afficher des éléments comme les sélecteurs de devise, les sélecteurs de langue ou les liens rapides. |
| `displayNav2` | Rend le contenu dans la deuxième zone de navigation. | N/A | Souvent utilisé pour les liens de compte client, les informations de contact ou d'autres éléments de navigation secondaires. |
| `displayTop` | Rend le contenu dans la section supérieure de la page, généralement sous l'en-tête mais au-dessus du contenu principal. | N/A | Idéal pour les bannières, les barres de recherche ou les annonces importantes. |
| `displayLeftColumnProduct` | Rend le contenu dans la barre latérale gauche de la page produit. | N/A | Convient aux filtres de produits, aux catégories associées ou aux blocs promotionnels spécifiques au produit. |
| `displayRightColumnProduct` | Rend le contenu dans la barre latérale droite de la page produit. | N/A | Similaire à la colonne de gauche, peut être utilisé pour les ventes croisées, les informations du service client ou les badges de confiance. |
| `displayAfterProductThumbs` | Rend le contenu immédiatement après les miniatures des images du produit. | N/A | Bon pour les points forts rapides du produit, les courtes vidéos ou les appels à fonctionnalités spécifiques. |
| `displayProductAdditionalInfo` | Rend le contenu dans le bloc d'informations principales du produit, souvent près de la description ou des caractéristiques. | N/A | Excellent pour les spécifications détaillées, les instructions d'utilisation ou les propositions de vente uniques. |
| `displayProductPriceBlock` | Rend le contenu près de l'affichage du prix du produit. | N/A | Utile pour afficher les options de financement, les garanties de prix ou les messages de réduction spéciaux. |
| `displayReassurance` | Rend le contenu dans le bloc de réassurance du produit, généralement près du bouton d'ajout au panier. | N/A | Parfait pour les badges de confiance, les informations de livraison, les politiques de retour ou les icônes de paiement sécurisé. |
| `displayFooterProduct` | Rend le contenu dans la zone de pied de page spécifique au produit, généralement sous les détails principaux du produit. | N/A | Peut être utilisé pour des détails de produit étendus, des FAQ ou des avis clients. |
| `actionProductOutOfStock` | S'exécute lorsqu'un produit est en rupture de stock. | N/A | Permet d'afficher des messages ou des formulaires spécifiques pour les produits en rupture de stock. |
| `displayFooterBefore` | Rend le contenu juste avant le pied de page principal du site. | N/A | Convient aux promotions de dernière minute ou aux appels à l'action avant le pied de page. |
| `displayFooter` | Rend le contenu dans le pied de page général du site. | N/A | Pour les informations à l'échelle du site, mais peut être personnalisé par produit pour des éléments de pied de page uniques. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Blocs de contenu de page produit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module et son intégration avec votre boutique PrestaShop.
