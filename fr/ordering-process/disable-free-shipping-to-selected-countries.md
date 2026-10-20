---
title: "Désactiver la livraison gratuite vers certains pays - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Désactiver la livraison gratuite vers certains pays » par MyPresta.eu."
sidebar:
  label: "Désactiver la livraison gratuite vers certains pays - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Disable free shipping to selected countries sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-free-shipping-to-selected-countries.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/disable-free-shipping-to-selected-countries/)
>
> ---


# Désactiver la livraison gratuite vers certains pays

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal et unique du module « Désactiver la livraison gratuite vers certains pays ». Vous le trouverez en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Désactiver la livraison gratuite vers certains pays » et en cliquant sur « Configurer ».

#### Exclure la livraison gratuite des pays :

- **Ce que fait ce paramètre :** C'est le paramètre principal du module. Il vous permet de sélectionner un ou plusieurs pays où la livraison gratuite ne doit *pas* être offerte, quelles que soient les autres règles de livraison gratuite que vous pourriez avoir en place (par exemple, livraison gratuite au-delà d'un certain montant de commande).
- **Effet de la modification de ce paramètre :**
  - *Lorsque des pays sont sélectionnés :* Si l'adresse de livraison d'un client se trouve dans l'un des pays sélectionnés, l'option « Livraison gratuite » sera supprimée de la liste des transporteurs disponibles lors du paiement. Ils ne verront que les options d'expédition payantes.
  - *Lorsque aucun pays n'est sélectionné :* Le module n'aura aucun effet, et la livraison gratuite sera offerte à tous les pays conformément à vos paramètres PrestaShop standard.
- **Valeur recommandée :** Sélectionnez uniquement les pays où offrir la livraison gratuite est réellement non rentable ou problématique pour votre entreprise.
- **Scénario / exemple de marchand :** Vous expédiez à l'international, mais l'expédition vers l'Australie et la Nouvelle-Zélande est considérablement plus chère en raison de la distance et des douanes. Vous sélectionneriez « Australie » et « Nouvelle-Zélande » dans cette liste. Désormais, les clients de ces pays seront toujours facturés pour l'expédition, même si la valeur de leur commande est éligible à la livraison gratuite dans d'autres régions comme l'UE ou les États-Unis.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Exclure la livraison gratuite des pays : | Aucun sélectionné | Sélectionnez les pays où la livraison gratuite ne doit PAS être offerte. Si l'adresse de livraison d'un client se trouve dans un pays sélectionné, la livraison gratuite ne sera pas disponible pour sa commande. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais la livraison gratuite est toujours affichée pour un pays sélectionné. Qu'est-ce qui ne va pas ?**
R :

1. **Vider le cache :** Videz toujours le cache de votre PrestaShop après avoir effectué des modifications de configuration. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite.
2. **Tester avec un nouveau panier :** Assurez-vous de tester avec un nouveau panier et une adresse de livraison définie pour le pays exclu. Parfois, le cache du navigateur ou les données de session peuvent interférer.
3. **Vérifier les paramètres du transporteur :** Vérifiez que votre transporteur de livraison gratuite (ou le transporteur offrant la livraison gratuite) est correctement configuré dans **Livraison > Transporteurs**. Assurez-vous qu'il est actif et que l'option « Livraison gratuite » est activée. Ce module *désactive* l'option de livraison gratuite, il ne crée pas de nouvelles règles d'expédition.
4. **Ordre des modules :** Dans de rares cas, si vous avez plusieurs modules liés à l'expédition, il peut y avoir un conflit. Essayez de désactiver temporairement d'autres modules d'expédition pour isoler le problème.

**Q : Ce module affecte-t-il les autres frais d'expédition ?**
R : Non, ce module n'affecte *que* la disponibilité de l'option « Livraison gratuite ». Il ne modifie ni ne supprime aucune option d'expédition payante ou leurs coûts. Si la livraison gratuite est désactivée pour un pays, les clients se verront simplement présenter les options d'expédition payantes standard disponibles pour leur panier et leur destination.

**Q : Puis-je désactiver la livraison gratuite pour des produits ou des catégories spécifiques au lieu de pays ?**
R : Non, ce module est conçu spécifiquement pour désactiver la livraison gratuite en fonction du *pays de livraison*. Il n'offre pas d'options pour exclure la livraison gratuite en fonction du produit, de la catégorie ou du groupe de clients. Si vous avez besoin d'une telle fonctionnalité, vous auriez besoin d'un module de règles d'expédition différent et plus avancé.

**Q : Que faire si je veux offrir la livraison gratuite à un pays pour les commandes dépassant un certain montant, mais la désactiver pour les montants inférieurs ?**
R : Ce module désactive *toute* livraison gratuite pour les pays sélectionnés. Si vous souhaitez une livraison gratuite conditionnelle (par exemple, livraison gratuite au-delà de X €), vous devez la configurer directement dans les paramètres de vos transporteurs PrestaShop (Livraison > Transporteurs). Ce module annulerait alors ce paramètre pour les pays exclus, rendant la livraison gratuite indisponible à *tout* montant pour ces destinations spécifiques.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module « Désactiver la livraison gratuite vers certains pays » fonctionne en surchargeant les classes PrestaShop de base liées au comportement du transporteur et du panier. Plus précisément, il modifie la logique qui détermine si un transporteur offre la livraison gratuite et si un panier y est éligible, en fonction du pays de livraison du client. Ceci est réalisé grâce au système de surcharge de PrestaShop, garantissant que la logique du module est appliquée chaque fois que les calculs d'expédition sont effectués.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Sa logique est injectée directement dans la fonctionnalité PrestaShop de base via des surcharges de classe.

### 4.3 Classes et modèles de base (`classes/`)

Le module implémente sa fonctionnalité principalement via des surcharges de classe, situées dans le répertoire `override/classes/` du dossier du module.

- **`exfsc/override/classes/Carrier.php`**

  - **Nom de la classe et classe parente :** `Carrier` (surcharge la classe `Carrier` de base)
  - **Responsabilité :** Cette surcharge modifie la méthode `isFree()` de la classe `Carrier`. Lorsque PrestaShop vérifie si un transporteur particulier offre la livraison gratuite, cette surcharge intercepte l'appel. Elle vérifie si le pays de livraison du panier actuel fait partie de ceux configurés pour exclure la livraison gratuite. Si c'est le cas, et que la méthode `isFree()` originale aurait renvoyé `true`, cette surcharge la force à renvoyer `false`, désactivant effectivement la livraison gratuite pour ce transporteur pour le pays exclu.
  - **Méthodes clés :**
    - `isFree($cart)` : Modifiée pour vérifier la configuration `exfsc_country` et renvoyer `false` si le pays de livraison du panier est exclu et que la méthode originale aurait renvoyé `true`.
- **`exfsc/override/classes/Cart.php`**

  - **Nom de la classe et classe parente :** `Cart` (surcharge la classe `Cart` de base)
  - **Responsabilité :** Cette surcharge modifie la méthode `getDeliveryOptionList()`. Cette méthode est responsable de la génération de la liste des options de livraison disponibles (y compris les transporteurs et leurs services) lors du paiement. La surcharge garantit que si un transporteur est marqué comme « livraison gratuite » mais que le pays de livraison est exclu par le module, ce transporteur est correctement présenté avec ses options d'expédition *payantes*, ou s'il n'offre que la livraison gratuite, il est entièrement exclu.
  - **Méthodes clés :**
    - `getDeliveryOptionList(Country $default_country = null, $product_list = null, $id_zone = null)` : Modifiée pour garantir que les transporteurs marqués comme gratuits sont correctement évalués par rapport à la liste d'exclusion de pays du module.
- **`exfsc/override/classes/index.php`**

  - **Objectif :** Il s'agit d'un fichier `index.php` vide, généralement inclus dans les répertoires pour empêcher la liste des répertoires lorsqu'ils sont directement accessibles via un navigateur web, améliorant ainsi la sécurité. Il n'a aucun impact fonctionnel sur la logique du module.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé. Toutes les fonctionnalités sont gérées côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. Toutes les fonctionnalités sont gérées côté serveur.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module n'inclut aucun fichier de template Smarty personnalisé. Ses effets sont intégrés aux templates de paiement PrestaShop existants en modifiant les données sous-jacentes qui leur sont transmises.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données :**

  - Le module ne crée aucune table SQL personnalisée.
  - Les paramètres de configuration sont stockés dans la table `ps_configuration`.
    - `exfsc_country` : Stocke une liste d'`id_country` séparés par des virgules pour les pays où la livraison gratuite est désactivée.
    - `mypresta_updates`, `update_`, `updatev_` : Clés de configuration internes utilisées par les modules MyPresta.eu pour les vérifications de mise à jour.
    - `exfsc_visibility_cat`, `exfsc_visibility_products` : Ces clés sont présentes dans la méthode `getContent()` mais ne sont pas activement utilisées par la logique de base du module telle que décrite dans l'ensemble des fonctionnalités. Elles pourraient être des vestiges ou des espaces réservés pour de futures fonctionnalités potentielles.
- **Table des hooks enregistrés :**
  Le module n'enregistre explicitement aucun hook front-office. Sa fonctionnalité est implémentée via des surcharges de classe, qui sont déclenchées automatiquement par les processus de base de PrestaShop lorsque les options d'expédition sont calculées.
  La méthode `install()` du module peut enregistrer des hooks back-office standard pour la gestion des modules (par exemple, `displayBackOfficeHeader`), mais ceux-ci sont à des fins administratives et n'affectent pas le comportement du front-office.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Désactiver la livraison gratuite vers certains pays », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le fonctionnement parfait de votre module avec votre boutique PrestaShop.
