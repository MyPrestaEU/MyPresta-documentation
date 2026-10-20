---
title: "Exclure des produits sélectionnés de la livraison gratuite - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop « Exclure des produits sélectionnés de la livraison gratuite » par MyPresta.eu."
sidebar:
  label: "Exclure des produits sélectionnés de la livraison gratuite - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Exclude selected products from free shipping sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-selected-products-from-free-shipping.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/exclude-selected-products-from-free-shipping/)
>
> ---


# Exclure des produits sélectionnés de la livraison gratuite

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous définirez les règles fondamentales pour exclure les produits de la livraison gratuite.

#### 2.1.1 Paramètres généraux

- **Supprimer le code de réduction avec livraison gratuite**

  - **Ce que fait ce paramètre :** Cette option détermine si un bon de livraison gratuite (une `CartRule` qui accorde la livraison gratuite) doit être supprimé ou invalidé du panier du client si un produit exclu est présent.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Si un client applique un bon de livraison gratuite et ajoute ensuite un produit que vous avez marqué pour exclusion, le module tentera de supprimer ce bon de son panier. Cela garantit que même avec un bon, la livraison gratuite n'est pas accordée pour les articles exclus.
    - *Lorsqu'désactivé (NON) :* Les bons de livraison gratuite resteront actifs même si un produit exclu est dans le panier. Cela signifie qu'un client pourrait toujours obtenir la livraison gratuite via un bon, annulant l'exclusion basée sur le produit du module.
  - **Valeur recommandée :** **OUI**. Cela offre le contrôle le plus cohérent sur vos coûts d'expédition, empêchant la livraison gratuite même lorsqu'un bon est utilisé.
  - **Scénario / exemple de marchand :** Vous vendez de grands meubles qui entraînent toujours des frais d'expédition. Vous offrez également un bon « LIVRAISONGRATUITE » pour les commandes de plus de 100 €. Si un client ajoute un canapé (un produit exclu) et utilise le bon « LIVRAISONGRATUITE », l'activation de ce paramètre supprimera le bon, garantissant qu'il paie l'expédition du canapé.
- **Exclure les produits en rupture de stock**

  - **Ce que fait ce paramètre :** Cette option vous permet d'exclure automatiquement les produits actuellement en rupture de stock de l'éligibilité à la livraison gratuite.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Si un produit est en rupture de stock et dans le panier du client, et que vous l'avez également marqué pour exclusion, le module appliquera ses règles. C'est généralement moins pertinent car les produits en rupture de stock ne peuvent souvent pas être commandés de toute façon, mais cela assure la cohérence.
    - *Lorsqu'désactivé (NON) :* Le module ne prendra pas en compte l'état du stock lors de l'application de ses règles d'exclusion.
  - **Valeur recommandée :** **NON**. Ce paramètre est souvent redondant car les produits en rupture de stock ne peuvent généralement pas être ajoutés au panier ou commandés. Gardez-le désactivé sauf si vous avez une raison spécifique de l'utiliser (par exemple, autoriser les précommandes où la livraison gratuite devrait toujours être bloquée).
  - **Scénario / exemple de marchand :** Vous autorisez les précommandes pour certains articles. Si un article est en précommande (en rupture de stock) et est également un article volumineux et lourd que vous n'expédiez jamais gratuitement, l'activation de ce paramètre garantit que même en précommande, il contribue à désactiver la livraison gratuite.

#### 2.1.2 Règles d'exclusion de la livraison gratuite

- **Désactiver la livraison gratuite pour les produits sélectionnés**

  - **Ce que fait ce paramètre :** C'est la fonctionnalité principale. Il vous permet de spécifier des produits individuels qui, lorsqu'ils sont dans le panier, désactiveront la livraison gratuite.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Le module recherchera les produits spécifiques que vous avez ajoutés à la liste d'exclusion. Si l'un de ces produits est dans le panier du client, la livraison gratuite sera désactivée.
    - *Lorsqu'désactivé (NON) :* Aucun produit individuel ne désactivera la livraison gratuite, quelle que soit la liste d'exclusion.
  - **Valeur recommandée :** **OUI**. Activez ceci pour utiliser la fonctionnalité principale du module.
  - **Scénario / exemple de marchand :** Vous vendez des bijoux fins (petits, légers, généralement livraison gratuite) et aussi de grandes vitrines (lourdes, chères à expédier). Vous activeriez ceci et ajouteriez les vitrines à la liste d'exclusion.
- **Désactiver la livraison gratuite pour les catégories sélectionnées**

  - **Ce que fait ce paramètre :** Similaire aux produits, cette option vous permet de sélectionner des catégories de produits entières. Si *un* produit d'une catégorie sélectionnée est dans le panier du client, la livraison gratuite sera désactivée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Le module vérifiera si un produit du panier appartient à l'une des catégories que vous avez sélectionnées pour exclusion. Si c'est le cas, la livraison gratuite est désactivée.
    - *Lorsqu'désactivé (NON) :* Aucune catégorie ne désactivera la livraison gratuite.
  - **Valeur recommandée :** **OUI** si vous avez des groupes entiers de produits qui ne devraient jamais être éligibles à la livraison gratuite.
  - **Scénario / exemple de marchand :** Vous vendez à la fois des livres et de grandes impressions d'art. Toutes les impressions d'art nécessitent un emballage et une expédition spéciaux. Vous activeriez ceci et sélectionneriez la catégorie « Impressions d'art ». Toute impression d'art dans le panier désactivera la livraison gratuite.

#### 2.1.3 Interface de sélection de produits et de catégories

Sous ces paramètres, vous trouverez deux sections :

- **Produits à exclure de la livraison gratuite :** Une barre de recherche et une liste des produits actuellement exclus.
  - **Comment utiliser :** Commencez à taper le nom d'un produit dans la barre de recherche. Au fur et à mesure que vous tapez, une liste de produits correspondants apparaîtra. Cliquez sur un produit pour l'ajouter à la liste d'exclusion. Pour supprimer un produit, cliquez sur le « X » à côté de son nom dans la liste.
- **Catégories à exclure de la livraison gratuite :** Une vue arborescente des catégories de votre boutique avec des cases à cocher.
  - **Comment utiliser :** Cochez la case à côté de toute catégorie que vous souhaitez exclure. Tous les produits de cette catégorie (et de ses sous-catégories, selon le comportement des catégories de votre version de PrestaShop) désactiveront la livraison gratuite s'ils sont présents dans le panier.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration principale du module | Supprimer le code de réduction avec livraison gratuite | OUI | Garantit que les bons de livraison gratuite sont supprimés si des produits exclus sont dans le panier. |
| Configuration principale du module | Exclure les produits en rupture de stock | NON | Généralement pas nécessaire, car les articles en rupture de stock ne peuvent souvent pas être commandés. |
| Configuration principale du module | Désactiver la livraison gratuite pour les produits sélectionnés | OUI | Active l'exclusion de la livraison gratuite spécifique aux produits. |
| Configuration principale du module | Désactiver la livraison gratuite pour les catégories sélectionnées | OUI | Active l'exclusion de la livraison gratuite spécifique aux catégories. |
| Configuration principale du module | Produits à exclure de la livraison gratuite | (Vide) | Ajoutez des produits spécifiques ici à l'aide de l'outil de recherche. |
| Configuration principale du module | Catégories à exclure de la livraison gratuite | (Aucune sélectionnée) | Sélectionnez les catégories dans la vue arborescente. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais la livraison gratuite s'affiche toujours pour un produit exclu. Qu'est-ce qui ne va pas ?**
R :

1. **Vérifiez vos paramètres :** Vérifiez à nouveau que « Désactiver la livraison gratuite pour les produits sélectionnés » (ou les catégories) est activé, et que le produit/la catégorie spécifique est correctement ajouté(e) à la liste d'exclusion.
2. **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite. Parfois, PrestaShop met en cache les calculs d'expédition.
3. **Testez avec un nouveau panier :** Assurez-vous de tester avec un panier vierge, car le cache du navigateur ou les données de session pourraient interférer. Essayez dans une fenêtre de navigation privée.
4. **Conflit de bon :** Si vous utilisez un bon de livraison gratuite, assurez-vous que « Supprimer le code de réduction avec livraison gratuite » est activé.

**Q : Ce module affecte-t-il mes tarifs d'expédition standard ?**
R : Non, ce module n'affecte que la *disponibilité* de l'option « Livraison Gratuite » (soit via les règles de panier, soit via des transporteurs spécifiques de livraison gratuite). Il ne modifie pas vos tarifs d'expédition standard ni les autres configurations de transporteurs. Si la livraison gratuite est désactivée, les clients verront et paieront simplement vos options d'expédition régulières.

**Q : Puis-je exclure des produits en fonction du poids ou des dimensions au lieu de produits/catégories spécifiques ?**
R : Ce module cible spécifiquement les produits et les catégories. Les règles d'expédition intégrées de PrestaShop vous permettent de définir des seuils de livraison gratuite basés sur le poids total du panier ou le prix. Ce module ajoute une couche d'*exception* par-dessus ces règles. Si vous avez besoin de règles plus complexes basées uniquement sur le poids/les dimensions pour *tous* les produits, vous pourriez avoir besoin d'un module d'expédition plus avancé ou de configurations de transporteurs personnalisées.

**Q : Que se passe-t-il si un client a un produit exclu et un produit non exclu dans son panier ?**
R : Si *un* produit du panier figure sur votre liste d'exclusion (soit directement, soit via sa catégorie), la livraison gratuite sera désactivée pour l'ensemble du panier, même si d'autres produits du panier seraient normalement éligibles. La logique du module est : « si un produit exclu est présent, alors pas de livraison gratuite ».

**Q : J'utilise un thème personnalisé et l'outil de recherche de produits ne fonctionne pas correctement.**
R : Les thèmes personnalisés peuvent parfois interférer avec JavaScript.

1. **Vérifiez les erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (généralement F12) et recherchez les erreurs dans l'onglet « Console » lorsque vous essayez d'utiliser l'outil de recherche.
2. **Compatibilité du thème :** Assurez-vous que votre thème est entièrement compatible avec votre version de PrestaShop.
3. **Contactez le support :** Si vous voyez des erreurs ou si le problème persiste, fournissez des captures d'écran et des journaux de console au support MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Exclure des produits sélectionnés de la livraison gratuite » fonctionne principalement en surchargeant les classes PrestaShop de base liées à la gestion du panier et des règles de panier. Cela lui permet d'intercepter la logique de calcul de la livraison gratuite et d'appliquer ses règles d'exclusion avant que les options d'expédition finales ne soient présentées au client. Il utilise le système de surcharge de PrestaShop pour les classes `CartController`, `Cart` et `CartRule`. Le module comprend également un contrôleur d'administration dédié pour la recherche et la gestion des produits/catégories exclus.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `exfreeshipping/override/controllers/front/CartController.php`
    - **Nom de la classe et classe parente** : `CartController` (surcharge `CartControllerCore`)
    - **Responsabilité** : Cette surcharge est cruciale pour intercepter les actions liées au panier, en particulier lorsque des produits sont ajoutés ou supprimés, ou lorsque des calculs d'expédition sont effectués. Elle garantit que la logique du module est appliquée chaque fois que l'état du panier change, affectant l'éligibilité à la livraison gratuite.
- **Contrôleurs d'administration Back-Office** :

  - `exfreeshipping/controllers/admin/AdminExfreeshippingSearchController.php`
    - **Nom de l'onglet et entité gérée** : Ce contrôleur gère la fonctionnalité de recherche AJAX pour les produits dans la configuration du module. Il ne gère pas directement un `ObjectModel` spécifique mais fournit des données pour la liste d'exclusion des produits.
    - **Objectif** : Répond aux requêtes AJAX de la page de configuration du module pour rechercher des produits par nom, permettant à l'administrateur de sélectionner facilement les produits à exclure.
  - `exfreeshipping/controllers/admin/index.php`
    - **Objectif** : Il s'agit d'un fichier `index.php` vide standard souvent inclus dans les répertoires pour empêcher la liste des répertoires sur les serveurs web. Il ne contient aucune logique de contrôleur fonctionnelle.

### 4.3 Classes et modèles de base (`classes/`)

- `exfreeshipping/override/classes/Cart.php`

  - **Nom de la classe et classe parente** : `Cart` (surcharge `CartCore`)
  - **Table de base de données** : `ps_cart`
  - **Responsabilité** : Cette surcharge est centrale à la fonctionnalité du module. Elle modifie probablement les méthodes liées au calcul des frais d'expédition ou à l'éligibilité à la livraison gratuite au sein de l'objet `Cart`. Elle contiendra la logique pour vérifier si un produit du panier (ou sa catégorie) figure sur la liste d'exclusion et, si c'est le cas, pour désactiver le drapeau de livraison gratuite pour ce panier.
  - **Méthodes clés (probablement modifiées/étendues)** : `getProducts()`, `getPackageList()`, `getWsShippingCost()`, `getShippingCost()`, ou des méthodes similaires qui déterminent l'éligibilité à l'expédition.
- `exfreeshipping/override/classes/CartRule.php`

  - **Nom de la classe et classe parente** : `CartRule` (surcharge `CartRuleCore`)
  - **Table de base de données** : `ps_cart_rule`
  - **Responsabilité** : Cette surcharge est responsable de la gestion du paramètre « Supprimer le code de réduction avec livraison gratuite ». Elle modifie les méthodes liées à l'application ou à la validation des règles de panier pour supprimer les bons de livraison gratuite si un produit exclu est présent dans le panier.
  - **Méthodes clés (probablement modifiées/étendues)** : `checkValidity()`, `addCartRule()`, `removeCartRule()` ou des méthodes similaires qui interagissent avec les règles de panier et leur validité.
- `exfreeshipping/override/classes/index.php`

  - **Objectif** : Similaire à l'`index.php` d'administration, il s'agit d'un fichier vide pour empêcher la liste des répertoires.

### 4.4 Actifs JavaScript (`views/js/`)

- `exfreeshipping/lib/searchTool/views/js/autocomplete.js`
  - **Portée** : Back-office (page de configuration du module).
  - **Fonctionnalité** : Ce script alimente l'interface de recherche et de sélection de produits sur la page de configuration du module.
  - **Détails** :
    - Initialise un champ de saisie de saisie semi-automatique pour la recherche de produits.
    - Lie des écouteurs d'événements (par exemple, `keyup`, `change`, `click`) au champ de recherche et à la liste de résultats.
    - Envoie des requêtes AJAX à `AdminExfreeshippingSearchController` pour récupérer des suggestions de produits basées sur la saisie de l'utilisateur.
    - Gère l'affichage des résultats de recherche et permet aux administrateurs de sélectionner des produits, en les ajoutant à un champ de saisie masqué ou à une liste visible de produits exclus.
    - Gère la suppression des produits sélectionnés de la liste d'exclusion.

### 4.5 Feuilles de style CSS (`views/css/`)

- `exfreeshipping/lib/searchTool/views/css/autocomplete.css`
  - **Portée** : Back-office (page de configuration du module).
  - **Style** : Fournit le style pour le champ de saisie de saisie semi-automatique de la recherche de produits, la liste déroulante des résultats de recherche et l'affichage des produits exclus sélectionnés sur la page de configuration du module.
  - **Sélecteurs clés** : Inclut probablement des styles pour `.autocomplete-input`, `.autocomplete-results`, `.selected-product-tag`, etc. Les développeurs peuvent les surcharger dans leurs thèmes d'administration personnalisés si nécessaire.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles d'administration (`views/templates/admin/`)** :
  - `exfreeshipping/lib/searchTool/views/scripts.tpl`
    - **Objectif** : Ce modèle est probablement inclus dans la méthode `getContent()` du module pour rendre la structure HTML nécessaire à l'outil de recherche de produits, y compris le champ de saisie de recherche et la zone où les produits sélectionnés sont affichés. Il inclut également probablement la balise `<script>` pour charger `autocomplete.js`.
  - `exfreeshipping/views/tpl/selectedProducts.tpl`
    - **Objectif** : Ce modèle est utilisé pour rendre la liste des produits qui ont été sélectionnés pour exclusion de la livraison gratuite. Il est mis à jour dynamiquement par le JavaScript lorsque des produits sont ajoutés ou supprimés.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée pas de tables SQL personnalisées.
  - Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `exfreeshipping_oos`, `exfreeshipping_vcode`, `exfreeshipping_visibility_rule`, `exfreeshipping_visibility_products`, `exfreeshipping_visibility_cat`.
  - Les listes de produits et de catégories exclus sont stockées sous forme de tableaux sérialisés ou de chaînes séparées par des virgules dans `ps_configuration` sous `exfreeshipping_visibility_products` et `exfreeshipping_visibility_cat` respectivement.
- **Table des hooks enregistrés** :
Le module utilise principalement des surcharges plutôt que des appels de hook directs pour sa logique de base. Cependant, il peut enregistrer certains hooks standard à des fins d'initialisation ou d'affichage spécifiques.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Potentiellement utilisé pour charger tout CSS/JS spécifique au front-office, bien que l'impact principal du module soit la logique backend. |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Pourrait être utilisé pour la configuration initiale ou le chargement de scripts/styles très légers si nécessaire, mais pas directement pour la logique de base. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du back-office. | Utilisé pour charger `autocomplete.js` et `autocomplete.css` pour la page de configuration du module. |
| `actionCartSave` | Après qu'un panier est enregistré ou mis à jour. | C'est là que la logique de base du module pour vérifier les produits exclus et désactiver la livraison gratuite serait déclenchée ou réévaluée. |
| `actionValidateOrder` | Lorsqu'une commande est validée. | Garantit que les règles de livraison gratuite sont correctement appliquées à l'étape finale de la commande. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support technique pour le module « Exclure des produits sélectionnés de la livraison gratuite », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
