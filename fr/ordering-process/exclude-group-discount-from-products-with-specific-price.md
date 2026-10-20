---
title: "Exclure la réduction de groupe des produits avec prix spécifique - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Exclure la réduction de groupe des produits avec prix spécifique par MyPresta.eu."
sidebar:
  label: "Exclure la réduction de groupe des produits avec prix spécifique - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Exclude group discount from products with specific price sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-group-discount-from-products-with-specific-price.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/exclude-group-discount-from-products-with-specific-price/)
>
> ---


# Exclure la réduction de groupe des produits avec prix spécifique

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, naviguez vers **Modules > Gestionnaire de modules**, trouvez « Exclure la réduction de groupe des produits avec prix spécifique », et cliquez sur **Configurer**. Vous verrez l'écran de configuration principal.

#### Paramètre : Désactiver la réduction de groupe pour les produits avec prix spécifiques

- **Ce que fait ce paramètre :** C'est le contrôle principal de la fonctionnalité du module. Il détermine si le module doit activement empêcher les réductions de groupe de s'appliquer aux produits qui ont déjà des prix spécifiques.
- **Effet de la modification de ce paramètre :**
  - **Lorsque défini sur « Activé » :** Si un produit a un prix spécifique (par exemple, un prix de vente spécial que vous avez défini), et qu'un client d'un groupe qui reçoit normalement une réduction (par exemple, les « Clients VIP » obtiennent 10 % de réduction) consulte ou achète ce produit, la réduction de groupe de 10 % ne sera *pas* appliquée. Le client paiera le prix spécifique que vous avez défini. C'est le comportement prévu du module.
  - **Lorsque défini sur « Désactivé » :** Le module sera inactif. Le comportement par défaut de PrestaShop reprendra. Cela signifie que si un produit a un prix spécifique, et qu'un client d'un groupe bénéficiant d'une réduction le consulte ou l'achète, *les deux* le prix spécifique et la réduction de groupe seront appliqués, ce qui pourrait entraîner un prix final beaucoup plus bas que prévu.
- **Valeur recommandée :** **Activé**. C'est le but du module, d'empêcher le cumul involontaire des réductions.
- **Scénario / exemple de marchand :** Vous avez une « Vente d'été » où un T-shirt spécifique est au prix de 15 $ (au lieu de 25 $). Vous avez également un groupe de clients « Grossistes » qui bénéficie de 20 % de réduction sur toutes les commandes.
  - Si ce paramètre est **Activé** : Un client grossiste achète le T-shirt. Il paie 15 $. La réduction de 20 % pour les grossistes est ignorée pour ce produit spécifique.
  - Si ce paramètre est **Désactivé** : Un client grossiste achète le T-shirt. PrestaShop applique d'abord le prix spécifique (15 $), puis applique la réduction de 20 % pour les grossistes à 15 $, ce qui porte le prix final à 12 $. Cela pourrait être inférieur à votre marge bénéficiaire souhaitée.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Désactiver la réduction de groupe pour les produits avec prix spécifiques | Activé | Contrôle si les réductions de groupe sont empêchées de se cumuler avec les prix spécifiques. **Activé** empêche le cumul, préservant les marges bénéficiaires. **Désactivé** permet le cumul, pouvant entraîner des prix plus bas. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais les réductions de groupe s'appliquent toujours à mes prix spécifiques. Qu'est-ce qui ne va pas ?**
R :

1.  **Vider le cache :** Videz toujours le cache de votre PrestaShop après avoir effectué des modifications de configuration. Allez dans **Paramètres avancés > Performances**, puis cliquez sur « Vider le cache » en haut à droite.
2.  **Ordre des modules :** Dans de rares cas, un autre module pourrait annuler les calculs de prix. Si vous avez d'autres modules de prix ou de réduction, essayez de les désactiver temporairement un par un pour voir s'il y a un conflit.
3.  **Configuration du prix spécifique :** Vérifiez que vos « prix spécifiques » sont correctement configurés pour les produits en question. Allez sur la page d'édition du produit, puis sur l'onglet « Prix », et assurez-vous que le prix spécifique est actif et correctement appliqué.
4.  **Configuration de la réduction de groupe :** Vérifiez que la réduction de groupe de clients est correctement configurée sous **Paramètres de la boutique > Paramètres client > Groupes**.

**Q : Ce module affectera-t-il mes règles de panier ou mes codes de réduction habituels ?**
R : Non, ce module cible spécifiquement les « réductions de groupe » (réductions appliquées automatiquement en fonction du groupe attribué à un client) et leur interaction avec les « prix spécifiques » (remplacements manuels de prix pour un produit). Il n'interfère pas avec les règles de panier, les codes de réduction ou d'autres mécanismes promotionnels de PrestaShop, à moins que ces mécanismes ne soient eux-mêmes basés sur des prix spécifiques ou des réductions de groupe.

**Q : Ce module ralentit-il ma boutique ?**
R : Non, le module est très léger. Il fonctionne en surchargeant une classe PrestaShop de base (`Product.php`) pour modifier la façon dont les prix sont calculés. Il s'agit d'un processus hautement optimisé qui ne devrait pas entraîner de dégradation notable des performances.

**Q : Et si je veux que les réductions de groupe s'appliquent *parfois* aux prix spécifiques ?**
R : Ce module offre une approche « tout ou rien » : soit les réductions de groupe sont exclues de *tous* les produits avec des prix spécifiques, soit elles ne le sont pas. Si vous avez besoin d'un contrôle plus granulaire (par exemple, exclure pour le Produit A mais autoriser pour le Produit B, tous deux avec des prix spécifiques), ce module seul ne le permettra pas. Vous devrez gérer les prix spécifiques et les réductions de groupe manuellement ou envisager un module de tarification plus avancé. Pour ce module, la recommandation est de l'activer pour éviter un cumul involontaire.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module `Exclure la réduction de groupe des produits avec prix spécifique` implémente sa fonctionnalité principale via une surcharge de la classe `Product`. Il s'agit d'un modèle de développement PrestaShop courant et efficace pour modifier les comportements de base sans altérer directement les fichiers du cœur. En surchargeant `Product::getPriceStatic()`, le module intercepte la logique de calcul des prix pour empêcher l'application des réductions spécifiques aux groupes lorsqu'un produit a un prix spécifique actif.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Toute la logique front-office est gérée via la surcharge de la classe `Product`.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

La fonctionnalité principale du module réside dans sa surcharge de classe.

- **Chemin du fichier** : `exgdis/override/classes/Product.php`
- **Nom de la classe** : `Product` (surcharge la classe `Product` du cœur)
- **Classe parente** : `ProductCore`
- **Responsabilité** : Cette surcharge modifie la méthode `getPriceStatic()`, qui est essentielle pour la façon dont PrestaShop calcule les prix des produits dans le front office (pages produits, panier, commande) et le back office.
  - **Logique clé** : Dans la méthode `getPriceStatic()` surchargée, le module vérifie si son paramètre de configuration `exgdis_groups` (qui correspond à « Désactiver la réduction de groupe pour les produits avec prix spécifiques ») est activé.
  - Si activé, et si le produit en cours de tarification a un prix spécifique actif, le module s'assure que le paramètre `$use_group_reduction` passé à la méthode `ProductCore::getPriceStatic()` originale est défini sur `false`. Cela indique effectivement à PrestaShop de *ne pas* appliquer de réductions spécifiques aux groupes pour ce calcul de prix particulier.
  - Le fichier `index.php` dans `override/classes/` est un fichier vide standard pour empêcher l'affichage du répertoire.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun. Le module n'a pas de composants JavaScript front-end ou back-end.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucun. Le module n'a pas de style CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- Aucun. La configuration du module est rendue directement via `getContent()` dans le fichier principal du module, et sa fonctionnalité est purement basée sur la logique, non sur l'affichage.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il stocke sa configuration dans la table `ps_configuration`.

  - Entrée `ps_configuration` : `exgdis_groups` (stocke l'état activé/désactivé du paramètre principal).
- **Table des hooks enregistrés** : Le module n'enregistre explicitement aucun hook dans la table `ps_hook_module`. Sa fonctionnalité est implémentée via une surcharge de classe, qui est chargée par le mécanisme de surcharge de PrestaShop.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `override/classes/Product.php` | Lors des appels à `Product::getPriceStatic()` | Intercepte le calcul du prix pour empêcher les réductions de groupe sur les produits avec des prix spécifiques. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Exclure la réduction de groupe des produits avec prix spécifique », veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez télécharger les dernières versions et accéder aux ressources de support directement depuis [MyPresta.eu](https://mypresta.eu).
