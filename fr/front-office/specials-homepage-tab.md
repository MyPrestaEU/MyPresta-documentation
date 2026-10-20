---
title: "Onglet Promotions sur la page d'accueil - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Onglet Promotions sur la page d'accueil par MyPresta.eu."
sidebar:
  label: "Onglet Promotions sur la page d'accueil - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Specials Homepage Tab sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/specials-homepage-tab.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/specials-homepage-tab/)
>
> ---


# Onglet Promotions sur la page d'accueil

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et sont suffisantes pour ce module.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Onglet Promotions sur la page d'accueil » pour accéder à ses paramètres.

#### Paramètres et options :

- **Nombre de produits**

  - **Ce que fait ce paramètre :** Il contrôle le nombre de produits en promotion qui seront affichés dans l'onglet « Promotions » sur votre page d'accueil.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 12) :* Plus de produits seront visibles dans l'onglet, offrant aux clients un plus grand choix d'offres. Cela peut nécessiter plus de défilement ou de pagination selon votre thème.
    - *Lorsqu'il est défini sur un nombre plus faible (par exemple, 4) :* Moins de produits seront affichés, créant un affichage plus concis. Cela peut être utile si vous souhaitez mettre en évidence uniquement vos meilleures offres ou garder la page d'accueil propre.
  - **Valeur recommandée :** Commencez par un nombre qui s'intègre bien à la conception de votre thème (par exemple, 8 ou 12) et ajustez en fonction du nombre d'offres spéciales que vous avez généralement et de l'espace que vous souhaitez qu'elles occupent.
  - **Scénario / exemple de marchand :** Si vous avez de nombreux produits en promotion et que vous souhaitez présenter de la variété, définissez-le sur 12. Si vous préférez une page d'accueil minimaliste et ne souhaitez mettre en évidence que quelques offres phares, définissez-le sur 4.
- **Produits aléatoires**

  - **Ce que fait ce paramètre :** Il détermine si les produits en promotion affichés dans l'onglet sont présentés dans un ordre fixe (par exemple, par ID, date d'ajout) ou dans un ordre aléatoire à chaque chargement de la page.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* Chaque fois qu'un client visite votre page d'accueil, l'ordre des produits dans l'onglet « Promotions » sera aléatoire. Cela garantit que différents produits obtiennent de la visibilité et empêche les mêmes quelques articles d'être toujours en haut.
    - *Lorsqu'il est désactivé (NON) :* Les produits seront affichés dans un ordre cohérent et non aléatoire (généralement par ID de produit ou date de création, selon le tri par défaut de PrestaShop pour les promotions). Cela signifie que les mêmes produits apparaîtront toujours en premier.
  - **Valeur recommandée :** **OUI**. La randomisation des produits est généralement recommandée pour donner à toutes vos offres spéciales une chance équitable d'être vues et pour garder la page d'accueil fraîche pour les clients qui reviennent.
  - **Scénario / exemple de marchand :** Si vous avez 20 produits en promotion mais n'en affichez que 8, l'activation de « Produits aléatoires » garantit qu'au fil du temps, les 20 produits apparaîtront finalement dans l'onglet, plutôt que seulement les 8 premiers.

#### Autres clés de configuration (paramètres internes de PrestaShop) :

Le module interagit également avec plusieurs clés de configuration PrestaShop. Bien que celles-ci ne soient pas directement configurables dans le module lui-même, comprendre leur objectif aide au dépannage ou à la personnalisation avancée :

- `PS_CATALOG_MODE` : Si votre boutique est en mode catalogue (pas de prix, pas d'ajout au panier), les prix spéciaux ne seront pas pertinents.
- `PS_LANG_DEFAULT` : La langue par défaut de votre boutique, utilisée pour récupérer les noms et descriptions des produits.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Détermine si les employés peuvent changer la langue des formulaires dans le back office.
- `PS_TAX_ADDRESS_TYPE` : Comment les taxes sont calculées (par exemple, en fonction de l'adresse de livraison ou de facturation).
- `PS_COUNTRY_DEFAULT` : Le pays par défaut de votre boutique, impactant les calculs de taxes et d'expédition.
- `PS_NB_DAYS_NEW_PRODUCT` : Le nombre de jours pendant lesquels un produit est considéré comme « nouveau ». (Non directement lié aux promotions, mais souvent trouvé dans les modules qui listent des produits).

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Nombre de produits | 8-12 (Adapter au thème) | Définit le nombre de produits en promotion affichés dans l'onglet. |
| Configuration du module | Produits aléatoires | OUI | Randomise l'ordre des produits dans l'onglet pour un affichage frais. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Mon onglet « Promotions » est vide ou n'affiche aucun produit, mais j'ai des produits en promotion.**

- **R :** Tout d'abord, assurez-vous que vos produits sont correctement marqués comme « en promotion » dans leurs paramètres de produit dans le back office de PrestaShop (sous l'onglet « Prix », assurez-vous que les « Prix spécifiques » sont configurés et actifs). Vérifiez également le paramètre « Nombre de produits » dans la configuration du module ; s'il est défini sur 0, aucun produit ne s'affichera. Enfin, videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**).

**Q2 : L'onglet « Promotions » n'apparaît pas du tout sur ma page d'accueil.**

- **R :**
  1.  **Module activé :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module « Onglet Promotions sur la page d'accueil » est activé.
  2.  **Accroché correctement :** Le module utilise `displayHomeTab` et `displayHomeTabContent`. Votre thème doit prendre en charge ces hooks pour que l'onglet apparaisse. La plupart des thèmes PrestaShop standard le font. Si vous utilisez un thème fortement personnalisé, il se peut qu'il n'appelle pas ces hooks.
  3.  **Cache :** Videz toujours le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**) après avoir installé ou configuré des modules.
  4.  **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, des thèmes très anciens ou hautement personnalisés peuvent nécessiter des ajustements mineurs. Si les problèmes persistent, contactez le support MyPresta.eu.

**Q3 : Les produits de l'onglet « Promotions » n'ont pas l'air bien ou ne correspondent pas au design de mon thème.**

- **R :** Le module utilise le style existant de votre thème pour les listes de produits. Si les produits ont l'air étranges, il s'agit généralement d'un problème CSS avec votre thème plutôt qu'avec le module lui-même.
  - **Vérifier le CSS du thème :** Inspectez le CSS de votre thème pour les styles de liste de produits.
  - **CSS personnalisé :** Vous devrez peut-être ajouter du CSS personnalisé au fichier `custom.css` de votre thème (si disponible) ou modifier directement la feuille de style de votre thème pour ajuster l'apparence.
  - **Réactivité mobile :** Testez sur différents appareils. Si l'affichage est correct sur ordinateur de bureau mais pas sur mobile, il s'agit d'un problème de réactivité avec le CSS de votre thème.

**Q4 : Puis-je changer le titre de l'onglet « Promotions » (par exemple, en « Offres » ou « Soldes ») ?**

- **R :** Le module utilise la traduction PrestaShop par défaut pour « Promotions ». Pour le modifier, vous iriez généralement dans **International > Traductions**, sélectionneriez « Traductions des modules installés », choisiriez votre thème, puis trouveriez le module « Onglet Promotions sur la page d'accueil ». Vous pourrez alors modifier la traduction du titre de l'onglet.

**Q5 : Pourquoi certains produits en promotion n'apparaissent-ils pas dans l'onglet ?**

- **R :**
  1.  **Limite du nombre de produits :** Vérifiez le paramètre « Nombre de produits » dans la configuration du module. Si vous avez plus de promotions que cette limite, seul le premier ensemble (ou aléatoire, si activé) s'affichera.
  2.  **Visibilité du produit :** Assurez-vous que le produit est actif, visible et qu'un prix spécifique réel est configuré (pas seulement une réduction de prix régulière).
  3.  **Cache :** Videz le cache de votre PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Onglet Promotions sur la page d'accueil » (`blockspecialstab`) est un module PrestaShop léger principalement axé sur l'affichage en front-office. Il adhère à l'architecture standard des modules PrestaShop, tirant parti des hooks pour injecter du contenu dans la page d'accueil. Il n'introduit pas de contrôleurs, de modèles ou de JavaScript/CSS complexes personnalisés au-delà de ce qui est nécessaire pour le templating de base. Sa fonctionnalité principale tourne autour de la récupération des produits avec des prix spécifiques et de leur rendu dans une structure d'onglet.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'inclut **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est encapsulée dans la classe principale du module (`blockspecialstab.php`).

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit **pas** de classes personnalisées ou de définitions `ObjectModel`. Il s'appuie sur les classes `Product` et `SpecificPrice` de PrestaShop pour récupérer les données des produits.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés. La fonctionnalité de commutation d'onglets et l'affichage des produits sont gérés par le JavaScript existant du thème (par exemple, jQuery, Bootstrap JS) qui gère généralement les interactions `displayHomeTab` et `displayHomeTabContent`.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **pas** de fichiers CSS personnalisés. Il est conçu pour hériter du style du thème PrestaShop actif pour les listes de produits, garantissant une intégration transparente. Les développeurs doivent se référer au CSS de leur thème pour le style des grilles de produits et des onglets.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise deux modèles Smarty principaux, tous deux situés dans le répertoire `views/templates/hook/`, pour rendre l'onglet et son contenu.

-   **`blockspecialstab/views/templates/hook/blockspecialstab.tpl`**

    -   **Objectif :** Ce modèle est responsable du rendu de l'*en-tête* de l'onglet « Promotions » qui apparaît à côté d'autres onglets (par exemple, « Nouveautés »).
    -   **Hook :** Principalement rendu via `displayHomeTab`.
    -   **Sortie :** Génère généralement un élément `<li>` contenant une balise `<a>` avec un lien vers le contenu de l'onglet (par exemple, `#blockspecialstab`).
    -   **Éléments clés pour les développeurs :**
        -   `id="home-page-tabs"` : Le conteneur pour tous les onglets de la page d'accueil (généralement dans le thème).
        -   `id="blockspecialstab"` : L'ID de l'onglet lui-même, utilisé pour le lier à son contenu.
        -   `{l s='Specials' mod='blockspecialstab'}` : Le texte traduisible pour le titre de l'onglet.
-   **`blockspecialstab/views/templates/hook/blockspecialstabcontents.tpl`**

    -   **Objectif :** Ce modèle rend le *contenu* qui apparaît lorsque l'onglet « Promotions » est cliqué. Il contient la liste réelle des produits en promotion.
    -   **Hook :** Principalement rendu via `displayHomeTabContent`.
    -   **Sortie :** Génère généralement un élément `<div>` contenant une boucle qui itère sur la variable `$products` (passée depuis le module) et affiche chaque produit en utilisant un partiel de liste de produits commun du thème (par exemple, `product-list.tpl` ou un extrait similaire).
    -   **Éléments clés pour les développeurs :**
        -   `id="blockspecialstab"` : L'ID du bloc de contenu, correspondant à l'en-tête de l'onglet.
        -   `{$products}` : Un tableau d'objets `Product` (ou de tableaux associatifs représentant des produits) passé depuis le module, contenant des détails comme l'ID, le nom, le prix, l'image, etc.
        -   `{include file='catalog/_partials/miniatures/product.tpl' product=$product}` (exemple pour PS 1.7/8) : Le module utilise généralement un partiel de thème standard pour rendre chaque produit, garantissant un style cohérent. Les développeurs doivent vérifier le fichier `_partials/miniatures/product.tpl` ou `product-list.tpl` de leur thème pour savoir comment les produits individuels sont rendus.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne crée aucune table SQL personnalisée.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` en utilisant des clés comme `BLOCKSTAB_NB_CACHES` (hérité), `BLOCKSTABS_NB_CACHES` (actuel) et `BLOCKSTABS_RAND`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHomeTab` | Rendu dans la zone de navigation des onglets de la page d'accueil. | Injecte l'en-tête de l'onglet « Promotions » (`blockspecialstab.tpl`) dans la liste principale des onglets de la page d'accueil. |
| `displayHomeTabContent` | Rendu dans la zone de contenu de la page d'accueil, correspondant à l'onglet. | Injecte la liste des produits en promotion (`blockspecialstabcontents.tpl`) lorsque l'onglet « Promotions » est actif. |
| `addproduct` | Après l'ajout d'un produit. | Vide le cache interne du module pour s'assurer que les nouveaux produits sont pris en compte pour les promotions. |
| `updateproduct` | Après la mise à jour d'un produit. | Vide le cache interne du module pour refléter les changements de prix ou de statut des produits. |
| `deleteproduct` | Après la suppression d'un produit. | Vide le cache interne du module pour supprimer les produits supprimés des promotions. |
| `displayAddProduct` | (Hook hérité, souvent utilisé pour les formulaires d'administration) | Vide le cache interne du module. |
| `displayUpdateProduct` | (Hook hérité, souvent utilisé pour les formulaires d'administration) | Vide le cache interne du module. |
| `displayDeleteProduct` | (Hook hérité, souvent utilisé pour les formulaires d'administration) | Vide le cache interne du module. |

Les hooks `addproduct`, `updateproduct`, `deleteproduct`, `displayAddProduct`, `displayUpdateProduct` et `displayDeleteProduct` sont principalement utilisés pour déclencher un vidage du cache au sein du module. Cela garantit que la liste des produits spéciaux affichés sur la page d'accueil est toujours à jour lorsque les informations sur les produits (en particulier les prix ou le statut) changent.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Onglet Promotions sur la page d'accueil », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
