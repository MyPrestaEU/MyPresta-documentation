---
title: "Assignation / déplacement en masse de produits vers des catégories - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Assignation / déplacement en masse de produits vers des catégories' par MyPresta.eu."
sidebar:
  label: "Assignation / déplacement en masse de produits vers des catégories - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Mass assign / move products to categories sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-assign-move-products-to-categories.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/mass-assign-move-products-to-categories/)
>
> ---


# Assignation / déplacement en masse de produits vers des catégories

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module « Assignation / déplacement en masse de produits vers des catégories » offre une interface de type assistant pour vous guider dans le processus de gestion des catégories de produits en masse.

### 2.1 Page de configuration du module (Back Office > Modules > Gestionnaire de modules > Configurer « Assignation / déplacement en masse de produits vers des catégories »)

En cliquant sur « Configurer », vous serez dirigé vers la page de configuration principale du module, qui agit comme un assistant étape par étape.

#### Étape 1 : Sélectionner les produits à gérer

Cette section vous permet de définir les produits que vous souhaitez modifier.

-   **Ce que fait ce paramètre :** C'est la première étape cruciale où vous identifiez le groupe de produits qui sera affecté par l'action de masse.
-   **Effet de la modification de ce paramètre :** Les produits que vous sélectionnez ici seront les seuls traités dans les étapes suivantes.
-   **Valeur recommandée :** Utilisez la barre de recherche pour trouver des produits par nom. Vous pouvez ajouter plusieurs produits à la liste.
-   **Scénario / exemple pour le marchand :**
    *   *Scénario 1 : Produits spécifiques :* Vous souhaitez déplacer « Produit A », « Produit B » et « Produit C » vers une nouvelle catégorie. Vous recherchez chaque produit et les ajoutez à la liste.
    *   *Scénario 2 : Produits d'une catégorie existante :* Vous souhaitez déplacer tous les produits actuellement dans votre catégorie « Ancienne Collection » vers une nouvelle catégorie « Articles Archivés ». Vous sélectionnez d'abord tous les produits de « Ancienne Collection » ici.

#### Étape 2 : Sélectionner les catégories auxquelles assigner/déplacer les produits

Cette section vous permet de choisir les catégories cibles pour vos produits sélectionnés.

-   **Ce que fait ce paramètre :** Ici, vous spécifiez les catégories où les produits de l'Étape 1 seront assignés ou déplacés.
-   **Effet de la modification de ce paramètre :** Les produits sélectionnés seront liés à ces catégories.
-   **Valeur recommandée :** Utilisez l'arborescence des catégories pour sélectionner une ou plusieurs catégories cibles.
-   **Scénario / exemple pour le marchand :**
    *   *Scénario 1 : Assignation à une nouvelle catégorie :* Vous avez sélectionné 5 produits à l'Étape 1. Maintenant, vous sélectionnez « Nouveautés » et « Meilleures ventes » ici. Les 5 produits seront assignés à la fois à « Nouveautés » et à « Meilleures ventes ».
    *   *Scénario 2 : Déplacement vers une seule catégorie :* Vous avez sélectionné 10 produits. Vous sélectionnez « Soldes saisonnières » ici. Selon votre choix à l'Étape 3, ces produits seront soit ajoutés à « Soldes saisonnières », soit déplacés exclusivement vers celle-ci.

#### Étape 3 : Que faire des produits sélectionnés ?

C'est l'étape la plus critique, déterminant la nature de l'action en masse.

-   **Ce que fait ce paramètre :** Cette sélection par bouton radio dicte si les produits sont *assignés* (ajoutés à de nouvelles catégories tout en conservant les existantes) ou *déplacés* (supprimés des catégories existantes et placés uniquement dans les nouvelles).
-   **Effet de la modification de ce paramètre :**
    *   **Assigner les produits aux catégories sélectionnées :**
        *   *Lorsque sélectionné :* Les produits choisis à l'Étape 1 seront *ajoutés* aux catégories sélectionnées à l'Étape 2. Ils conserveront toutes leurs associations de catégories actuelles. Ceci est utile pour référencer des produits ou les ajouter à des catégories promotionnelles sans perturber leur placement principal.
        *   *Scénario marchand :* Vous avez un produit dans « Électronique » et « Gadgets ». Vous souhaitez l'ajouter à « Offres de vacances » sans le retirer de « Électronique » ou « Gadgets ». Vous sélectionneriez « Assigner ».
    *   **Déplacer les produits vers les catégories sélectionnées (supprimer des catégories actuelles) :**
        *   *Lorsque sélectionné :* Les produits choisis à l'Étape 1 seront *supprimés* de toutes les catégories auxquelles ils sont actuellement assignés, puis *uniquement* assignés aux catégories sélectionnées à l'Étape 2. Il s'agit d'une recatégorisation complète.
        *   *Scénario marchand :* Vous avez un produit dans « Ancienne Collection » et « Articles discontinués ». Vous souhaitez qu'il n'apparaisse *que* dans « Produits archivés ». Vous sélectionneriez « Déplacer ».
-   **Valeur recommandée :** Cela dépend entièrement de votre objectif spécifique. Examinez attentivement si vous souhaitez *ajouter* des catégories ou les *remplacer*.
-   **Scénario / exemple pour le marchand :**
    *   *Assigner :* Vous organisez une vente « Black Friday ». Vous sélectionnez tous les produits en solde et les « Assignez » à la catégorie « Offres Black Friday ». Ils apparaissent toujours dans leurs catégories d'origine (par exemple, « T-shirts », « Ordinateurs portables »), mais maintenant aussi sous « Offres Black Friday ».
    *   *Déplacer :* Vous avez décidé de restructurer votre section « Vêtements pour femmes ». Vous sélectionnez tous les produits des catégories « Robes » et « Jupes » et les « Déplacez » vers une nouvelle catégorie « Bas et Robes pour femmes ». Ils n'apparaîtront plus dans les anciennes catégories « Robes » ou « Jupes ».

#### Bouton « Exécuter »

-   **Ce que fait ce paramètre :** Ce bouton lance l'opération en masse basée sur vos sélections des étapes précédentes.
-   **Effet de la modification de ce paramètre :** Une fois cliqué, le module traitera tous les produits sélectionnés selon l'action choisie (assigner ou déplacer) et les catégories cibles. Un message de confirmation ou de succès apparaîtra généralement.
-   **Valeur recommandée :** Cliquez uniquement lorsque vous êtes absolument sûr de vos sélections.
-   **Scénario / exemple pour le marchand :** Après avoir soigneusement examiné vos sélections de produits et de catégories et confirmé l'action souhaitée (assigner ou déplacer), cliquez sur « Exécuter » pour appliquer les modifications au catalogue de produits de votre boutique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration principale | **Étape 1 : Sélectionner les produits** | N/A (saisie utilisateur) | Définit les produits spécifiques à affecter par l'action en masse. |
| Configuration principale | **Étape 2 : Sélectionner les catégories** | N/A (saisie utilisateur) | Définit les catégories cibles où les produits seront assignés ou déplacés. |
| Configuration principale | **Étape 3 : Que faire ?** | N/A (choix utilisateur) | **Assigner :** Ajoute des produits à de nouvelles catégories, en conservant les existantes. **Déplacer :** Supprime de toutes les catégories actuelles, assigne uniquement aux nouvelles. |
| Configuration principale | **Bouton Exécuter** | N/A (action utilisateur) | Déclenche l'opération d'assignation/déplacement de catégorie en masse. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai cliqué sur « Exécuter », mais rien ne s'est passé, ou je ne vois pas les changements.**
R :

1.  **Vider le cache :** Après tout changement significatif dans PrestaShop, en particulier les assignations de catégories ou de produits, vous devez toujours vider le cache de votre boutique. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
2.  **Vérifier le statut du produit :** Assurez-vous que les produits que vous essayez d'assigner/déplacer sont actifs et visibles.
3.  **Vérifier le statut de la catégorie :** Assurez-vous que les catégories cibles sont actives et visibles.
4.  **Réexécuter le module :** Retournez au module, resélectionnez vos produits et catégories, et réessayez.

**Q : Mes produits ont disparu de leurs catégories d'origine après avoir utilisé le module !**
R : Cela signifie probablement que vous avez sélectionné « Déplacer les produits vers les catégories sélectionnées (supprimer des catégories actuelles) » à l'Étape 3. Cette option est conçue pour *remplacer* les assignations de catégories existantes par les nouvelles. Si cela était involontaire, vous devrez réassigner manuellement les produits à leurs catégories d'origine ou utiliser le module à nouveau avec l'option « Assigner les produits » pour les rajouter. Vérifiez toujours l'Étape 3 avant d'exécuter !

**Q : Puis-je annuler une assignation/un déplacement en masse ?**
R : Le module n'a pas de bouton « annuler ». C'est pourquoi il est crucial de **toujours sauvegarder votre base de données avant d'effectuer toute action en masse** sur votre boutique. Si vous avez fait une erreur, restaurer une sauvegarde est le moyen le plus sûr de revenir en arrière. Sinon, vous devrez corriger manuellement les assignations de catégories ou utiliser le module à nouveau pour réassigner les produits si nécessaire.

**Q : La recherche de produits ne trouve pas mes produits.**
R :

1.  **Vérifier l'orthographe :** Assurez-vous de taper correctement le nom du produit.
2.  **Statut du produit :** Assurez-vous que le produit est actif dans votre catalogue.
3.  **Vider le cache du navigateur :** Parfois, le cache du navigateur peut interférer avec les fonctions de recherche AJAX. Essayez de vider le cache de votre navigateur ou d'utiliser une fenêtre de navigation privée.

**Q : Ce module affecte-t-il la catégorie par défaut d'un produit ?**
R : Le module gère principalement les catégories *associées*. Bien que le déplacement d'un produit puisse implicitement modifier sa catégorie par défaut si l'ancienne catégorie par défaut est supprimée et qu'une seule nouvelle catégorie est assignée, il est préférable de vérifier et de définir manuellement la catégorie par défaut sur la page d'édition du produit si vous avez des exigences spécifiques en matière de SEO ou de navigation pour la catégorie par défaut.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, déboguer ou étendre le module « Assignation / déplacement en masse de produits vers des catégories ».

### 4.1 Aperçu de l'architecture

Le module `masspc` (Mass Product Categories) est un module PrestaShop standard fonctionnant principalement dans le Back Office. Il utilise AJAX pour la recherche de produits et la sélection de catégories, offrant une expérience utilisateur de type assistant. La logique principale de manipulation des produits et des catégories est gérée au sein de la classe principale du module, qui étend `Module`. Il n'introduit pas de classes `ObjectModel` personnalisées ni de contrôleurs d'administration dédiés au-delà de sa page de configuration principale.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office dédiés dans le répertoire `controllers/`. Toute la logique est gérée directement dans le fichier principal du module `masspc.php` (ou `ajax_products_list.php` selon le dossier, ce qui est une convention de nommage inhabituelle pour le fichier principal du module mais implique qu'il gère la logique principale et les requêtes AJAX).

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe ou modèle personnalisé dans un répertoire `classes/`. Toute la logique principale est encapsulée dans le fichier principal du module. La manipulation des données de produits et de catégories repose sur les classes `ObjectModel` natives de PrestaShop `Product` et `Category` et leurs méthodes associées (par exemple, `Product::updateCategories()`).

### 4.4 Actifs JavaScript (`views/js/`)

-   **`masspc/lib/searchTool/views/js/autocomplete.js`**
    *   **Portée :** Back-office (utilisé dans la page de configuration du module).
    *   **Description :** Ce script fournit probablement la fonctionnalité principale pour une fonction de recherche d'autocomplétion basée sur AJAX, spécifiquement pour trouver des produits par nom. Il écoute la saisie de l'utilisateur dans un champ de recherche, envoie des requêtes AJAX au backend du module (probablement `ajax_products_list.php` lui-même ou une méthode à l'intérieur), et affiche des suggestions. Il gère la sélection des produits et leur ajout à la liste pour traitement.
-   **`masspc/views/js/jquery.autocomplete.js`**
    *   **Portée :** Back-office (utilisé dans la page de configuration du module).
    *   **Description :** Il semble s'agir d'un plugin jQuery ou d'un script personnalisé qui implémente ou améliore la fonctionnalité d'autocomplétion. Il pourrait être une dépendance pour `autocomplete.js` ou une implémentation alternative/plus ancienne. Il gérerait le rendu visuel des suggestions d'autocomplétion et l'interaction lorsqu'un utilisateur sélectionne un élément.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`masspc/lib/searchTool/views/css/autocomplete.css`**
    *   **Portée :** Back-office (style la page de configuration du module).
    *   **Description :** Cette feuille de style fournit le style visuel pour le champ de saisie de recherche d'autocomplétion, la liste déroulante de suggestions et potentiellement la liste des produits sélectionnés dans l'interface de configuration du module. Les développeurs peuvent remplacer ces styles dans leur thème d'administration personnalisé ou en ajoutant des règles CSS plus spécifiques.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`masspc/lib/searchTool/views/scripts.tpl`**
    *   **Portée :** Back-office (inclus dans la page de configuration du module).
    *   **Description :** Ce template inclut probablement du code JavaScript ou des liens vers des fichiers JS (`autocomplete.js`, `jquery.autocomplete.js`) et potentiellement des fichiers CSS (`autocomplete.css`) requis pour l'interface de recherche et de sélection de produits. Il est généralement utilisé pour injecter des actifs dans le `<head>` ou le `<body>` de la page d'administration.
-   **`masspc/views/templates/admin/cselection.tpl`**
    *   **Portée :** Back-office (page de configuration de l'administration).
    *   **Description :** Ce template rend la section « Étape 2 : Sélectionner les catégories auxquelles assigner/déplacer les produits » du module. Il affiche la structure de l'arborescence des catégories, permettant à l'administrateur de sélectionner les catégories cibles. Il utilise probablement une structure récursive pour afficher les catégories parentes et enfants.
-   **`masspc/views/templates/admin/target_products.tpl`**
    *   **Portée :** Back-office (page de configuration de l'administration).
    *   **Description :** Ce template rend la section « Étape 1 : Sélectionner les produits à gérer ». Il inclut le champ de saisie de recherche de produits (où `autocomplete.js` opère) et affiche la liste des produits qui ont été sélectionnés pour l'action en masse.
-   **`masspc/views/templates/admin/wtd.tpl`**
    *   **Portée :** Back-office (page de configuration de l'administration).
    *   **Description :** Ce template rend la section « Étape 3 : Que faire des produits sélectionnés ? ». Il contient les boutons radio pour « Assigner les produits aux catégories sélectionnées » et « Déplacer les produits vers les catégories sélectionnées », ainsi que leurs descriptions.
-   **`masspc/views/templates/hook/form.tpl`**
    *   **Portée :** Back-office (page de configuration de l'administration).
    *   **Description :** Il s'agit probablement du template d'enveloppe principal pour le formulaire de configuration du module, qui inclut les autres templates `admin/` (`target_products.tpl`, `cselection.tpl`, `wtd.tpl`) pour construire l'interface complète de l'assistant. Il contiendrait la structure globale du formulaire et le bouton « Exécuter ».

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    *   Ce module ne crée aucune table de base de données personnalisée. Il interagit directement avec les tables principales de PrestaShop :
        *   `ps_product_category` : Pour gérer les associations produit-catégorie.
        *   `ps_product_shop` : Pour les données spécifiques au magasin du produit, y compris la catégorie par défaut.
        *   `ps_category` : Pour récupérer les noms et la structure des catégories.
        *   `ps_product` : Pour récupérer les noms et les détails des produits pour la recherche.
-   **Table des hooks enregistrés** :
    *   La fonctionnalité principale du module est accessible via sa page de configuration, et non via des hooks front-office.
    *   Il utilise probablement le hook `displayBackOfficeHeader` pour injecter ses actifs CSS et JavaScript dans l'en-tête du Back Office.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Rendu dans le `<head>` des pages du Back Office. | Injecte les fichiers CSS et JavaScript spécifiques au module pour la page de configuration. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Assignation / déplacement en masse de produits vers des catégories », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
