---
title: "Désactiver la réduction de groupe pour des produits spécifiques - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Désactiver la réduction de groupe pour des produits spécifiques' par MyPresta.eu."
sidebar:
  label: "Désactiver la réduction de groupe pour des produits spécifiques - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Disable group discount for specific products sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-for-specific-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/disable-group-discount-for-specific-products/)
>
> ---


# Désactiver la réduction de groupe pour des produits spécifiques

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique du module « Désactiver la réduction de groupe pour des produits spécifiques ». Vous y trouverez tous les paramètres pour contrôler quels produits sont exclus des réductions de groupe.

**Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > « Désactiver la réduction de groupe pour des produits spécifiques » > Configurer

#### 2.1.1 Section « Désactiver la réduction de groupe pour des produits spécifiques »

Cette section contient les paramètres essentiels pour activer ou désactiver la fonctionnalité du module et définir les produits concernés.

-   **Paramètre : Interrupteur Activé / Désactivé**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Il détermine si la logique du module pour désactiver les réductions de groupe est active ou inactive.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque Activé :* Le module vérifiera activement si un produit ou sa catégorie est listé dans vos règles d'exclusion. Si c'est le cas, toutes les réductions de groupe seront ignorées pour ce produit.
        -   *Lorsque Désactivé :* Le module n'interférera pas avec les calculs de réduction de groupe par défaut de PrestaShop. Tous les produits seront soumis aux réductions de groupe si applicables.
    -   **Valeur recommandée :** « Activé » si vous avez l'intention d'utiliser la fonctionnalité du module.
    -   **Scénario / exemple pour le marchand :** Si vous configurez le module pour la première fois ou effectuez une maintenance, vous l'activeriez. Si vous souhaitez temporairement que toutes les réductions de groupe s'appliquent sans désinstaller le module, vous le désactiveriez.
-   **Paramètre : Catégories (Boîte de sélection)**

    -   **Ce que fait ce paramètre :** Cela vous permet de sélectionner des catégories de produits entières dont les produits doivent être exclus des réductions de groupe. Tout produit appartenant à une catégorie sélectionnée ne recevra pas de réductions de groupe.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des catégories sont sélectionnées :* Tous les produits des catégories choisies (et de leurs sous-catégories, selon la structure des catégories de PrestaShop et la manière dont les produits sont assignés) auront les réductions de groupe désactivées.
        -   *Lorsque aucune catégorie n'est sélectionnée :* Les produits ne sont pas exclus en fonction de leur catégorie.
    -   **Valeur recommandée :** Sélectionnez les catégories qui contiennent les produits que vous souhaitez exclure des réductions de groupe.
    -   **Scénario / exemple pour le marchand :** Vous vendez des produits électroniques. Votre catégorie « Nouveautés » contient souvent des articles très demandés. Vous voulez vous assurer que même vos clients grossistes paient le prix fort pour ces nouveaux produits pendant le premier mois. Vous sélectionneriez la catégorie « Nouveautés » ici.
-   **Paramètre : Produits spécifiques (Recherche et saisie de sélection)**

    -   **Ce que fait ce paramètre :** Cela vous permet de rechercher et de sélectionner des produits individuels qui doivent être exclus des réductions de groupe. Cela offre un contrôle plus granulaire que les catégories.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsque des produits spécifiques sont sélectionnés :* Seuls les produits explicitement choisis auront les réductions de groupe désactivées, quelle que soit leur catégorie.
        -   *Lorsque aucun produit spécifique n'est sélectionné :* Les produits ne sont pas exclus en fonction de la sélection individuelle.
    -   **Valeur recommandée :** Sélectionnez les produits spécifiques que vous souhaitez exclure des réductions de groupe.
    -   **Scénario / exemple pour le marchand :** Vous avez une impression d'art en édition limitée (ID Produit 123) et une offre groupée spéciale (ID Produit 456) que vous ne voulez jamais réduire pour aucun groupe de clients. Vous rechercheriez et ajouteriez « Impression d'art (Édition limitée) » et « Offre groupée spéciale » à cette liste.

#### 2.1.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activé / Désactivé | Activé | Interrupteur principal pour activer/désactiver la fonctionnalité du module. |
| Configuration du module | Catégories | Sélectionner les catégories pertinentes | Exclut tous les produits des catégories sélectionnées des réductions de groupe. |
| Configuration du module | Produits spécifiques | Sélectionner les produits pertinents | Exclut les produits sélectionnés individuellement des réductions de groupe. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré le module, mais les réductions de groupe s'appliquent toujours à mes produits exclus. Qu'est-ce qui ne va pas ?**
R :

-   **Le module est-il activé ?** Vérifiez l'interrupteur « Activé / Désactivé » sur la page de configuration du module. Il doit être réglé sur « Activé ».
-   **Avez-vous enregistré vos modifications ?** Cliquez toujours sur le bouton « Enregistrer » après avoir apporté des modifications à la configuration.
-   **Videz votre cache PrestaShop :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
-   **Vérifiez l'affectation produit/catégorie :** Assurez-vous que le produit est correctement affecté à la catégorie que vous avez exclue, ou que vous avez sélectionné le produit exact que vous souhaitez exclure.
-   **Vérifiez les autres modules :** Un autre module de prix ou de réduction pourrait être en conflit. Essayez de désactiver temporairement d'autres modules liés aux réductions pour voir si le problème se résout.

**Q2 : Ce module affectera-t-il mes règles de prix catalogue régulières ou mes prix spécifiques ?**
R : Non, ce module cible spécifiquement les *réductions de groupe*. Il n'interfère pas avec les règles de prix catalogue, les prix spécifiques que vous définissez pour des produits individuels ou les règles de panier (bons de réduction). Il empêche uniquement la réduction en pourcentage supplémentaire appliquée en fonction du groupe d'un client.

**Q3 : Comment ce module gère-t-il les produits dans plusieurs catégories ?**
R : Si un produit se trouve dans plusieurs catégories, et que *n'importe laquelle* de ces catégories est sélectionnée pour l'exclusion dans le module, le produit sera exclu des réductions de groupe. Le module vérifie si le produit *appartient* à une catégorie exclue.

**Q4 : J'utilise un thème personnalisé. Ce module fonctionnera-t-il correctement ?**
R : Oui, ce module fonctionne au niveau du calcul du prix de base et n'introduit aucun nouvel élément front-office ni style complexe qui entrerait généralement en conflit avec les thèmes. Il devrait être entièrement compatible avec n'importe quel thème PrestaShop.

**Q5 : Puis-je exclure des produits pour *certains* groupes mais pas pour d'autres ?**
R : Non, ce module désactive les réductions de groupe pour les produits/catégories sélectionnés *pour tous les groupes de clients*. Si un produit figure sur la liste d'exclusion, aucun groupe de clients ne recevra de réduction sur celui-ci. La fonctionnalité principale de PrestaShop vous permet de définir des réductions de groupe par groupe, mais ce module agit comme une dérogation pour des produits spécifiques, les exemptant de *toute* réduction de groupe.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters souhaitant comprendre, déboguer ou étendre le module « Désactiver la réduction de groupe pour des produits spécifiques ».

### 4.1 Aperçu de l'architecture

Le module fonctionne principalement en surchargeant une classe PrestaShop de base (`Product.php`) pour modifier la logique de calcul du prix. Il s'accroche à la méthode `Product::getPriceStatic()`, qui est centrale à la façon dont PrestaShop détermine le prix final d'un produit. Lorsque cette méthode est appelée, le module vérifie si le produit actuel ou ses catégories associées sont configurés pour être exclus des réductions de groupe. Si c'est le cas, il s'assure que le composant de réduction de groupe du calcul du prix est ignoré.

Le module utilise la classe `Module` standard de PrestaShop pour son interface de configuration et s'appuie sur les entrées de la table `Configuration` pour stocker ses paramètres. Il inclut également un outil de recherche simple pour la sélection de produits dans le back office.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa logique est principalement implémentée via une surcharge de classe et la méthode `getContent()` du fichier de module principal pour la configuration.

### 4.3 Classes et modèles de base (`classes/`)

-   **`exgdisc/override/classes/Product.php`**
    -   **Responsabilité :** C'est le fichier le plus critique du module. Il surcharge la classe `Product` de base pour modifier la méthode `getPriceStatic()`.
    -   **Nom de la classe :** `Product` (surcharge la classe `Product` originale)
    -   **Classe parente :** `ProductCore`
    -   **Logique clé :**
        -   La méthode `getPriceStatic()` surchargée appelle d'abord la méthode `getPriceStatic()` du parent pour obtenir le prix de base.
        -   Elle récupère ensuite la configuration du module (`exgdisc_categories`, `exgdisc_products`) depuis `Configuration::get()`.
        -   Elle vérifie si l'ID du produit actuel (`$id_product`) est dans la liste `exgdisc_products`.
        -   Elle vérifie également si l'une des catégories associées à `$id_product` est dans la liste `exgdisc_categories`.
        -   Si l'une ou l'autre condition est vraie, cela signifie que le produit doit être exclu des réductions de groupe. La méthode recalcule alors le prix, ignorant effectivement le composant de réduction de groupe qui serait normalement appliqué par la méthode `getPriceStatic()` du parent.
        -   La méthode `Product::getPriceStatic()` originale a un paramètre `$use_group_reduction`. La surcharge garantit que même si celui-ci est `true`, la réduction de groupe n'est pas appliquée si le produit est exclu par le module.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`exgdisc/lib/searchTool/views/js/autocomplete.js`**
    -   **Portée :** Back-office (utilisé sur la page de configuration du module).
    -   **Objectif :** Fournit la fonctionnalité d'autocomplétion pour la sélection de produits spécifiques dans le formulaire de configuration du module.
    -   **Logique clé :**
        -   Initialise un champ de saisie d'autocomplétion (ciblant probablement un élément avec un ID spécifique, par exemple, `#product_autocomplete_input`).
        -   Envoie des requêtes AJAX à un contrôleur d'administration PrestaShop (par exemple, `AdminProducts` ou un contrôleur de recherche personnalisé) pour récupérer des suggestions de produits basées sur la saisie de l'utilisateur.
        -   Gère la sélection des produits, les ajoutant à un champ de saisie masqué ou à une liste visuelle sur la page de configuration.
        -   Gère la suppression des produits sélectionnés de la liste.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`exgdisc/lib/searchTool/views/css/autocomplete.css`**
    -   **Portée :** Back-office (style l'outil de recherche d'autocomplétion).
    -   **Objectif :** Fournit le style pour le champ de recherche de produits et la liste des produits sélectionnés sur la page de configuration du module.
    -   **Sélecteurs clés :** Inclut probablement des styles pour la liste déroulante d'autocomplétion, les balises/badges des éléments sélectionnés, et éventuellement le champ de saisie de recherche lui-même. Les développeurs peuvent surcharger ces classes dans leurs thèmes d'administration personnalisés si nécessaire.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`exgdisc/lib/searchTool/views/scripts.tpl`**

    -   **Portée :** Back-office (inclus dans la page de configuration du module).
    -   **Objectif :** Rend la structure HTML pour le champ de recherche de produits et la zone où les produits sélectionnés sont affichés. Il inclut également probablement les appels JavaScript nécessaires pour initialiser le script `autocomplete.js`.
    -   **Éléments clés :** Champ de saisie pour la recherche de produits, un conteneur pour afficher les produits sélectionnés (par exemple, sous forme de balises ou d'éléments de liste), et des champs de saisie masqués pour stocker les ID des produits sélectionnés.
-   **`exgdisc/views/script.tpl`**

    -   **Portée :** Back-office (inclus dans la page de configuration du module).
    -   **Objectif :** Ce template est probablement utilisé pour générer du JavaScript ou du CSS supplémentaire spécifique au formulaire de configuration principal du module, potentiellement lié à la validation du formulaire ou aux éléments d'interface utilisateur dynamiques. Compte tenu du hook `ActionAdminControllerSetMedia`, il pourrait être utilisé pour enregistrer des actifs.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table de base de données personnalisée.
    -   Tous les paramètres de configuration sont stockés dans la table `ps_configuration` :
        -   `exgdisc_categories` : Stocke une chaîne sérialisée ou une liste d'ID de catégories séparés par des virgules à exclure.
        -   `exgdisc_products` : Stocke une chaîne sérialisée ou une liste d'ID de produits séparés par des virgules à exclure.
        -   `mypresta_updates`, `update_`, `updatev_` : Liés au mécanisme de mise à jour de MyPresta.eu.
        -   `exgdisc_groups` : (Non explicitement utilisé dans les informations fournies, mais pourrait être un paramètre hérité ou futur pour les exclusions spécifiques aux groupes).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration est chargé et que ses médias (JS/CSS) sont définis. | Utilisé par le module pour charger son JavaScript (`autocomplete.js`) et son CSS (`autocomplete.css`) du back-office pour la page de configuration, garantissant le fonctionnement de l'outil de recherche de produits. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Désactiver la réduction de groupe pour des produits spécifiques », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir le fonctionnement optimal du module avec votre boutique PrestaShop.
"""
