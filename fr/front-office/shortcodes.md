---
title: "Shortcodes - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Shortcodes par MyPresta.eu."
sidebar:
  label: "Shortcodes"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Shortcodes sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/shortcodes.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/shortcodes/)
>
> ---


# Shortcodes

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après avoir installé le module, naviguez vers **Modules > Gestionnaire de modules** et recherchez "Shortcodes". Cliquez sur le bouton "Configurer" pour accéder à ses paramètres.

La page de configuration du module Shortcodes est simple et se concentre sur un seul paramètre crucial :

#### Désactiver tous les shortcodes
-   **Ce que fait ce paramètre :** Il s'agit d'un interrupteur principal qui contrôle si le module traite et remplace les shortcodes sur l'ensemble de votre site web.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (réglé sur "Oui") :* Le module analysera activement votre contenu et les fichiers de votre thème à la recherche de shortcodes reconnus (par exemple, `[products]`, `[categories]`, `[html]`) et les remplacera par le contenu dynamique correspondant. C'est le mode de fonctionnement prévu pour le module.
    -   *Lorsqu'il est désactivé (réglé sur "Non") :* Le module cessera de traiter tous les shortcodes. Tous les shortcodes que vous avez placés dans votre contenu ou les fichiers de votre thème apparaîtront simplement comme du texte brut (par exemple, `[products]` sera visible comme `[products]` pour vos clients) et ne seront pas remplacés par du contenu dynamique.
-   **Valeur recommandée :** **Oui**
-   **Scénario / exemple pour le marchand :**
    -   Vous le réglerez sur "Oui" pour activer la fonctionnalité des shortcodes et afficher votre contenu dynamique.
    -   Vous pourriez le régler temporairement sur "Non" si vous déboguez un problème, effectuez une maintenance, ou si vous souhaitez désactiver tout le contenu dynamique généré par les shortcodes sur votre boutique sans désinstaller le module. N'oubliez pas d'enregistrer vos modifications après avoir basculé ce paramètre.

:::tip
Après avoir modifié des paramètres, cliquez toujours sur le bouton "Enregistrer" pour appliquer vos modifications.
:::

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
|---|---|---|---|
| Page de configuration du module | Désactiver tous les shortcodes | Oui | Contrôle si le module traite et remplace les shortcodes par du contenu dynamique. Réglez sur "Oui" pour activer, "Non" pour désactiver. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes shortcodes apparaissent comme du texte brut (par exemple, `[products]`) au lieu de contenu dynamique. Qu'est-ce qui ne va pas ?**
**R1 :**
1.  **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module "Shortcodes" est installé et activé.
2.  **Vérifier la configuration du module :** Allez sur la page de configuration du module et assurez-vous que "Désactiver tous les shortcodes" est réglé sur **"Oui"**.
3.  **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures).
4.  **Syntaxe correcte du shortcode :** Vérifiez que vous avez tapé le shortcode exactement comme requis, y compris les crochets `[]` et tous les paramètres (par exemple, `[products type="new"]`). Toute faute de frappe l'empêchera d'être traité.

**Q2 : Le contenu dynamique (par exemple, le carrousel de produits) n'est pas stylisé correctement ou semble cassé sur mon thème.**
**R2 :**
Cela indique généralement un conflit CSS ou un style manquant spécifique à votre thème.
1.  **Compatibilité du thème :** Bien que le module fournisse un style de base, les thèmes personnalisés peuvent remplacer ou manquer de styles pour certains éléments.
2.  **Assistance d'un développeur :** Vous pourriez avoir besoin d'un développeur web pour inspecter la page à l'aide des outils de développement du navigateur (F12) afin d'identifier les conflits CSS et d'ajouter des règles CSS personnalisées à votre thème pour garantir que la sortie du shortcode s'intègre visuellement. Le fichier CSS du module (`cmsproductspro.css`) peut servir de point de départ pour référence.

**Q3 : Puis-je utiliser des shortcodes dans des boutiques multilingues ?**
**R3 :** Oui, les shortcodes eux-mêmes sont agnostiques à la langue. Le contenu qu'ils génèrent (par exemple, les noms de produits, les descriptions) sera automatiquement affiché dans la langue sélectionnée par le client, à condition que vos produits et catégories aient des traductions pour cette langue. Lorsque vous placez des shortcodes dans des pages CMS ou des descriptions de produits, assurez-vous d'éditer le contenu pour la bonne langue dans le back office.

**Q4 : J'ai ajouté un shortcode à une nouvelle page CMS, mais il n'apparaît pas sur le front office.**
**R4 :**
1.  **Statut de la page :** Assurez-vous que votre page CMS est activée et visible dans votre menu de navigation ou liée à partir d'une autre page.
2.  **Cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances**).
3.  **Placement du shortcode :** Vérifiez que le shortcode est placé dans une zone de contenu qui est réellement rendue par votre thème pour cette page CMS. Certains thèmes peuvent avoir des blocs de contenu spécifiques.

**Q5 : Quels shortcodes sont disponibles et quels paramètres puis-je utiliser ?**
**R5 :** La documentation du module (ce guide) ou la page de configuration du module (s'il les liste) devrait détailler les shortcodes disponibles. Les shortcodes courants incluent :
-   `[products]` (pour diverses listes de produits comme les nouveaux, les meilleures ventes, les ID spécifiques)
-   `[categories]` (pour afficher des listes de catégories)
-   `[html]` (pour intégrer du HTML personnalisé)
-   `[imageManufacturer]` (pour afficher les images des fabricants)
Vous devrez vous référer à l'implémentation spécifique du module pour les paramètres exacts (par exemple, `limit`, `carousel`, `id`, `type`).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, déboguer ou étendre le module Shortcodes.

### 4.1 Aperçu de l'architecture
Le module Shortcodes (`cmsproductspro`) fonctionne principalement comme un filtre de contenu. Il s'accroche au processus de rendu de la sortie de PrestaShop pour intercepter le contenu HTML avant qu'il ne soit envoyé au navigateur. Il utilise ensuite des expressions régulières pour trouver et remplacer des motifs de shortcodes prédéfinis par du contenu HTML généré dynamiquement. La configuration du module est minimale, se concentrant sur un interrupteur global d'activation/désactivation. La logique de génération de contenu est encapsulée dans la classe principale du module, tirant parti des fonctionnalités de base de PrestaShop pour la récupération des données (produits, catégories, fabricants).

### 4.2 Contrôleurs (`controllers/`)
Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique de configuration et de traitement du contenu est gérée dans le fichier principal du module (`cmsproductspro.php`).

### 4.3 Classes et modèles principaux (`classes/`)
Ce module ne définit **pas** de classes personnalisées ou d'`ObjectModel` dans un répertoire `classes/`. Toute la logique principale réside dans le fichier `cmsproductspro.php`.

### 4.4 Actifs JavaScript (`views/js/`)
Ce module ne contient **pas** de fichiers JavaScript personnalisés. Tout comportement dynamique (comme les carrousels) s'appuierait généralement sur des bibliothèques JavaScript existantes fournies par PrestaShop ou le thème (par exemple, Owl Carousel, Slick Carousel) si la sortie du shortcode inclut de tels composants.

### 4.5 Feuilles de style CSS (`views/css/`)
-   **`cmsproductspro/cmsproductspro.css`**
    *   **Portée :** Style client du front-office.
    *   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style fournit un style de base pour la sortie HTML générée par les shortcodes. Cela inclut :
        *   Grilles et carrousels de produits (par exemple, `.cmsproductspro-products-grid`, `.cmsproductspro-carousel`).
        *   Articles de produits individuels (par exemple, `.cmsproductspro-product-item`, `.cmsproductspro-product-image`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`).
        *   Listes de catégories (par exemple, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`).
        *   Images de fabricants (par exemple, `.cmsproductspro-manufacturer-image`).
        *   Mise en page générale et réactivité pour ces éléments.
    *   **Sélecteurs de classes CSS clés que les développeurs peuvent surcharger :** Les développeurs peuvent cibler des classes comme `.cmsproductspro-products-grid`, `.cmsproductspro-product-item`, `.cmsproductspro-product-name`, `.cmsproductspro-product-price`, `.cmsproductspro-categories-list`, `.cmsproductspro-category-item`, `.cmsproductspro-manufacturer-image` pour personnaliser l'apparence du contenu généré par le shortcode dans leur thème.

### 4.6 Structure des templates Smarty (`views/templates/`)
Le module utilise plusieurs templates Smarty pour rendre le contenu dynamique de divers shortcodes. Ces templates sont situés dans `views/templates/`.

-   **Templates de hook (`views/templates/hook/`)** : Ce module n'utilise pas explicitement un sous-répertoire `hook/` pour ses templates. Les templates sont directement dans `views/templates/` et sont rendus en fonction du shortcode détecté.

-   **Templates d'administration (`views/templates/admin/`)** : Ce module ne contient pas de templates d'administration spécifiques au-delà du formulaire de configuration standard géré par `getContent()`.

-   **Templates front-office (`views/templates/front/`)** :
    *   **`cmsproductspro/categories.tpl`** :
        *   **Objectif :** Rend une liste de catégories, généralement utilisée par un shortcode `[categories]`.
        *   **Variables :** Attend des variables comme `$categories` (un tableau d'objets catégorie), `$display_subcategories`, `$image` etc.
        *   **Sortie :** Génère du HTML pour une grille ou une liste de catégories, potentiellement avec des images et des liens.
    *   **`cmsproductspro/html.tpl`** :
        *   **Objectif :** Rend du contenu HTML brut, utilisé par un shortcode `[html]`.
        *   **Variables :** Attend une variable `$content` contenant la chaîne HTML à afficher.
        *   **Sortie :** Affiche directement le contenu HTML fourni.
    *   **`cmsproductspro/imageManufacturer.tpl`** :
        *   **Objectif :** Affiche l'image d'un fabricant, utilisée par un shortcode `[imageManufacturer]`.
        *   **Variables :** Attend `$manufacturer` (un objet avec les détails du fabricant, y compris le chemin de l'image) et potentiellement `$link` pour la page du fabricant.
        *   **Sortie :** Génère une balise `<img>` pour le logo du fabricant, souvent enveloppée dans un lien.
    *   **`cmsproductspro/productGallery.tpl`** :
        *   **Objectif :** Rend une galerie de produits, potentiellement avec une mise en page ou des fonctionnalités spécifiques. Il peut s'agir d'un template d'affichage de produit plus générique.
        *   **Variables :** Attend `$products` (un tableau d'objets produit) et d'autres options d'affichage.
        *   **Sortie :** Structure HTML pour une galerie de produits.
    *   **`cmsproductspro/products-carousel.tpl`** :
        *   **Objectif :** Rend une liste de produits spécifiquement conçue pour être utilisée dans un composant carrousel.
        *   **Variables :** Attend `$products` (tableau d'objets produit) et potentiellement des options spécifiques au carrousel.
        *   **Sortie :** Structure HTML pour une liste de produits, souvent avec des classes adaptées à une bibliothèque JavaScript de carrousel.
    *   **`cmsproductspro/products.tpl`** :
        *   **Objectif :** Rend une liste ou une grille générale de produits, utilisée par un shortcode `[products]`.
        *   **Variables :** Attend `$products` (tableau d'objets produit) et d'autres options d'affichage comme `$grid_class`, `$item_class`.
        *   **Sortie :** Structure HTML pour une grille ou une liste de produits.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée **pas** de tables de base de données personnalisées. Sa configuration est stockée dans la table `ps_configuration` en utilisant des clés comme `CMSPRODUCTSPRO_HIDE` (pour le paramètre "Désactiver tous les shortcodes").

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `actionOutputHTMLBefore` | Exécuté juste avant que la sortie HTML finale ne soit envoyée au navigateur. | C'est le hook principal où le module intercepte l'ensemble du contenu de la page, recherche les shortcodes et effectue les remplacements. |
| `displayHeader` | Exécuté dans la section `<head>` du HTML. | Utilisé pour inclure les fichiers CSS nécessaires (`cmsproductspro.css`) pour le contenu généré par le shortcode. |
| `actionAjaxDieProductControllerdisplayAjaxQuickviewBefore` | Exécuté avant la méthode `displayAjaxQuickview` dans `ProductController` (pour les modales de vue rapide). | Ce hook garantit que les shortcodes sont également traités et remplacés dans le contenu chargé via AJAX pour les vues rapides de produits, en maintenant la cohérence. |

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Shortcodes", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
