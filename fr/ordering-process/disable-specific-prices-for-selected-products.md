---
title: "Désactiver les prix spécifiques pour les produits sélectionnés - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Désactiver les prix spécifiques pour les produits sélectionnés' par MyPresta.eu."
sidebar:
  label: "Désactiver les prix spécifiques pour les produits sélectionnés - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Disable specific prices for selected products sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/disable-specific-prices-for-selected-products/)
>
> ---


# Désactiver les prix spécifiques pour les produits sélectionnés

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres. C'est l'écran de configuration principal et unique pour ce module.

#### **Paramètres généraux**

- **Désactiver les prix spécifiques pour les produits sélectionnés**
  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Le module empêchera activement l'application des prix spécifiques aux produits et catégories que vous sélectionnez ci-dessous.
    - *Lorsqu'désactivé (NON) :* Le module sera inactif. Tous les prix spécifiques et les règles de prix catalogue s'appliqueront à tous les produits normalement, quelles que soient vos sélections dans les champs « Catégories » ou « Produits spécifiques ».
  - **Valeur recommandée :** **OUI** si vous avez l'intention d'utiliser la fonctionnalité du module pour exclure des produits des remises. **NON** si vous souhaitez le désactiver temporairement sans perdre vos configurations enregistrées.
  - **Scénario / exemple marchand :** Vous venez de lancer une nouvelle gamme de produits premium et souhaitez vous assurer qu'ils ne sont jamais remisés. Vous activez ce paramètre, puis ajoutez ces produits à la liste d'exclusion.

#### **Critères d'exclusion**

- **Catégories**

  - **Ce que fait ce paramètre :** Ce champ vous permet de sélectionner des catégories de produits entières dont les produits doivent être exclus des prix spécifiques.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des catégories sont sélectionnées :* Tous les produits appartenant aux catégories sélectionnées (y compris les sous-catégories, selon la structure des catégories de PrestaShop et la manière dont les prix spécifiques sont appliqués) auront les prix spécifiques désactivés.
    - *Lorsqu'aucune catégorie n'est sélectionnée :* Seuls les produits explicitement listés dans le champ « Produits spécifiques » seront affectés.
  - **Valeur recommandée :** Sélectionnez les catégories qui contiennent des produits que vous souhaitez constamment protéger des remises, tels que « Nouveautés », « Articles de luxe » ou « Liquidation (si vous ne souhaitez appliquer que des remises manuelles) ».
  - **Scénario / exemple marchand :** Vous avez une catégorie « Marques Premium ». En la sélectionnant ici, tous les produits de cette catégorie seront automatiquement exclus des calculs de prix spécifiques, vous évitant de lister chaque produit individuellement.
- **Produits spécifiques**

  - **Ce que fait ce paramètre :** Ce champ vous permet de rechercher et de sélectionner des produits individuels qui doivent être exclus des prix spécifiques. Il utilise un outil de recherche avec auto-complétion pour vous aider à trouver rapidement des produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des produits sont sélectionnés :* Les produits individuels choisis auront les prix spécifiques désactivés, quelle que soit leur catégorie.
    - *Lorsqu'aucun produit n'est sélectionné :* Seuls les produits des « Catégories » sélectionnées seront affectés.
  - **Valeur recommandée :** Utilisez ceci pour les articles individuels qui ne rentrent pas dans une exclusion de catégorie plus large, ou pour des best-sellers spécifiques que vous souhaitez conserver au prix fort.
  - **Scénario / exemple marchand :** Vous avez quelques gadgets très demandés qui se vendent toujours bien au prix fort. Vous recherchez « iPhone 15 » et « Samsung Galaxy S24 » et les ajoutez à cette liste pour vous assurer qu'ils ne sont jamais remisés par des prix spécifiques.

#### **Enregistrement de vos modifications**

Après avoir apporté des modifications aux paramètres, n'oubliez pas de cliquer sur le bouton **« Enregistrer »** en bas de la page de configuration pour les appliquer.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Désactiver les prix spécifiques pour les produits sélectionnés | OUI | Interrupteur principal pour activer/désactiver la fonctionnalité du module. OUI signifie que les exclusions sont actives. |
| Page de configuration du module | Catégories | Aucune sélectionnée | Sélectionnez les catégories dont les produits seront exclus des prix spécifiques. |
| Page de configuration du module | Produits spécifiques | Aucun sélectionné | Recherchez et sélectionnez des produits individuels à exclure des prix spécifiques. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré le module, mais les prix spécifiques s'appliquent toujours à mes produits exclus. Qu'est-ce qui ne va pas ?**
R1 :

- **Vérifier l'état du module :** Tout d'abord, assurez-vous que le paramètre « Désactiver les prix spécifiques pour les produits sélectionnés » sur la page de configuration du module est réglé sur **OUI (Activé)**.
- **Vérifier les exclusions :** Vérifiez à nouveau que les produits ou catégories spécifiques que vous souhaitez exclure sont correctement sélectionnés dans les paramètres du module. Utilisez la fonction de recherche avec soin pour les produits.
- **Vider le cache :** PrestaShop met souvent en cache les informations de prix. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite. Videz également le cache de votre navigateur.
- **Priorité des prix spécifiques :** Assurez-vous que la règle de prix spécifique que vous testez ne remplace pas le module d'une manière ou d'une autre. Ce module fonctionne en remplaçant le calcul des prix spécifiques de base de PrestaShop. Si vous avez d'autres modules qui modifient également les prix, il pourrait y avoir un conflit. Essayez de désactiver temporairement d'autres modules liés aux prix pour diagnostiquer.

**Q2 : Ce module affectera-t-il mes règles de panier (bons de réduction) ?**
R2 : Oui, indirectement. Ce module empêche l'application de prix spécifiques aux produits sélectionnés. Si une règle de panier (bon de réduction) offre une remise qui *dépend* ou interagit avec le mécanisme de prix spécifiques de PrestaShop (par exemple, une remise en pourcentage qui calcule en fonction du prix actuel du produit *après* les prix spécifiques), alors les produits exclus ne recevront pas cette réduction de prix spécifique avant l'application du bon de réduction. Le bon de réduction s'appliquera alors au prix de base du produit (ou à son prix après d'autres remises non spécifiques).

**Q3 : Ce module fonctionne-t-il avec les configurations multi-boutiques ?**
R3 : La configuration du module est généralement globale ou liée au contexte dans lequel vous vous trouvez lors de sa configuration. Si vous avez une configuration multi-boutiques, testez minutieusement pour vous assurer que les exclusions s'appliquent comme prévu dans toutes les boutiques concernées. Le mécanisme d'`override` de PrestaShop s'applique généralement globalement, mais les règles de prix spécifiques elles-mêmes peuvent être spécifiques à la boutique.

**Q4 : J'ai ajouté un nouveau produit à une catégorie exclue, mais il reçoit toujours des prix spécifiques. Pourquoi ?**
R4 :

- **Cache :** Videz toujours votre cache PrestaShop (**Paramètres avancés > Performances**) après avoir apporté des modifications aux catégories ou aux produits, surtout si vous ajoutez de nouveaux articles ou les déplacez entre les catégories.
- **Structure des catégories :** Assurez-vous que la règle de prix spécifique n'est pas appliquée d'une manière qui contourne l'exclusion de catégorie (par exemple, une règle pour « tous les produits » qui ne respecte pas la hiérarchie des catégories). Le module devrait intercepter le calcul du prix spécifique quoi qu'il arrive, mais le cache est souvent le coupable.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Désactiver les prix spécifiques pour les produits sélectionnés » tire parti du système d'override de PrestaShop pour modifier la logique de prix de base. Plus précisément, il surcharge les classes `Product` et `SpecificPrice` pour injecter sa logique d'exclusion directement dans le processus de calcul des prix. Cela garantit que lorsque PrestaShop tente de déterminer le prix d'un produit, le module vérifie d'abord si le produit ou sa catégorie figure sur la liste d'exclusion, et si c'est le cas, il empêche l'application des prix spécifiques. Le module utilise une structure de module PrestaShop standard, avec un fichier de module principal, des overrides et des `views` pour les ressources et les templates.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Sa configuration est gérée directement dans la méthode `getContent()` du fichier de module principal, et sa fonctionnalité principale est implémentée via des overrides de classe.

### 4.3 Classes et modèles de base (`classes/`)

- **`exsp/override/classes/index.php`** :

  - Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher l'affichage du contenu du répertoire. Il n'a aucun impact fonctionnel sur la logique du module.
- **`exsp/override/classes/Product.php`** :

  - **Nom de la classe et classe parente** : `Product` (surcharge la classe `Product` de base de PrestaShop).
  - **Responsabilité** : Cette surcharge est le mécanisme principal pour intercepter les calculs de prix des produits. Elle modifie la méthode `getPrice()` (ou les méthodes associées) pour vérifier si le produit actuel (ou sa catégorie) est configuré pour l'exclusion. Si c'est le cas, le composant de prix spécifique du calcul est ignoré, garantissant que le prix de base du produit est renvoyé sans aucune réduction de prix spécifique. Ceci est crucial pour empêcher l'application des prix spécifiques au niveau du produit.
  - **Méthodes publiques clés** : La méthode `getPrice()` surchargée (ou des méthodes de calcul de prix similaires au sein de la classe `Product`) contiendra la logique pour vérifier les valeurs de configuration `exsp_categories` et `exsp_products`.
- **`exsp/override/classes/SpecificPrice.php`** :

  - **Nom de la classe et classe parente** : `SpecificPrice` (surcharge la classe `SpecificPrice` de base de PrestaShop).
  - **Responsabilité** : Cette surcharge a un impact direct sur la manière dont les prix spécifiques sont récupérés et appliqués. Elle modifie des méthodes comme `getSpecificPrice()` ou `getSpecificPrices()` pour filtrer ou ignorer les règles de prix spécifiques pour les produits qui figurent sur la liste d'exclusion. Cela agit comme une couche de défense secondaire, garantissant que même si une règle de prix spécifique existe, elle ne sera pas prise en compte pour les produits exclus.
  - **Méthodes publiques clés** : Les méthodes surchargées liées à la récupération ou à l'application des prix spécifiques incorporeront des vérifications par rapport aux listes d'exclusion du module.

### 4.4 Ressources JavaScript (`views/js/`)

- **`exsp/lib/searchTool/views/js/autocomplete.js`** :

  - **Portée** : Back-office (page de configuration du module).
  - **Description** : Ce script fournit la fonctionnalité d'auto-complétion pour le champ de saisie « Produits spécifiques » sur la page de configuration du module. Il utilise probablement AJAX pour interroger la base de données de produits de PrestaShop au fur et à mesure que l'utilisateur tape, suggérant des noms de produits correspondants. Il gère l'affichage des suggestions et la sélection des produits à ajouter à la liste d'exclusion.
  - **Écouteurs d'événements** : Événements `keyup` sur l'entrée de recherche de produit, événements `click` sur les suggestions d'auto-complétion.
  - **Manipulation du DOM** : Crée et met à jour dynamiquement la liste de suggestions, ajoute les produits sélectionnés à une entrée cachée ou à une zone d'affichage.
- **`exsp/views/js/exsp.js`** :

  - **Portée** : Back-office (page de configuration du module).
  - **Description** : Il s'agit du fichier JavaScript principal pour l'interface de configuration du module. Il gère l'initialisation de l'outil de recherche avec auto-complétion, gère l'affichage et la suppression des produits/catégories sélectionnés, et potentiellement effectue d'autres interactions d'interface utilisateur spécifiques aux paramètres du module.
  - **Écouteurs d'événements** : Événements `click` pour la suppression des produits/catégories sélectionnés, potentiellement des événements `change` pour l'interrupteur principal d'activation/désactivation.
  - **Manipulation du DOM** : Gère la représentation visuelle des catégories et produits sélectionnés, met à jour les champs de saisie cachés qui stockent les valeurs de configuration.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`exsp/lib/searchTool/views/css/autocomplete.css`** :
  - **Portée** : Back-office (page de configuration du module).
  - **Description** : Cette feuille de style fournit le style visuel pour le champ de recherche avec auto-complétion et sa liste de suggestions. Elle définit l'apparence de la boîte de recherche, des suggestions déroulantes et potentiellement les états de survol/actif pour une meilleure expérience utilisateur.
  - **Composants d'interface utilisateur principaux** : `.autocomplete-container`, `.autocomplete-suggestions`, `.autocomplete-suggestion`.
  - **Sélecteurs de classe CSS clés** : `.exsp-product-search-input`, `.exsp-selected-item`, `.exsp-remove-item`.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **`exsp/lib/searchTool/views/scripts.tpl`** :

  - **Portée** : Back-office (page de configuration du module).
  - **Description** : Ce template inclut probablement les fichiers JavaScript et CSS nécessaires pour l'outil de recherche avec auto-complétion, ou il pourrait contenir du JavaScript en ligne pour initialiser le widget d'auto-complétion avec des paramètres spécifiques (par exemple, l'URL AJAX pour la recherche de produits).
  - **Rendu dans** : Hook `ActionAdminControllerSetMedia` ou directement dans `getContent()`.
- **`exsp/views/script.tpl`** :

  - **Portée** : Back-office (page de configuration du module).
  - **Description** : Ce template est responsable du rendu du formulaire de configuration principal du module. Il inclut la structure HTML pour l'interrupteur d'activation/désactivation, le champ de sélection de catégorie et le champ de recherche de produit avec son affichage associé pour les produits sélectionnés. Il inclut également probablement les scripts `exsp.js` et `autocomplete.js`.
  - **Rendu dans** : Méthode `getContent()` de `exsp.php`.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration (état activé, catégories exclues, produits exclus) dans la table `ps_configuration` de PrestaShop.
    - `exsp_categories` : Stocke un tableau sérialisé ou une liste d'ID de catégories séparés par des virgules à exclure.
    - `exsp_products` : Stocke un tableau sérialisé ou une liste d'ID de produits séparés par des virgules à exclure.
    - `exsp_enabled` : Stocke l'état activé/désactivé du module (par exemple, `1` pour activé, `0` pour désactivé).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration est chargé, avant que son contenu ne soit rendu. | Utilisé pour enregistrer et inclure les ressources JavaScript et CSS du module (par exemple, pour l'outil de recherche avec auto-complétion) sur la page de configuration du module. |
| (Hooks implicites via Overrides) | Pendant le calcul du prix du produit (`Product::getPrice()`) et la récupération des prix spécifiques (`SpecificPrice::getSpecificPrices()`). | La fonctionnalité principale du module est implémentée en surchargeant les classes `Product` et `SpecificPrice` de PrestaShop. Cela signifie que la logique du module est exécutée chaque fois que ces méthodes de base sont appelées, se « branchant » efficacement sur le processus de calcul des prix sans enregistrer explicitement un hook `display` ou `action`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Désactiver les prix spécifiques pour les produits sélectionnés », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité du module.
