---
title: "Fourchette de prix des produits - de / à - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Fourchette de prix des produits - de / à' par MyPresta.eu."
sidebar:
  label: "Fourchette de prix des produits - de / à - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product price range - from / to sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-price-range-from-to.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-price-range-from-to/)
>
> ---


# Fourchette de prix des produits - de / à

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes pour les modules PrestaShop. Aucune exigence d'hébergement particulière au-delà d'un environnement standard compatible PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, naviguez vers **Modules > Gestionnaire de modules** et cliquez sur « Configurer » à côté de « Fourchette de prix des produits - de / à ». Vous serez présenté avec l'écran de configuration principal.

#### Paramètres généraux

Cette section contrôle le comportement principal du module.

- **Afficher la fourchette de prix sur la liste des produits :**

  - **Ce que fait ce paramètre :** Cet interrupteur détermine si la fourchette « de [prix le plus bas] à [prix le plus élevé] » est affichée sur les pages qui listent plusieurs produits, telles que les pages de catégorie, les résultats de recherche ou les modules comme « Nouveaux produits » ou « Produits vedettes ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Les produits avec des combinaisons et des prix variables afficheront une fourchette de prix sur toutes les pages de liste de produits.
    - *Lorsqu'désactivé (NON) :* Seul un prix unique (généralement le prix de base ou le prix de la combinaison la plus basse) sera affiché sur les pages de liste de produits, selon le comportement par défaut de PrestaShop.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple pour le marchand :** Si vous vendez des T-shirts qui coûtent 10 € pour la taille S et 15 € pour la taille L, l'activation de cette option affichera « de 10,00 € à 15,00 € » sur votre page de catégorie de T-shirts, donnant aux clients un aperçu rapide des options de prix.
- **Afficher la fourchette de prix sur la page du produit :**

  - **Ce que fait ce paramètre :** Cet interrupteur contrôle si la fourchette de prix est affichée sur la page du produit individuelle elle-même, généralement près de la zone principale du prix du produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* La page du produit affichera la fourchette de prix pour les produits avec des combinaisons, informant le client des variations de prix avant qu'il ne sélectionne les options.
    - *Lorsqu'désactivé (NON) :* La page du produit n'affichera qu'un prix unique (généralement le prix de base ou le prix de la combinaison la plus basse), selon le comportement par défaut de PrestaShop.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple pour le marchand :** Sur la page produit d'un ordinateur sur mesure, l'activation de cette option affichera « de 800,00 € à 2500,00 € » avant que le client ne commence à sélectionner les options de CPU, de RAM et de stockage, fixant des attentes claires.
- **Prendre en compte les réductions de quantité :**

  - **Ce que fait ce paramètre :** Ce paramètre crucial détermine si le module doit prendre en compte les réductions de prix basées sur la quantité (prix spécifiques pour les quantités) lors du calcul du prix *le plus bas* de la fourchette.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Le module calculera le prix le plus bas possible, y compris les réductions de quantité, pour la partie « de » de la fourchette. Par exemple, si un produit coûte 10 €, mais 8 € si vous achetez 10 unités, le prix « de » sera de 8 €.
    - *Lorsqu'désactivé (NON) :* Les réductions de quantité seront ignorées, et le prix « de » sera basé uniquement sur le prix de la combinaison la plus basse sans tenir compte des économies d'achat en gros.
  - **Valeur recommandée :** OUI (pour garantir que le prix le plus bas le plus attrayant et le plus précis est affiché).
  - **Scénario / exemple pour le marchand :** Si vous vendez des stylos à 1 € l'unité, mais les proposez à 0,80 € s'ils sont achetés par lots de 100, l'activation de cette option garantira que le prix « de » sur votre liste de produits reflète 0,80 €, rendant le produit encore plus abordable.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher la fourchette de prix sur la liste des produits | OUI | Affiche le prix « de/à » sur les pages de catégorie, de recherche et de liste. |
| Configuration du module | Afficher la fourchette de prix sur la page du produit | OUI | Affiche le prix « de/à » sur la page de détail du produit individuelle. |
| Configuration du module | Prendre en compte les réductions de quantité | OUI | Inclut les réductions de prix basées sur la quantité lors du calcul du prix le plus bas de la fourchette. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q1 : La fourchette de prix n'apparaît pas sur mes pages/listes de produits.**
R :

1. **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules > Fourchette de prix des produits - de / à > Configurer**. Assurez-vous que « Afficher la fourchette de prix sur la liste des produits » et « Afficher la fourchette de prix sur la page du produit » sont tous deux réglés sur **OUI**.
2. **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
3. **Combinaisons de produits :** Le produit a-t-il réellement des combinaisons avec des prix *différents* ? Si toutes les combinaisons ont le même prix, le module affichera probablement un prix unique car il n'y a pas de fourchette à afficher.
4. **Compatibilité du thème :** Bien que le module soit conçu pour une large compatibilité, les thèmes très fortement personnalisés peuvent nécessiter des ajustements mineurs. Si le problème persiste après avoir vérifié ce qui précède, contactez le support MyPresta.eu.

**Q2 : Le prix « de » ne semble pas inclure mes réductions de quantité.**
R :

1. **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules > Fourchette de prix des produits - de / à > Configurer**. Assurez-vous que « Prendre en compte les réductions de quantité » est réglé sur **OUI**.
2. **Vérifiez les réductions de quantité :** Vérifiez que vos réductions de quantité (prix spécifiques) sont correctement configurées pour le produit et ses combinaisons dans le back office de PrestaShop.
3. **Videz le cache :** Videz toujours votre cache PrestaShop après avoir effectué des modifications de configuration.

**Q3 : La fourchette de prix semble un peu décalée ou mal alignée avec le design de mon thème.**
R :
Le module essaie de s'intégrer de manière transparente, mais chaque thème est unique.

1. **Videz le cache :** Parfois, les problèmes de style sont dus à d'anciens fichiers mis en cache.
2. **CSS personnalisé :** Vous pourriez avoir besoin d'ajouter du CSS personnalisé à votre thème pour ajuster l'apparence. Les classes CSS du module sont généralement bien définies (voir Section 7.5). Un webmaster peut vous aider à cibler ces classes pour qu'elles correspondent à votre thème.
3. **Contactez le support :** Si vous n'êtes pas à l'aise avec le CSS, le support MyPresta.eu peut souvent vous fournir des conseils ou de petits extraits de CSS pour vous aider.

**Q4 : Ce module va-t-il ralentir ma boutique ?**
R :
Le module est optimisé pour la performance. Il calcule les prix efficacement. Bien que tout module ajoute une petite surcharge, celui-ci est conçu pour être léger. Si vous remarquez des ralentissements importants, assurez-vous que votre serveur répond aux spécifications recommandées par PrestaShop et que d'autres modules ne causent pas de conflits. Vider régulièrement le cache aide également.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Fourchette de prix des produits - de / à » (`prange`) est un module PrestaShop standard suivant le modèle MVC. Il fonctionne principalement en s'accrochant à divers points d'affichage (`displayProductPriceBlock`, `displayProductListReviews`, etc.) pour injecter sa fourchette de prix calculée. La logique principale réside dans le fichier `index.php` principal, qui agit comme point d'entrée du module et gère la configuration, l'installation et l'enregistrement des hooks. Il utilise les classes `Product` et `SpecificPrice` de PrestaShop pour calculer la fourchette de prix, y compris les réductions de quantité.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office personnalisés. Toute la logique est encapsulée dans la classe principale du module et exécutée via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit pas de classes personnalisées ni n'étend `ObjectModel`. Toutes les manipulations de données et les calculs de prix nécessaires sont effectués à l'aide des classes natives `Product` et `SpecificPrice` de PrestaShop dans le fichier principal du module.

### 4.4 Actifs JavaScript (`views/js/`)

- **`prange/views/js/prange-hide-p.js`**
  - **Portée :** Front-office (Page produit)
  - **Objectif :** Ce script contient probablement une logique pour masquer ou modifier l'affichage du prix par défaut du produit sur la page du produit individuelle lorsque la fourchette de prix du module est active. Il peut écouter les changements du DOM ou les événements de chargement de page pour s'assurer que la fourchette du module est le prix principal affiché.
- **`prange/views/js/prange-hide-pl.js`**
  - **Portée :** Front-office (Pages de liste de produits)
  - **Objectif :** Similaire à `prange-hide-p.js`, mais cible spécifiquement les pages de liste de produits (catégories, résultats de recherche). Il est conçu pour masquer ou ajuster l'affichage du prix unique par défaut sur ces pages afin de faire place à la fourchette de prix du module.
- **`prange/views/js/prange.js`**
  - **Portée :** Front-office
  - **Objectif :** Il s'agit probablement du fichier JavaScript principal du module. Il pourrait contenir :
    - Une logique pour mettre à jour dynamiquement la fourchette de prix si les attributs du produit sont modifiés via AJAX (par exemple, la sélection d'une combinaison).
    - Des écouteurs d'événements pour les événements `prestashop.on` liés aux mises à jour des données du produit.
    - Tout rendu ou manipulation côté client requis pour l'affichage de la fourchette de prix.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`prange/views/css/prange.css`**
  - **Portée :** Style client du Front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style fournit la présentation visuelle par défaut pour le texte de la fourchette de prix. Elle définira les styles pour le conteneur contenant le texte « de/à », les tailles de police, les couleurs, les marges et potentiellement les ajustements réactifs.
  - **Sélecteurs de classes CSS clés que les développeurs peuvent surcharger :** Les développeurs doivent inspecter le HTML rendu pour identifier les classes spécifiques (par exemple, `.prange-price-range`, `.prange-from`, `.prange-to`) utilisées par le module. Celles-ci peuvent ensuite être ciblées dans le `custom.css` ou `theme.css` d'un thème personnalisé pour ajuster l'apparence.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** : Ce module ne définit pas explicitement de templates dans un sous-répertoire `hook/` basé sur l'inventaire fourni, mais les templates listés ci-dessous sont effectivement rendus via des hooks.
- **Templates d'administration (`views/templates/admin/`)** : Ce module n'a pas de templates d'administration personnalisés au-delà du formulaire `getContent()` standard.
- **Templates front-office (`views/templates/front/`)** :
  - **`prange/views/templates/prange-oneprice.tpl`**
    - **Objectif :** Ce template est probablement utilisé lorsqu'un produit *n'a pas* de combinaisons avec des prix variables, ou lorsque le module détermine qu'un seul prix doit être affiché (par exemple, si les prix « de » et « à » sont identiques). Il assure une mise en forme cohérente même pour les produits à prix unique si le module est actif.
    - **Rendu via :** Probablement accroché à `displayProductPriceBlock` ou similaire.
  - **`prange/views/templates/prange.tpl`**
    - **Objectif :** C'est le template principal pour afficher la fourchette réelle « de [prix le plus bas] à [prix le plus élevé] ». Il reçoit les prix les plus bas et les plus élevés calculés à partir de la logique PHP du module et les formate pour l'affichage.
    - **Rendu via :** Ce template sera rendu lorsque le module s'accrochera à `displayProductPriceBlock` (pour la page produit) et potentiellement à d'autres hooks pour les pages de liste de produits (par exemple, `displayProductListReviews`, `displayProductPriceBlock` dans le contexte de la liste de produits, ou en surchargeant les templates principaux).

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée pas de tables SQL personnalisées.
  - Il stocke ses paramètres de configuration (par exemple, `PRANGE_DISPLAY_LIST`, `PRANGE_DISPLAY_PRODUCT`, `PRANGE_QUANTITY_DISCOUNT`) dans la table standard `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour inclure les fichiers CSS (`prange.css`) et JavaScript (`prange.js`, `prange-hide-p.js`, `prange-hide-pl.js`) du module pour le style et la fonctionnalité du front-office. |
| `displayProductPriceBlock` | Rend le contenu dans le bloc de prix du produit sur les pages de produits et potentiellement les listes de produits. | C'est le hook principal pour injecter la fourchette de prix calculée dans l'affichage du prix du produit. Le module vérifie probablement le paramètre `type` de ce hook pour déterminer le contexte (page produit vs liste). |
| `displayProductListReviews` | Rend le contenu près des avis sur les produits sur les pages de liste de produits. | Bien que nommé pour les avis, ce hook est souvent utilisé par les modules pour injecter des informations supplémentaires (comme les fourchettes de prix) dans les éléments de la liste de produits. |
| `displayProductExtraContent` | Rend des blocs de contenu supplémentaires sur la page du produit. | Pourrait être utilisé comme emplacement alternatif ou supplémentaire pour la fourchette de prix sur la page du produit. |
| `displayAfterProductThumbs` | Rend le contenu après les images miniatures du produit sur la page du produit. | Un autre emplacement potentiel pour afficher la fourchette de prix sur la page du produit. |
| `displayProductButtons` | Rend le contenu près des boutons d'action du produit (par exemple, Ajouter au panier). | Moins probable pour la fourchette de prix, mais possible pour des informations contextuelles. |
| `displayFooterProduct` | Rend le contenu dans la section du pied de page de la page du produit. | Un emplacement de secours ou alternatif pour la fourchette de prix sur la page du produit. |
| `displayProductAdditionalInfo` | Rend des informations supplémentaires sur la page du produit. | Un hook courant pour injecter des détails de produit personnalisés. |
| `displayProductPrice` | Rend le prix du produit lui-même. | Ce hook est souvent surchargé ou étendu par les modules qui modifient l'affichage des prix. |
| `actionProductUpdate` | Exécuté après la mise à jour d'un produit dans le back office. | Pourrait être utilisé pour vider les caches spécifiques au module ou réindexer les fourchettes de prix si le module maintenait son propre cache. |
| `actionProductAdd` | Exécuté après l'ajout d'un nouveau produit. | Similaire à `actionProductUpdate`. |
| `actionProductDelete` | Exécuté après la suppression d'un produit. | Similaire à `actionProductUpdate`. |

*Note : Les hooks exacts utilisés peuvent varier légèrement entre les versions du module et les versions de PrestaShop. La liste ci-dessus représente les hooks courants pour la fonctionnalité de ce module basée sur sa description.*

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur dédié pour le module « Fourchette de prix des produits - de / à », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Assurez-vous d'utiliser la dernière version du module pour des performances et une compatibilité optimales avec votre boutique PrestaShop.
