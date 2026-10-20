---
title: "Accessoires sur la liste des produits - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Accessoires sur la liste des produits' par MyPresta.eu."
sidebar:
  label: "Accessoires sur la liste des produits - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Accessories on list of products sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/accessories-on-list-of-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/accessories-on-list-of-products/)
>
> ---


# Accessoires sur la liste des produits

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur le bouton "Configurer" à côté du module "Accessoires sur la liste de produits" dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple marchand |
| --- | --- | --- | --- | --- |
| **Corriger le bug du thème classic** | Ce paramètre résout un problème d'affichage spécifique qui peut survenir avec le thème PrestaShop Classic par défaut ou les thèmes basés sur celui-ci, où les accessoires pourraient ne pas s'afficher correctement. | *Lorsque activé :* Le module applique un correctif pour garantir que les accessoires s'affichent correctement sur les listes de produits, en particulier avec le thème Classic. *Lorsque désactivé :* Le correctif n'est pas appliqué. Si vous utilisez le thème Classic ou un dérivé, les accessoires pourraient ne pas s'afficher correctement ou avoir des problèmes de mise en page. | **OUI** (Si vous utilisez le thème Classic ou un thème basé sur celui-ci) / **NON** (Si vous utilisez un thème entièrement personnalisé et ne rencontrez pas de problèmes) | Si vous avez installé le module et que les accessoires n'apparaissent pas ou semblent cassés sur vos pages de catégorie, l'activation de ce paramètre est la première étape de dépannage, surtout si vous êtes sur le thème Classic. Si votre thème est fortement personnalisé et ne présente pas ce bug, vous pouvez le laisser désactivé pour éviter tout conflit potentiel, bien qu'il soit généralement sûr de l'activer. |
| **Activé / Désactivé** | C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module dans l'ensemble de votre boutique. | *Lorsque activé :* Le module affichera activement les accessoires sur les pages de liste de produits comme décrit. *Lorsque désactivé :* La fonctionnalité du module est complètement désactivée, et aucun accessoire n'apparaîtra sur les listes de produits. | **Activé** | Vous avez terminé de configurer vos accessoires pour les produits et souhaitez qu'ils apparaissent sur votre boutique en ligne. Vous l'activeriez. Si vous devez masquer temporairement les accessoires pour la maintenance ou une campagne spéciale, vous le désactiveriez. |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Corriger le bug du thème classic | OUI (pour les utilisateurs du thème Classic) | Résout les problèmes d'affichage des accessoires sur les listes de produits avec le thème Classic. |
| Page de configuration du module | Activé / Désactivé | Activé | Active ou désactive la fonctionnalité principale du module. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Les accessoires n'apparaissent pas sur mes pages de liste de produits.**
R :

1.  **Vérifier l'état du module** : Assurez-vous que le module est "Activé" dans sa configuration.
2.  **Vérifier l'attribution des accessoires** : Vérifiez que les produits principaux ont bien des accessoires qui leur sont attribués dans la page d'édition du produit PrestaShop (sous l'onglet "Accessoires").
3.  **Compatibilité du thème** : Si vous utilisez un thème personnalisé, il pourrait remplacer le modèle de liste de produits standard d'une manière qui empêche le module de s'accrocher correctement. Essayez d'activer le paramètre "Corriger le bug du thème classic", même si vous n'êtes pas sur le thème Classic, car cela pourrait résoudre certains problèmes d'affichage généraux.
4.  **Vider le cache** : Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). Parfois, le cache de PrestaShop doit être rafraîchi pour refléter les nouvelles modifications du module.

**Q : Les accessoires ont l'air étranges ou sont mal alignés sur ma boutique.**
R :

1.  **"Corriger le bug du thème classic"** : Essayez d'activer ce paramètre dans la configuration du module. Il résout spécifiquement les problèmes de mise en page.
2.  **Conflit CSS du thème** : Le CSS de votre thème pourrait être en conflit avec le style du module. Cela nécessite souvent qu'un webmaster ou un développeur inspecte le CSS et effectue des ajustements.
3.  **Vider le cache** : Videz toujours votre cache PrestaShop après avoir effectué des modifications de configuration.

**Q : Puis-je contrôler quels accessoires apparaissent pour des produits spécifiques ?**
R : Oui, le module utilise la fonction d'attribution d'accessoires native de PrestaShop. Pour ajouter ou supprimer des accessoires pour un produit, allez dans **Catalogue > Produits**, modifiez le produit souhaité et naviguez vers l'onglet "Accessoires". Ici, vous pouvez rechercher et ajouter/supprimer des produits associés.

**Q : Ce module ralentit-il ma boutique ?**
R : Le module est conçu pour être efficace. Il exploite les données d'accessoires existantes de PrestaShop. Cependant, si vous avez des milliers de produits, chacun avec des dizaines d'accessoires, et que les ressources de votre serveur sont limitées, tout chargement de données supplémentaire peut avoir un impact mineur. Pour la plupart des boutiques, l'impact sur les performances est négligeable.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "Accessoires sur la liste de produits" (`accol`) est un module PrestaShop standard principalement axé sur l'affichage en front-office. Il étend `Module` et utilise le système de hooks de PrestaShop pour injecter les données et le rendu des accessoires dans les modèles de liste de produits existants. Il n'introduit pas de nouvelles tables de base de données ni de contrôleurs personnalisés complexes, ce qui le rend léger et axé sur son objectif d'affichage. La logique du module est contenue dans son fichier PHP principal, avec les fichiers JS et CSS associés pour le style et l'interaction.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Le module injecte son contenu directement dans les modèles de liste de produits existants via des hooks.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration est gérée directement via la méthode `getContent()` dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   Le module ne définit aucune classe personnalisée dans le répertoire `classes/`. Toute la logique principale réside dans le fichier principal du module `accol.php`.
-   Il interagit avec les méthodes standard `Product` et `Product::getAccessories()` de PrestaShop pour récupérer les données des accessoires.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`accol/js/accol.js`**
    -   **Portée** : Front-office.
    -   **Objectif** : Ce script est responsable de la gestion de l'affichage dynamique et des interactions potentielles avec les listes d'accessoires. Il peut inclure une logique pour les carrousels réactifs (si implémentés), l'affichage/masquage des blocs d'accessoires, ou les appels AJAX pour ajouter des accessoires au panier (bien que la fonction principale du module soit l'affichage, et non l'ajout direct au panier via AJAX). Il est probablement chargé via le hook `displayHeader` ou `header`.
    -   **Détails** : Il peut lier des écouteurs d'événements aux éléments d'accessoires, gérer leur visibilité ou initialiser des bibliothèques tierces utilisées pour les carrousels ou les curseurs si le module implémente de telles fonctionnalités pour l'affichage des accessoires.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`accol/css/accol.css`**
    -   **Portée** : Style client front-office.
    -   **Objectif** : Cette feuille de style fournit le style visuel nécessaire pour les listes d'accessoires affichées sur les pages de produits.
    -   **Composants et conteneurs UI principaux** : Elle stylise le conteneur des accessoires, les éléments d'accessoires individuels (images, noms, prix) et potentiellement les éléments de navigation (comme les flèches pour les carrousels).
    -   **Sélecteurs de classe CSS clés** : Les développeurs peuvent s'attendre à des sélecteurs comme `.accol-accessories-list`, `.accol-accessory-item`, `.accol-accessory-image`, `.accol-accessory-name`, etc., qui peuvent être surchargés dans le `custom.css` ou `theme.css` d'un thème personnalisé pour correspondre à l'esthétique du thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    -   `accol/accol.tpl` : C'est le modèle front-office principal responsable du rendu de la liste des accessoires pour un produit donné. Il est probablement accroché à `displayProductListReviews` ou à un hook similaire qui permet d'injecter du contenu dans la boucle d'éléments de la liste de produits. Il reçoit un tableau de produits accessoires et les parcourt pour afficher leurs images, noms et potentiellement prix.
-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `accol/admin.tpl` : Ce modèle est utilisé pour la page de configuration du module dans le Back Office de PrestaShop. Il contient les éléments de formulaire HTML pour les paramètres "Corriger le bug du thème classic" et "Activé/Désactivé", ainsi que tous les messages d'information ou boutons de sauvegarde.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il s'appuie sur la table native `ps_product_accessory` de PrestaShop (qui lie les produits à leurs accessoires) et `ps_configuration` pour ses propres paramètres (`ACCOL_FIX`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Utilisé pour charger les actifs CSS (`accol.css`) et JavaScript (`accol.js`) pour l'affichage front-office. |
| `displayProductListReviews` | Dans la boucle d'éléments de la liste de produits, généralement sous les informations principales du produit. | Le hook principal utilisé pour injecter le modèle `accol.tpl`, rendant les accessoires pour chaque produit de la liste. Ce hook est souvent disponible dans `product-list.tpl` ou des modèles similaires. |
| `header` | (Alias de `displayHeader` dans de nombreux contextes, en particulier les anciennes versions de PrestaShop). | Même objectif que `displayHeader` – chargement des actifs. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses actifs multimédias. | Peut être utilisé pour ajouter conditionnellement du CSS/JS en fonction du contexte de la page actuelle, garantissant que les actifs ne sont chargés que lorsque cela est nécessaire. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module "Accessoires sur la liste de produits", veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
