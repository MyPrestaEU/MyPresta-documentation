---
title: "Afficher les prix de base (sans réductions) - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Afficher les prix de base (sans réductions)' par MyPresta.eu."
sidebar:
  label: "Afficher les prix de base (sans réductions) - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Display base prices (without discounts) sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/display-base-prices-without-discounts.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/display-base-prices-without-discounts/)
>
> ---


# Afficher les prix de base (sans réductions)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du nom du module pour accéder à ses paramètres. C'est l'écran principal où vous contrôlez comment et où les prix de base sont affichés.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple marchand |
| --- | --- | --- | --- | --- |
| **Activer le module** | C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module. | *Lorsque activé :* Le module commencera à afficher les prix de base sur votre front-office selon les autres paramètres. *Lorsque désactivé :* Le module cessera d'afficher les prix de base, et votre boutique reviendra à n'afficher que les prix actuels. | OUI | Vous venez d'installer le module et souhaitez activer ses fonctionnalités. |
| **Afficher sur la page produit** | Contrôle si le prix de base est affiché sur les pages de détails de produits individuels. | *Lorsque activé :* Le prix original apparaîtra à côté du prix réduit sur la page de chaque produit. *Lorsque désactivé :* Le prix de base ne sera pas affiché sur les pages de produits, même s'il est activé ailleurs. | OUI | Vous voulez que les clients qui consultent un produit spécifique voient clairement les économies. |
| **Afficher sur les pages de catégories** | Contrôle si le prix de base est affiché sur les pages de listes de produits (par exemple, pages de catégories, résultats de recherche). | *Lorsque activé :* Le prix original apparaîtra à côté du prix réduit pour chaque produit listé dans les catégories, les résultats de recherche, etc. *Lorsque désactivé :* Le prix de base ne sera pas affiché sur les pages de listes de produits. | OUI | Vous voulez que les clients qui naviguent dans les catégories identifient rapidement les articles à prix réduit et leurs économies. |
| **Afficher dans le récapitulatif du panier** | Contrôle si le prix de base est affiché dans le récapitulatif du panier. | *Lorsque activé :* Le prix original sera visible pour chaque produit dans le panier du client, renforçant les économies totales. *Lorsque désactivé :* Seul le prix actuel, réduit, sera affiché dans le panier. | NON (ou OUI, selon le thème) | Vous voulez rappeler aux clients leurs économies totales avant qu'ils ne procèdent au paiement. Cependant, certains thèmes pourraient ne pas avoir de zone d'affichage appropriée, ou cela pourrait encombrer le panier. Testez minutieusement. |
| **CSS personnalisé pour le prix de base** | Vous permet d'ajouter des règles CSS personnalisées pour styliser le prix de base affiché. | *Lorsque rempli de CSS :* Le prix de base sera stylisé selon votre saisie (par exemple, taille de police, couleur, barré). *Lorsque vide :* Le module utilisera son style par défaut ou héritera des styles de votre thème. | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Vous voulez que le prix de base soit grisé et barré pour le différencier clairement du prix actuel. |
| **Position du prix de base** | Détermine où le prix de base est injecté par rapport au prix actuel. | *Options : Avant le prix actuel, Après le prix actuel.* *Lorsque défini sur 'Avant' :* Le prix de base apparaîtra à gauche du prix actuel. *Lorsque défini sur 'Après' :* Le prix de base apparaîtra à droite du prix actuel. | Avant le prix actuel | Vous voulez que le client voie d'abord le prix original, puis le nouveau prix, plus bas. |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le module | OUI | Active/désactive la fonctionnalité principale du module. |
| Configuration du module | Afficher sur la page produit | OUI | Affiche le prix de base sur les pages de produits individuels. |
| Configuration du module | Afficher sur les pages de catégories | OUI | Affiche le prix de base sur les pages de listes de produits (catégories, recherche). |
| Configuration du module | Afficher dans le récapitulatif du panier | NON (ou OUI, tester) | Affiche le prix de base dans le panier. |
| Configuration du module | CSS personnalisé pour le prix de base | `text-decoration: line-through; color: #999; font-size: 0.9em;` | Personnalise le style visuel du prix de base. |
| Configuration du module | Position du prix de base | Avant le prix actuel | Contrôle le placement par rapport au prix actuel. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Les prix de base ne s'affichent pas sur ma boutique, même si le module est activé.**
R :

1.  **Vérifiez les paramètres du module :** Assurez-vous que "Activer le module" et les options d'affichage spécifiques (par exemple, "Afficher sur la page produit") sont définies sur OUI.
2.  **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" en haut à droite. Le cache Smarty doit souvent être vidé pour que les modifications de template apparaissent.
3.  **Vérifiez les réductions :** Assurez-vous que les produits que vous testez ont bien des réductions actives (règles de prix catalogue, prix spécifiques ou réductions en pourcentage) appliquées. Le module n'affiche un prix de base que s'il y a une différence.
4.  **Compatibilité du thème :** Certains thèmes très personnalisés peuvent remplacer les fonctions d'affichage des prix de base de PrestaShop. Si le problème persiste, contactez le support MyPresta.eu.

**Q : Le prix de base s'affiche, mais il ne s'intègre pas bien à mon thème (mauvaise couleur, taille, etc.).**
R : Utilisez le paramètre "CSS personnalisé pour le prix de base" dans la configuration du module. Vous pouvez ajouter des règles CSS pour correspondre au design de votre thème. Par exemple, pour le rendre gris et barré : `text-decoration: line-through; color: #999; font-size: 0.9em;`. Si vous n'êtes pas sûr du CSS, un développeur web peut vous aider.

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Le module est conçu pour être léger. Il remplace principalement une classe PrestaShop de base (`Product.php`) pour récupérer le prix de base et injecte un petit template. L'impact sur les performances devrait être négligeable. Assurez-vous toujours que votre cache PrestaShop est activé pour une vitesse optimale.

**Q : Ce module fonctionne-t-il avec les boutiques multilingues ?**
R : Oui, le module fonctionne avec les capacités multilingues de PrestaShop. Les prix sont affichés dans la devise et le format de la langue/pays actif.

**Q : Je vois une erreur "Conflit d'override" après l'installation du module.**
R : Ce module surcharge la classe `Product.php`. Si un autre module tente également de surcharger cette même classe, vous pourriez rencontrer un conflit. PrestaShop 1.7+ a une meilleure gestion des overrides, mais des conflits peuvent toujours survenir. Vous devrez soit désactiver l'un des modules en conflit, soit fusionner les overrides manuellement (nécessite des connaissances de développeur). Contactez le support MyPresta.eu pour obtenir de l'aide.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "Afficher les prix de base (sans réductions)" fonctionne principalement en surchargeant la classe `Product` de base pour introduire une méthode de récupération du prix de base du produit sans réductions. Il utilise ensuite un template Smarty pour afficher ce prix dans le front office, injecté via un mécanisme de hook personnalisé. La configuration du module est gérée via une méthode `getContent()` PrestaShop standard dans le fichier principal du module.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa fonctionnalité est intégrée directement dans les mécanismes d'affichage des prix existants de PrestaShop et via une surcharge.

### 4.3 Classes et modèles de base (`classes/`)

-   **`baseprices/override/classes/index.php`** : Un fichier `index.php` vide standard pour empêcher l'affichage du répertoire.
-   **`baseprices/override/classes/Product.php`** :
    -   **Nom de la classe** : `Product` (surcharge la classe `Product` de base)
    -   **Classe parente** : `ProductCore`
    -   **Responsabilité** : Cette surcharge est le cœur de la fonctionnalité du module. Elle introduit une nouvelle méthode, `getBasePrice()`, qui calcule et renvoie le prix du produit *avant* l'application de tout prix spécifique, règle de prix catalogue ou réduction de groupe. Cette méthode garantit que le véritable prix original est toujours disponible pour l'affichage. Elle implique généralement de contourner la logique de calcul de prix standard qui tient compte des réductions.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`baseprices/views/js/baseprices-admin.js`** :
    -   **Portée** : Back-office (page de configuration du module).
    -   **Responsabilité** : Ce script gère probablement tout comportement dynamique ou validation sur le formulaire de configuration du module. Par exemple, il pourrait afficher/masquer des paramètres en fonction d'autres sélections, ou fournir un retour en temps réel pour le champ CSS personnalisé.
-   **`baseprices/views/js/baseprices.js`** :
    -   **Portée** : Front-office.
    -   **Responsabilité** : Ce script est responsable de l'injection dynamique du prix de base dans le DOM si nécessaire, en particulier pour le contenu chargé par AJAX ou lorsque les attributs du produit changent (par exemple, la sélection d'une combinaison différente sur la page produit). Il écoute l'événement `updateProduct` de PrestaShop ou des événements similaires pour rafraîchir l'affichage du prix. Il peut également gérer le style ou les bascules de visibilité pour l'élément de prix de base.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`baseprices/views/css/baseprices.css`** :
    -   **Portée** : Style client du front-office.
    -   **Principaux composants d'interface utilisateur et conteneurs qu'il stylise** : Cette feuille de style fournit la présentation visuelle par défaut du prix de base. Elle inclut généralement des règles pour :
        -   `span.base-price` ou des sélecteurs similaires.
        -   `text-decoration: line-through;` pour barrer le prix.
        -   `color`, `font-size`, `margin`, `padding` pour positionner et styliser le prix de base par rapport au prix actuel.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** : `span.base-price`, `div.product-price-and-shipping .base-price`, etc. Les développeurs peuvent cibler ces classes dans le CSS personnalisé de leur thème pour surcharger le style par défaut du module.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **`baseprices/views/templates/baseprices.tpl`** :
    -   **Portée** : Front-office.
    -   **Responsabilité** : Ce template est la sortie principale pour l'affichage du prix de base. Il est conçu pour être inclus ou rendu partout où le prix d'un produit est affiché. Il reçoit généralement des variables comme `$base_price` et `$current_price` et les formate selon les paramètres du module (par exemple, CSS personnalisé, position). Il contiendra la structure HTML (par exemple, `<span class="base-price">...</span>`) que le CSS cible.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Ses paramètres de configuration sont stockés dans la table `ps_configuration`, en utilisant des clés préfixées par `BASEPRICES_`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Utilisé pour charger les actifs CSS et JavaScript du front-office du module. |
| `displayProductPriceBlock` | Dans le bloc d'affichage du prix du produit sur les pages de produits et les listes. | Le module utilise probablement ce hook (ou des hooks similaires liés au prix) pour injecter son template `baseprices.tpl`, affichant le prix de base à côté du prix actuel. |
| `actionProductUpdate` / `actionProductSave` | Après la mise à jour ou l'enregistrement d'un produit dans le Back Office. | Bien que non explicitement listés, les modules qui surchargent `Product.php` peuvent utiliser de tels hooks pour vider les caches ou réindexer les données du produit si nécessaire, bien que la fonction principale de ce module soit uniquement l'affichage. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son template. | Utilisé pour enregistrer les fichiers JavaScript et CSS du front-office pour la page actuelle. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module "Afficher les prix de base (sans réductions)", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
