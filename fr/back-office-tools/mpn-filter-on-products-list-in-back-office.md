---
title: "Filtre MPN sur la liste de produits dans le back office - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Filtre MPN sur la liste de produits dans le back office' par MyPresta.eu."
sidebar:
  label: "Filtre MPN sur la liste de produits dans le back office - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module MPN filter on products list in back office sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/mpn-filter-on-products-list-in-back-office.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/mpn-filter-on-products-list-in-back-office/)
>
> ---


# Filtre MPN sur la liste de produits dans le back office

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et habituellement activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module est conçu pour être "plug-and-play". Il n'a pas d'écran de configuration dédié avec des paramètres à ajuster. Lors de l'installation, le module intègre automatiquement la colonne MPN et les capacités de filtrage dans votre liste de produits.

Vous verrez un bouton "Configurer" standard après l'installation, mais cliquer dessus affichera généralement un simple message indiquant que le module est actif et ne nécessite aucune configuration supplémentaire.

**Comment utiliser le module après l'installation :**

1. Naviguez vers **Catalogue > Produits** dans votre back office PrestaShop.
2. Vous verrez maintenant une nouvelle colonne intitulée "MPN" dans votre liste de produits.
3. Vous pouvez cliquer sur l'en-tête de colonne "MPN" pour trier vos produits par MPN dans l'ordre croissant ou décroissant.
4. Au-dessus de la liste de produits, dans la section de filtre, vous trouverez un nouveau champ de saisie sous la colonne "MPN". Vous pouvez taper un MPN (ou une partie d'un MPN) dans ce champ et appuyer sur Entrée ou cliquer sur le bouton "Filtrer" pour filtrer votre liste de produits par ce MPN.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | (Aucun paramètre configurable) | N/A | Le module fonctionne automatiquement après l'installation, ajoutant la colonne MPN et le filtre à Catalogue > Produits. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois pas la colonne MPN dans ma liste de produits.**
R : Tout d'abord, assurez-vous que vous êtes sur la page "Catalogue > Produits" dans votre back office PrestaShop. Si elle n'est toujours pas visible, essayez de vider le cache de votre PrestaShop :
1. Allez dans **Paramètres avancés > Performances**.
2. Cliquez sur "Vider le cache" dans le coin supérieur droit.
3. Videz également le cache de votre navigateur.
4. Si le problème persiste, assurez-vous que le module est activé dans le Gestionnaire de modules.

**Q : Puis-je utiliser ce module pour ajouter le MPN au front office pour les clients ?**
R : Non, ce module est strictement destiné à l'administration du back office. Il ne modifie pas le front office et n'affiche pas les MPN aux clients. Vous auriez besoin d'un module séparé ou d'un développement personnalisé pour l'affichage du MPN en front office.

**Q : Ce module crée-t-il de nouveaux champs de base de données pour le MPN ?**
R : Non, PrestaShop dispose déjà d'un champ `mpn` dans la table `ps_product`. Ce module rend simplement ce champ existant visible et filtrable dans la liste de produits du back office. Il n'ajoute pas de nouvelles tables ou champs de base de données.

**Q : Le filtre ne fonctionne pas, ou la colonne ne trie pas correctement.**
R : Cela pourrait être un problème de cache ou un conflit avec un autre module qui modifie la liste de produits.
1. Videz le cache de PrestaShop (comme décrit ci-dessus).
2. Si vous avez d'autres modules qui personnalisent fortement la page "Catalogue > Produits", essayez de les désactiver temporairement un par un pour identifier un conflit.
3. Assurez-vous que votre version de PrestaShop est entièrement compatible avec la version du module que vous avez téléchargée.

**Q : Comment puis-je saisir ou modifier le MPN d'un produit ?**
R : Vous modifiez le MPN directement sur la page d'édition du produit :
1. Allez dans **Catalogue > Produits**.
2. Cliquez sur "Modifier" à côté du produit que vous souhaitez modifier.
3. Naviguez vers l'onglet "Quantités" (ou "Paramètres de base" dans les versions plus anciennes).
4. Vous y trouverez le champ "MPN (Manufacturer Part Number)". Saisissez ou mettez à jour la valeur et enregistrez le produit. Le nouveau MPN apparaîtra alors dans la liste de produits.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "Filtre MPN sur la liste de produits dans le back office" est un module PrestaShop léger principalement conçu pour étendre la fonctionnalité existante de la liste de produits du Back Office. Il y parvient en surchargeant des templates Twig spécifiques responsables du rendu de la page du catalogue de produits dans PrestaShop 1.7.x, 8.x et 9.x. Il n'introduit pas de nouveaux contrôleurs, modèles ou d'actifs JavaScript/CSS complexes. Sa fonction principale est d'injecter la colonne MPN et son filtre associé dans la vue standard de la liste de produits.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toutes ses fonctionnalités sont réalisées via des surcharges de templates et les mécanismes de module de base de PrestaShop.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit aucune classe PHP personnalisée ou définition d'`ObjectModel`. Il utilise l'`ObjectModel` `Product` existant et son champ `mpn`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. La fonctionnalité de filtrage et de tri pour la nouvelle colonne MPN est gérée par l'implémentation existante de DataTables.js de PrestaShop pour la liste de produits, qui s'adapte automatiquement aux nouvelles colonnes.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style de la nouvelle colonne MPN et du champ de filtre héritera directement du thème de votre back office PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le mécanisme principal du module est de surcharger les templates Twig du Back Office de PrestaShop pour injecter la colonne MPN.

- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`** :
  - **Objectif** : Ce template est une surcharge directe du template de liste de produits de base de PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/list.html.twig` ou un chemin similaire selon la version de PS).
  - **Fonctionnalité** : Il modifie la structure de la liste de produits pour inclure l'en-tête de colonne MPN et le champ de saisie de filtre correspondant. Il garantit que le champ MPN est reconnu comme une colonne triable et filtrable dans la configuration de DataTables.
- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`** :
  - **Objectif** : Ce template est une surcharge directe du template de table de produits de base de PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/products_table.html.twig` ou un chemin similaire).
  - **Fonctionnalité** : Il modifie les lignes du tableau pour afficher la valeur MPN réelle de chaque produit dans la colonne nouvellement ajoutée. Il accède à la propriété `product.mpn` à partir des données produit passées au template.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée aucune nouvelle table de base de données. Il s'appuie sur la colonne `mpn` existante dans la table `ps_product` (ou `ps_product_shop` pour les MPN spécifiques à la boutique, bien que ce soit généralement sur `ps_product`).
- **Table des hooks enregistrés** : Ce module n'enregistre explicitement aucun nouveau hook. Sa fonctionnalité est réalisée via des surcharges de templates. Bien qu'il n'utilise pas `displayHeader`, `displayRightColumn`, `actionValidateOrder` etc., dans sa méthode `install()`, il s'enregistre probablement pour les surcharges de templates, ce qui est une forme implicite de "hooking" dans le processus de rendu.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute question concernant le module "Filtre MPN sur la liste de produits dans le back office", veuillez vous référer à votre compte client MyPresta.eu. Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.

- **Historique des commandes et téléchargements MyPresta.eu** : <https://mypresta.eu/my-account/orders/>
- **Contact support MyPresta.eu** : <https://mypresta.eu/contact>
