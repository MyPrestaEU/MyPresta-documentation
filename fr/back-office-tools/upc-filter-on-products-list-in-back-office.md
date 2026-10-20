---
title: "Filtre UPC sur la liste des produits dans le back office - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Filtre UPC sur la liste des produits dans le back office' par MyPresta.eu."
sidebar:
  label: "Filtre UPC sur la liste des produits dans le back office - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module UPC filter on products list in back office sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/upc-filter-on-products-list-in-back-office.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/upc-filter-on-products-list-in-back-office/)
>
> ---


# Filtre UPC sur la liste des produits dans le back office

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module est conçu pour être prêt à l'emploi. Il n'a pas d'écran de configuration dédié avec des paramètres à ajuster. Une fois installé, le module intègre automatiquement la colonne et le filtre UPC dans votre liste de produits dans le back office.

Vous trouverez la nouvelle fonctionnalité en naviguant vers :
**Back Office > Catalogue > Produits**

Sur cette page, vous verrez maintenant :

- Une nouvelle colonne intitulée « UPC » affichant le code UPC pour chaque produit.
- Un nouveau champ de filtre en haut de la colonne « UPC », vous permettant de taper un code UPC (ou une partie de celui-ci) pour filtrer la liste des produits.

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois pas la colonne ou le filtre UPC sur ma liste de produits.**
R :
\* **Vider le cache :** La solution la plus courante consiste à vider le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » dans le coin supérieur droit.
\* **Vérifier l'état du module :** Assurez-vous que le module est activé. Allez dans **Modules > Gestionnaire de modules**, recherchez « Filtre UPC sur la liste des produits dans le back office » et vérifiez qu'il est actif.
\* **Compatibilité du thème :** Bien que rare pour les modules de back office, un thème d'administration très personnalisé *pourrait* potentiellement interférer. Si vider le cache ne fonctionne pas, passez temporairement au thème d'administration PrestaShop par défaut pour voir si la colonne apparaît.
\* **Position du module :** Ce module modifie les modèles existants. Assurez-vous que le module est correctement installé et qu'il n'affiche aucune erreur lors de l'installation.

**Q : La colonne UPC est là, mais certains produits n'affichent pas d'UPC.**
R : Ce module affiche simplement le code UPC qui est déjà stocké dans les informations de votre produit. Si un produit n'affiche pas d'UPC, cela signifie que le champ UPC pour ce produit spécifique dans votre catalogue PrestaShop est vide. Vous devrez modifier le produit (Catalogue > Produits > Modifier le produit > onglet Quantités) et y saisir le code UPC.

**Q : Puis-je modifier la position de la colonne UPC ?**
R : Le module intègre la colonne UPC dans une position spécifique au sein du tableau de la liste des produits. Il n'y a pas d'option de configuration dans le module pour modifier sa position. Cela nécessiterait des modifications de modèle personnalisées (voir le Guide du développeur).

**Q : Ce module ajoute-t-il des champs UPC aux produits s'ils n'existent pas ?**
R : Non, ce module suppose que votre installation PrestaShop dispose déjà du champ UPC standard disponible pour les produits (ce qui est le cas par défaut). Il affiche et filtre uniquement en fonction des données que vous avez déjà saisies dans ce champ.

**Q : Ce module ralentira-t-il mon back office ?**
R : Le module est hautement optimisé. Il exploite les mécanismes de filtrage existants de PrestaShop et n'ajoute qu'un simple affichage de colonne. Il ne devrait pas avoir d'impact notable sur les performances de votre liste de produits dans le back office.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters souhaitant comprendre, déboguer ou étendre le module « Filtre UPC sur la liste des produits dans le back office ».

### 4.1 Aperçu de l'architecture

Le module fonctionne principalement en surchargeant des modèles Twig spécifiques utilisés pour la liste du catalogue de produits dans le back office de PrestaShop. Il injecte le HTML nécessaire pour l'en-tête de la colonne UPC et le champ de saisie du filtre, puis modifie le modèle de ligne de produit pour afficher la valeur UPC. La logique de filtrage est gérée par le contrôleur natif de PrestaShop `AdminProducts`, qui reconnaît automatiquement le champ `upc` pour le filtrage une fois qu'il est présent dans le modèle.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit **aucun** contrôleur front-office ou back-office personnalisé. Sa fonctionnalité est obtenue par des surcharges de modèles et en tirant parti de la logique de contrôleur PrestaShop existante.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit **aucune** classe PHP personnalisée ou définition `ObjectModel`. Il interagit directement avec les données de produit PrestaShop existantes.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **aucun** fichier JavaScript personnalisé. La fonctionnalité de filtrage est gérée côté serveur par le contrôleur `AdminProducts` de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **aucun** fichier CSS personnalisé. Il s'appuie sur le style par défaut du back office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module utilise le nouveau moteur de templating Twig introduit dans PrestaShop 1.7+ pour les pages du back office. Il surcharge deux modèles de liste de produits principaux :

- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**

  - **Objectif :** Ce modèle est responsable du rendu de la page principale du catalogue de produits, y compris l'en-tête du tableau et le formulaire de recherche/filtre.
  - **Modification :** Le module injecte un nouvel élément `<th>` pour la colonne « UPC » dans l'en-tête du tableau et un champ de saisie correspondant pour le filtrage dans le formulaire de recherche. Cela permet au champ `upc` d'être reconnu par le contrôleur `AdminProducts` pour le filtrage.
- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**

  - **Objectif :** Ce modèle est responsable du rendu des lignes individuelles du tableau de la liste des produits.
  - **Modification :** Le module ajoute un nouvel élément `<td>` dans la boucle de produit pour afficher la valeur `product.upc` pour chaque produit.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée **aucune** table de base de données personnalisée. Il lit le champ `upc` de la table standard `ps_product`.
- **Table des hooks enregistrés** : Ce module n'enregistre **aucun** hook spécifique au sens traditionnel de PrestaShop (par exemple, `displayHeader`, `actionValidateOrder`). Son intégration est réalisée uniquement par des surcharges de modèles Twig, qui sont une forme de « hooking » implicite dans le processus de rendu.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Filtre UPC sur la liste des produits dans le back office », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module.
"""
