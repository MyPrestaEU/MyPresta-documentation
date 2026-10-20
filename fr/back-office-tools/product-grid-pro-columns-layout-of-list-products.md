---
title: "Product Grid Pro - colonnes et mise en page des produits listés - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Product Grid Pro - colonnes et mise en page des produits listés par MyPresta.eu."
sidebar:
  label: "Product Grid Pro - colonnes et mise en page des produits listés"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product Grid Pro - columns & layout of list products sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-grid-pro-columns-layout-of-list-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/product-grid-pro-columns-layout-of-list-products/)
>
> ---


# Product Grid Pro - colonnes et mise en page des produits listés

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence d'hébergement particulière au-delà d'une configuration PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Ce module fonctionne principalement en surchargeant le contrôleur de liste de produits PrestaShop par défaut. Sa configuration est principalement gérée directement dans la section "Catalogue > Produits" elle-même, avec une simple option de "réinitialisation" disponible dans la configuration principale du module.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour y accéder, naviguez vers **Modules > Gestionnaire de modules**, recherchez "Product Grid Pro" et cliquez sur "Configurer".

Cet écran offre une seule option cruciale :

-   **Réinitialiser la configuration du module**
    -   **Ce que fait ce paramètre :** Ce bouton vous permet de rétablir tous les changements effectués par le module à ses paramètres par défaut. Cela signifie que tout ordre de colonne personnalisé, toute visibilité ou toute colonne ajoutée que vous avez configurée dans la liste "Catalogue > Produits" sera réinitialisé à l'état initial du module.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque cliqué :* Le module effacera ses préférences stockées pour la mise en page de votre grille de produits. Ceci est utile si vous avez effectué de nombreux changements et souhaitez repartir de zéro, ou si vous rencontrez un problème d'affichage inattendu et souhaitez exclure les problèmes de configuration.
    -   **Valeur recommandée :** Ne cliquez sur ce bouton que si vous souhaitez explicitement réinitialiser la personnalisation de votre grille de produits.
    -   **Scénario / exemple pour le marchand :** Vous avez expérimenté différentes mises en page de colonnes pendant des mois, et maintenant votre liste de produits semble encombrée ou désorganisée. Cliquer sur "Réinitialiser la configuration du module" la ramènera à un état propre et par défaut, vous permettant de la reconfigurer à partir de zéro.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

La fonctionnalité principale de "Product Grid Pro" est expérimentée directement dans la section **Catalogue > Produits** de votre Back Office PrestaShop. Ce module améliore la liste de produits standard, ajoutant de nouvelles colonnes et vous permettant de personnaliser sa mise en page.

-   **Nom de l'écran et emplacement du menu :** **Catalogue > Produits**
-   **Actions et paramètres disponibles :**
    -   **Nouvelles colonnes :** Le module introduit plusieurs nouvelles colonnes très utiles à votre liste de produits. Celles-ci incluent :
        -   **EAN13 :** Numéro d'article européen (code-barres).
        -   **Référence fournisseur :** Votre référence interne pour le produit de votre fournisseur.
        -   **Fabricant :** La marque ou le fabricant du produit.
        -   **Déclinaisons :** Indique si le produit a des variations (tailles, couleurs, etc.).
        -   **Unités vendues :** Le nombre total d'unités de ce produit vendues.
        -   **Dernière vente :** La date à laquelle la dernière unité de ce produit a été vendue.
        -   **Poids :** Le poids du produit.
        -   **Prix de gros :** Le prix de gros du produit.
        -   **Créé le :** La date à laquelle le produit a été ajouté à votre catalogue.
        -   **Condition :** La condition du produit (Neuf, Occasion, Reconditionné).
        -   **En solde :** Indique si le produit est actuellement en solde.
        -   **Disponible à la commande :** Si les clients peuvent actuellement acheter le produit.
        -   **Afficher le prix :** Si le prix du produit est affiché sur le front office.
        -   **En ligne uniquement :** Indique si le produit est uniquement disponible en ligne (pas dans les magasins physiques).
        -   **Visibilité :** Où le produit est visible (Catalogue, Recherche, Les deux, Aucun).
        -   **Virtuel :** Indique si le produit est un produit virtuel (par exemple, téléchargement, service).
        -   **Pack :** Indique si le produit est un pack de produits.
        -   **Indexé :** Si le produit est indexé pour la recherche.
        -   **Personnalisable :** Si le produit a des champs de personnalisation.
        -   **Fournisseur :** Le fournisseur spécifique associé au produit.
    -   **Visibilité des colonnes :** Vous pouvez choisir lesquelles de ces nouvelles colonnes et des colonnes existantes sont visibles dans votre liste de produits. Cela aide à désencombrer la vue et à se concentrer sur ce qui est important.
    -   **Ordre des colonnes (Glisser-déposer) :** Vous pouvez facilement réorganiser les colonnes en les faisant glisser et déposer dans votre séquence préférée. Cela vous permet d'organiser les informations les plus critiques à gauche pour un accès rapide.
    -   **Filtrage et tri :** Chacune des nouvelles colonnes prend en charge le filtrage et le tri, tout comme les colonnes PrestaShop par défaut. Cela signifie que vous pouvez, par exemple, trier les produits par "Unités vendues" pour voir vos meilleures ventes, ou filtrer par "Fabricant" pour gérer les produits d'une marque spécifique.
-   **Effet des changements :**
    -   **Ajout/Suppression de colonnes :** Modifie directement les informations affichées dans votre liste "Catalogue > Produits". La suppression d'une colonne masque ces données ; l'ajout d'une colonne les rend visibles.
    -   **Réorganisation des colonnes :** Modifie la mise en page visuelle de la liste des produits, vous permettant de prioriser les informations.
    -   **Filtrage/Tri :** Vous aide à localiser et analyser rapidement des groupes spécifiques de produits en fonction des critères que vous définissez.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Identifiez vos métriques clés :** Quelles informations sur les produits vérifiez-vous le plus souvent ? (par exemple, stock, prix, unités vendues, référence fournisseur).
    2.  **Activez les colonnes essentielles :** Allez dans **Catalogue > Produits**, trouvez les options de personnalisation des colonnes (souvent une icône d'engrenage ou un bouton "Colonnes"), et n'activez que les colonnes dont vous avez réellement besoin.
    3.  **Organisez pour l'efficacité :** Faites glisser et déposez vos colonnes les plus importantes sur le côté gauche de la grille afin qu'elles soient immédiatement visibles sans défilement horizontal.
    4.  **Utilisez les filtres :** Lors de la gestion des stocks, utilisez le filtre "Unités vendues" pour identifier les articles à faible rotation, ou filtrez par "Dernière vente" pour trouver les produits qui n'ont pas été vendus récemment.
    5.  **Revoyez régulièrement :** Revoyez périodiquement la configuration de vos colonnes pour vous assurer qu'elle répond toujours à vos besoins opérationnels.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | Réinitialiser la configuration du module | N/A (bouton) | Rétablit tous les paramètres personnalisés de la grille de produits (visibilité des colonnes, ordre) aux valeurs par défaut du module. À utiliser pour repartir de zéro ou résoudre des problèmes. |
| Grille Catalogue > Produits | Colonne EAN13 | Désactivé | Affiche le code-barres EAN13 pour chaque produit. Utile pour l'inventaire et la numérisation. |
| Grille Catalogue > Produits | Colonne Référence fournisseur | Désactivé | Affiche la référence interne du fournisseur pour le produit. Essentiel pour la gestion des fournisseurs. |
| Grille Catalogue > Produits | Colonne Fabricant | Désactivé | Affiche le fabricant/la marque du produit. Utile pour la gestion spécifique à la marque. |
| Grille Catalogue > Produits | Colonne Déclinaisons | Désactivé | Indique si un produit a des déclinaisons. Vérification rapide pour les produits complexes. |
| Grille Catalogue > Produits | Colonne Unités vendues | Désactivé | Affiche le total des unités vendues pour chaque produit. Idéal pour identifier les meilleures ventes. |
| Grille Catalogue > Produits | Colonne Dernière vente | Désactivé | Affiche la date de la dernière vente pour un produit. Aide à identifier les stocks à faible rotation. |
| Grille Catalogue > Produits | Colonne Poids | Désactivé | Affiche le poids du produit. Important pour les calculs d'expédition. |
| Grille Catalogue > Produits | Colonne Prix de gros | Désactivé | Affiche le prix de gros. Utile pour les calculs de marge et les boutiques B2B. |
| Grille Catalogue > Produits | Colonne Créé le | Désactivé | Affiche la date d'ajout du produit. Aide à suivre la croissance du catalogue. |
| Grille Catalogue > Produits | Colonne Condition | Désactivé | Affiche la condition du produit (Neuf, Occasion, Reconditionné). Pertinent pour certains types de produits. |
| Grille Catalogue > Produits | Colonne En solde | Désactivé | Indique si le produit est actuellement en solde. Aperçu rapide des promotions. |
| Grille Catalogue > Produits | Colonne Disponible à la commande | Désactivé | Indique si le produit peut être commandé. Essentiel pour la gestion des stocks. |
| Grille Catalogue > Produits | Colonne Afficher le prix | Désactivé | Indique si le prix est visible sur le front office. |
| Grille Catalogue > Produits | Colonne En ligne uniquement | Désactivé | Indique si le produit est exclusif aux ventes en ligne. |
| Grille Catalogue > Produits | Colonne Visibilité | Désactivé | Affiche où le produit est visible (catalogue, recherche, les deux, aucun). |
| Grille Catalogue > Produits | Colonne Virtuel | Désactivé | Indique si le produit est virtuel (téléchargeable, service). |
| Grille Catalogue > Produits | Colonne Pack | Désactivé | Indique si le produit est un pack d'autres produits. |
| Grille Catalogue > Produits | Colonne Indexé | Désactivé | Indique si le produit est indexé pour la recherche. |
| Grille Catalogue > Produits | Colonne Personnalisable | Désactivé | Indique si le produit a des options de personnalisation. |
| Grille Catalogue > Produits | Colonne Fournisseur | Désactivé | Affiche le fournisseur principal du produit. |
| Grille Catalogue > Produits | Ordre des colonnes (Glisser-déposer) | N/A (défini par l'utilisateur) | Personnalisez la séquence visuelle des colonnes pour un flux de travail optimal. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai activé de nouvelles colonnes, mais elles n'apparaissent pas dans la liste des produits.**
R1 : Après avoir activé les colonnes, assurez-vous d'enregistrer vos modifications (s'il y a un bouton d'enregistrement dans l'interface de personnalisation des colonnes). Parfois, vider le cache de votre navigateur ou le cache Smarty de PrestaShop peut aider. Allez dans **Paramètres avancés > Performances**, et cliquez sur "Vider le cache" en haut à droite.

**Q2 : Le réordonnancement par glisser-déposer ne fonctionne pas, ou la mise en page semble étrange.**
R2 : Cela pourrait être un conflit JavaScript avec un autre module ou votre thème.
    1.  Essayez de vider le cache de votre navigateur et le cache Smarty de PrestaShop (**Paramètres avancés > Performances > Vider le cache**).
    2.  Si le problème persiste, essayez de cliquer sur le bouton "Réinitialiser la configuration du module" sur la page de configuration du module (**Modules > Gestionnaire de modules > Product Grid Pro > Configurer**). Cela rétablira la mise en page par défaut et pourrait résoudre le conflit.
    3.  Si le problème persiste, désactivez temporairement d'autres modules qui modifient également la liste des produits ou l'interface d'administration pour identifier un conflit.

**Q3 : Puis-je ajouter encore plus de champs personnalisés à la grille de produits ?**
R3 : Ce module fournit un ensemble prédéfini de champs couramment demandés. Il n'offre pas de moyen générique d'ajouter *n'importe quel* champ personnalisé que vous auriez pu créer (par exemple, avec un autre module de champs personnalisés). Si vous avez besoin d'un champ personnalisé très spécifique, cela nécessiterait un développement personnalisé supplémentaire.

**Q4 : Ce module va-t-il ralentir mon Back Office ?**
R4 : Le module est conçu pour être efficace. Bien que l'ajout de nombreuses colonnes signifie que plus de données sont chargées, l'impact sur les performances est généralement minimal et compensé par les gains d'efficacité. Si vous remarquez des ralentissements significatifs, envisagez de désactiver les colonnes moins critiques pour réduire les données chargées.

**Q5 : Le module est installé, mais je ne vois aucune nouvelle option dans Catalogue > Produits.**
R5 : Assurez-vous que le module est correctement installé et activé. Parfois, après l'installation, vous devrez peut-être actualiser votre navigateur ou même vous déconnecter et vous reconnecter au Back Office pour que les modifications prennent effet. Vérifiez également les messages d'erreur pendant l'installation. Si vous êtes sur PrestaShop 1.6, l'interface de personnalisation des colonnes peut être légèrement différente de 1.7/8/9.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module "Product Grid Pro".

### 4.1 Aperçu de l'architecture

Le module "Product Grid Pro" fonctionne principalement en surchargeant le `AdminProductsController` de base dans PrestaShop. Il s'agit d'une technique courante et puissante dans le développement de modules PrestaShop, permettant aux modules d'étendre ou de modifier le comportement des fonctionnalités de base sans altérer directement les fichiers du cœur. Le module injecte des colonnes, des filtres et des capacités de tri supplémentaires dans le tableau de la liste des produits en manipulant le tableau `$this->fields_list` au sein du contrôleur surchargé. Il utilise également un fichier JavaScript dédié pour gérer le réordonnancement des colonnes par glisser-déposer et potentiellement d'autres améliorations dynamiques de l'interface utilisateur. La configuration est stockée dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit pas de nouveaux contrôleurs front-office. Son interaction principale est avec le `AdminProductsController` du Back Office.

-   **Contrôleurs Front-Office** : Aucun.
-   **Contrôleurs Admin Back-Office** :
    *   `myproductgridpro/override/controllers/admin/AdminProductsController.php`
        *   **Nom de la classe et classe parente** : `AdminProductsController` (surcharge le `AdminProductsController` de base).
        *   **Responsabilité** : C'est le cœur de la fonctionnalité du module. Il étend la fonctionnalité de la liste de produits par défaut.
            *   Il modifie le tableau `$this->fields_list` pour ajouter de nouvelles définitions de colonnes (EAN13, Référence fournisseur, Fabricant, Unités vendues, Dernière vente, Poids, Prix de gros, Créé le, Condition, En solde, Disponible à la commande, Afficher le prix, En ligne uniquement, Visibilité, Virtuel, Pack, Indexé, Personnalisable, Fournisseur).
            *   Il s'assure que ces nouveaux champs sont triables et filtrables.
            *   Il gère la logique de récupération des données pour ces nouvelles colonnes depuis la base de données.
            *   Il intègre le JavaScript pour le réordonnancement des colonnes et la gestion de la visibilité.
    *   `myproductgridpro/override/controllers/admin/index.php`
        *   **Nom de la classe et classe parente** : Ce fichier est probablement un espace réservé ou un simple redirecteur au sein de la structure de surcharge et ne contient pas une définition complète de classe de contrôleur pour une entité spécifique. Sa présence dans le répertoire `override/controllers/admin/` suggère qu'il pourrait faire partie du mécanisme de surcharge lui-même, assurant potentiellement que la surcharge de `AdminProductsController.php` est correctement chargée ou gérant le contexte d'administration général. Dans la plupart des cas, la logique réelle réside dans `AdminProductsController.php`.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit pas de classes `ObjectModel` personnalisées. Il interagit directement avec les objets `Product` et `Configuration` existants de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   `myproductgridpro/views/js/product_grid_admin.js`
    *   **Portée** : Back-office (spécifiquement la page `Catalogue > Produits`).
    *   **Responsabilité** :
        *   Gère la manipulation dynamique du tableau de la liste des produits dans le Back Office de PrestaShop.
        *   Implémente la fonctionnalité de glisser-déposer pour réorganiser les colonnes, permettant aux administrateurs de personnaliser la mise en page.
        *   Gère la visibilité des colonnes (les afficher/masquer en fonction des préférences de l'utilisateur).
        *   Stocke et récupère probablement les préférences de l'utilisateur pour l'ordre et la visibilité des colonnes à l'aide d'appels AJAX ou du stockage local/cookies, qui sont ensuite utilisés par le `AdminProductsController` surchargé pour rendre la grille.
        *   Peut inclure des écouteurs d'événements pour les éléments de l'interface utilisateur qui contrôlent la sélection des colonnes (par exemple, une icône d'engrenage ou un menu déroulant pour basculer les colonnes).

### 4.5 Feuilles de style CSS (`views/css/`)

-   `myproductgridpro/views/css/product_grid_admin.css`
    *   **Portée** : Back-office (spécifiquement la page `Catalogue > Produits`).
    *   **Responsabilité** :
        *   Fournit le style pour la grille de produits améliorée, garantissant que les nouvelles colonnes et les éléments de l'interface utilisateur (comme les poignées de glisser-déposer ou les bascules de colonnes) sont affichés correctement et s'intègrent de manière transparente au thème du Back Office de PrestaShop.
        *   Peut inclure des styles pour les indicateurs de glisser-déposer, les états de colonnes masquées ou des largeurs spécifiques pour les nouvelles colonnes.
        *   Sélecteurs de classes CSS clés que les développeurs peuvent surcharger dans leur thème : Recherchez les classes préfixées par `product-grid-pro` ou similaires, ou les classes spécifiques d'en-tête/cellule de tableau qui pourraient être ciblées pour un style personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module ne semble pas utiliser de fichiers `.tpl` personnalisés d'après l'inventaire fourni. Cela suggère que les modifications apportées à la grille de produits sont principalement réalisées via PHP (dans le contrôleur surchargé) et JavaScript, qui manipule dynamiquement la structure HTML existante générée par les modèles de base de PrestaShop pour le `AdminProductsController`. Le module injecte probablement son JS et son CSS via des hooks comme `displayBackOfficeHeader`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module stocke principalement ses paramètres de configuration (par exemple, l'ordre préféré des colonnes, la visibilité) dans la table `ps_configuration`. Les clés de configuration seraient généralement préfixées par `MYPRODUCTGRIDPRO_` ou similaire.
    *   Il ne crée pas de nouvelles tables de base de données personnalisées.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` du Back Office. | Utilisé pour inclure les actifs `product_grid_admin.js` et `product_grid_admin.css` du module, garantissant qu'ils sont chargés sur la page `AdminProductsController`. |
| `actionAdminProductsControllerSave` (ou hooks `actionAdminController` similaires) | Exécuté lorsqu'un contrôleur d'administration enregistre des données. | Bien que non explicitement listé, le module pourrait utiliser de tels hooks pour enregistrer les préférences de colonnes personnalisées (ordre, visibilité) dans `ps_configuration` lorsqu'un utilisateur administrateur les modifie. |
| `actionAdminProductsListingFieldsModifier` (PrestaShop 1.7+) | Exécuté avant le rendu des champs de la liste de produits. | Ce hook est crucial pour les modules qui modifient le `$this->fields_list` du `AdminProductsController`. Il permet au module d'ajouter, de supprimer ou de modifier dynamiquement les définitions de colonnes. |
| `actionAdminProductsListingResultsModifier` (PrestaShop 1.7+) | Exécuté après la récupération des données de produit mais avant le rendu. | Permet au module de modifier les lignes de données réelles pour les nouvelles colonnes (par exemple, calculer les "Unités vendues" ou la "Dernière vente" si elles ne sont pas directement disponibles à partir de la requête principale du produit). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module "Product Grid Pro - colonnes et mise en page des produits listés", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
"""
