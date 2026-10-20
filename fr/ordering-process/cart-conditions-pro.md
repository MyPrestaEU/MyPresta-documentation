---
title: "Cart conditions pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Cart conditions pro par MyPresta.eu."
sidebar:
  label: "Cart conditions pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cart conditions pro sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/cart-conditions-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/cart-conditions-pro/)
>
> ---


# Cart conditions pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Cart conditions pro)

Ceci est l'écran de configuration principal du module, où vous définissez les comportements globaux et accédez aux zones spécifiques de gestion des conditions.

- **Ce que fait ce paramètre :** Contrôle le comportement général du module et fournit des liens rapides pour gérer vos conditions.
- **Effet de la modification de ce paramètre :** Détermine l'étendue de l'application des conditions et la manière dont certains cas limites sont gérés.

#### Paramètres généraux

1. **Exclure des clients des conditions**

   - **Ce que fait ce paramètre :** Vous permet de spécifier certains groupes de clients ou des clients individuels qui seront exemptés de toutes les conditions de panier que vous avez définies.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque activé (et clients/groupes sélectionnés) :* Les clients/groupes sélectionnés pourront toujours passer à la caisse, que leur panier remplisse ou non les conditions.
     - *Lorsque désactivé (ou aucun client/groupe sélectionné) :* Tous les clients seront soumis aux conditions du panier.
   - **Valeur recommandée :** « Désactivé » par défaut, sauf si vous avez des clients B2B spécifiques ou des VIP que vous souhaitez exempter.
   - **Scénario/exemple de marchand :** Vous avez un groupe de clients grossistes qui bénéficie toujours d'un traitement spécial et ne devrait pas être restreint par des valeurs de commande minimales.
2. **Exclure des produits des conditions**

   - **Ce que fait ce paramètre :** Vous permet de spécifier certains produits qui ne seront pas pris en compte ou affectés par les conditions du panier. Ceci est utile pour les cadeaux gratuits, les échantillons ou les articles promotionnels spécifiques.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque activé (et produits sélectionnés) :* Les produits sélectionnés seront ignorés lors de l'évaluation des conditions du panier. Par exemple, si vous avez une condition « minimum 3 articles », et qu'un client a 2 articles réguliers + 1 article exclu, la condition pourrait toujours échouer.
     - *Lorsque désactivé (ou aucun produit sélectionné) :* Tous les produits du panier seront pris en compte lors de l'évaluation des conditions.
   - **Valeur recommandée :** « Désactivé » par défaut. Activez uniquement si vous avez des produits spécifiques qui devraient être exemptés des conditions.
   - **Scénario/exemple de marchand :** Vous offrez un échantillon gratuit avec chaque commande. Vous ne voulez pas que cet échantillon compte pour une condition de quantité minimale de produit.
3. **Bloquer la commande de produits avec des dates de disponibilité variées**

   - **Ce que fait ce paramètre :** Cette option concerne spécifiquement les produits qui ont des dates de disponibilité différentes (par exemple, les articles en précommande avec des dates de sortie échelonnées). Si activée, elle empêche les clients de commander un mélange de produits immédiatement disponibles et de produits disponibles ultérieurement dans le même panier.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque « Activé » :* Si le panier d'un client contient des produits avec des dates de disponibilité différentes, il sera bloqué au moment du paiement. Il devra passer des commandes séparées pour les articles ayant des disponibilités différentes.
     - *Lorsque « Désactivé » :* Les clients peuvent commander des produits avec des dates de disponibilité variées dans un seul panier.
   - **Valeur recommandée :** « Désactivé » sauf si vous avez des raisons logistiques spécifiques de séparer les commandes en fonction de la disponibilité.
   - **Scénario/exemple de marchand :** Vous vendez à la fois des articles en stock et des articles en précommande. Pour simplifier l'expédition et éviter de retenir les commandes, vous souhaitez que les clients passent des commandes séparées pour les articles en précommande.

#### Liens de gestion des conditions

Sous les paramètres généraux, vous trouverez des liens pour gérer différents types de conditions. Ces liens vous mèneront à des écrans d'administration dédiés.

- **Gérer les conditions (Général) :** C'est ici que vous définissez des conditions générales basées sur les associations de produits, les catégories ou d'autres règles générales.
- **Gérer les conditions par pays :** Définissez des conditions qui s'appliquent uniquement aux clients de pays spécifiques.
- **Gérer les conditions de quantité :** Définissez des quantités minimales ou maximales de produits/catégories requises dans le panier.
- **Gérer les conditions de valeur :** Définissez des valeurs totales de panier minimales ou maximales requises.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminCartConditionController (Back Office > Modules > Cart conditions pro > Gérer les conditions)

Cet écran vous permet de définir des conditions générales, souvent basées sur des associations de produits ou de catégories.

- **Nom de l'écran et emplacement du menu :** « Gérer les conditions » (accessible depuis la page de configuration principale du module).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche toutes les conditions générales existantes avec leurs noms, les produits/catégories associés et leur statut.
  - **Bouton Ajouter une nouvelle condition :** Vous permet de créer une nouvelle condition.
    - **Nom de la condition :** Un nom descriptif pour votre référence interne.
    - **Produits/Catégories :** Sélectionnez des produits spécifiques ou des catégories entières qui doivent être présentes (ou non présentes) dans le panier.
    - **Groupes de clients :** Appliquez cette condition uniquement à des groupes de clients spécifiques.
    - **Quantité minimale/maximale :** Définissez une plage pour le nombre de produits/catégories sélectionnés.
    - **Valeur minimale/maximale :** Définissez une plage pour la valeur totale des produits/catégories sélectionnés.
    - **Message :** Le message affiché au client si la condition n'est pas remplie.
    - **Actif :** Active ou désactive la condition.
  - **Boutons Modifier/Supprimer :** Modifiez ou supprimez les conditions existantes.
- **Effet des modifications :**
  - L'ajout d'une nouvelle condition applique immédiatement cette règle aux paniers des clients.
  - La modification d'une condition met à jour ses critères et son message.
  - La suppression d'une condition supprime la restriction.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Révisez régulièrement vos conditions, surtout après l'ajout de nouveaux produits, catégories ou le lancement de promotions, pour vous assurer qu'elles correspondent à votre stratégie de vente actuelle.

#### 2.2.2 AdminCartAssociationsConditionController (Back Office > Modules > Cart conditions pro > Gérer les conditions > (Condition spécifique) > Associations)

Cet écran est généralement accessible lors de la modification d'une condition générale et vous permet de spécifier quels produits ou catégories sont *associés* à cette condition.

- **Nom de l'écran et emplacement du menu :** Accessible en modifiant une condition depuis « Gérer les conditions ».
- **Actions et paramètres disponibles :**
  - **Rechercher et sélectionner des produits/catégories :** Outils pour trouver et ajouter des produits spécifiques ou des catégories entières qui font partie de cette condition.
  - **Liste des produits/catégories sélectionnés :** Affiche tous les articles actuellement associés à la condition.
  - **Bouton Supprimer :** Supprime un article de l'association.
- **Effet des modifications :** Impacte directement les produits ou catégories évalués par la condition parente. Par exemple, si une condition stipule « Le panier doit contenir au moins 2 articles de la catégorie 'Électronique' », cet écran est l'endroit où vous définissez quels produits appartiennent à cette catégorie « Électronique » pour cette condition spécifique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Lors de la création ou de la mise à jour d'une condition, assurez-vous que tous les produits et catégories pertinents sont correctement associés.

#### 2.2.3 AdminCartCountryConditionController (Back Office > Modules > Cart conditions pro > Gérer les conditions par pays)

Cet écran vous permet de définir des conditions spécifiques au pays de livraison du client.

- **Nom de l'écran et emplacement du menu :** « Gérer les conditions par pays » (accessible depuis la page de configuration principale du module).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche les conditions spécifiques aux pays existantes.
  - **Bouton Ajouter une nouvelle condition :**
    - **Pays :** Sélectionnez le pays cible.
    - **Quantité minimale/maximale :** Pour tous les produits du panier, ou des produits/catégories spécifiques.
    - **Valeur minimale/maximale :** Pour la valeur totale du panier.
    - **Message :** Le message affiché si la condition n'est pas remplie.
    - **Actif :** Active ou désactive.
- **Effet des modifications :** Applique des règles de panier spécifiques uniquement aux clients dont l'adresse de livraison se trouve dans le pays sélectionné.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utile pour les boutiques internationales avec des frais d'expédition, des réglementations douanières ou des stratégies de marché variables par pays.

#### 2.2.4 AdminCartQuantityConditionController (Back Office > Modules > Cart conditions pro > Gérer les conditions de quantité)

Cet écran se concentre sur les conditions liées au nombre total d'articles dans le panier, ou à la quantité d'articles/catégories spécifiques.

- **Nom de l'écran et emplacement du menu :** « Gérer les conditions de quantité » (accessible depuis la page de configuration principale du module).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche toutes les conditions basées sur la quantité.
  - **Bouton Ajouter une nouvelle condition :**
    - **Nom de la condition :**
    - **Quantité totale minimale/maximale :** Pour l'ensemble du panier.
    - **Quantité minimale/maximale de produits/catégories spécifiques :** Sélectionnez des articles et définissez des règles de quantité pour ceux-ci.
    - **Groupes de clients :** Appliquer à des groupes spécifiques.
    - **Message :**
    - **Actif :**
- **Effet des modifications :** Applique des règles basées sur le nombre d'articles dans le panier, ce qui peut être utilisé pour encourager les achats en gros ou gérer l'inventaire.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez ceci pour les promotions « achetez X obtenez Y », la quantité minimale de commande (MOQ) pour la vente en gros, ou pour vous assurer que les clients atteignent un certain seuil pour la livraison gratuite.

#### 2.2.5 AdminCartValueConditionController (Back Office > Modules > Cart conditions pro > Gérer les conditions de valeur)

Cet écran est destiné à définir des conditions basées sur la valeur monétaire totale du panier du client.

- **Nom de l'écran et emplacement du menu :** « Gérer les conditions de valeur » (accessible depuis la page de configuration principale du module).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche les conditions basées sur la valeur existantes.
  - **Bouton Ajouter une nouvelle condition :**
    - **Nom de la condition :**
    - **Valeur totale minimale/maximale du panier :** Définissez une plage pour la valeur totale du panier.
    - **Groupes de clients :**
    - **Message :**
    - **Actif :**
- **Effet des modifications :** Applique des règles basées sur la valeur monétaire du panier, impactant directement la valeur moyenne des commandes.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Idéal pour définir une valeur de commande minimale pour la livraison gratuite, ou une valeur de commande minimale générale pour assurer la rentabilité.

#### 2.2.6 index.php (cartcon/controllers/admin/index.php)

Ce fichier est une pratique standard de PrestaShop pour empêcher la liste des répertoires et ne représente pas un écran configurable. Il contient simplement `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` pour rediriger si quelqu'un tente d'accéder directement au répertoire.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Exclure des clients des conditions | Désactivé | Exempte des clients/groupes spécifiques de toutes les conditions. |
| | Exclure des produits des conditions | Désactivé | Exempte des produits spécifiques de toutes les conditions. |
| | Bloquer la commande de produits avec des dates de disponibilité variées | Désactivé | Empêche les commandes mixtes d'articles en stock et en précommande. |
| **Gérer les conditions** | Nom de la condition | Défini par l'utilisateur | Libellé interne de la condition. |
| | Produits/Catégories | Défini par l'utilisateur | Sélectionne les articles/catégories requis ou restreints. |
| | Groupes de clients | Tous | Applique la condition à des segments de clients spécifiques. |
| | Quantité min/max | Défini par l'utilisateur | Définit la plage de quantité pour les articles/catégories sélectionnés. |
| | Valeur min/max | Défini par l'utilisateur | Définit la plage de valeur pour les articles/catégories sélectionnés. |
| | Message | Défini par l'utilisateur | Message affiché au client lorsque la condition n'est pas remplie. |
| | Actif | Oui | Active/désactive la condition. |
| **Gérer les conditions par pays** | Pays | Défini par l'utilisateur | Cible des pays spécifiques pour les conditions. |
| | Quantité min/max | Défini par l'utilisateur | Plage de quantité pour les paniers du pays sélectionné. |
| | Valeur min/max | Défini par l'utilisateur | Plage de valeur pour les paniers du pays sélectionné. |
| | Message | Défini par l'utilisateur | Message client en cas d'échec spécifique au pays. |
| | Actif | Oui | Active/désactive la condition par pays. |
| **Gérer les conditions de quantité** | Nom de la condition | Défini par l'utilisateur | Libellé interne de la condition de quantité. |
| | Quantité totale min/max | Défini par l'utilisateur | Plage de quantité pour l'ensemble du panier. |
| | Quantité min/max de produits/catégories spécifiques | Défini par l'utilisateur | Plage de quantité pour les articles/catégories sélectionnés. |
| | Groupes de clients | Tous | Applique à des segments de clients spécifiques. |
| | Message | Défini par l'utilisateur | Message client en cas d'échec de quantité. |
| | Actif | Oui | Active/désactive la condition de quantité. |
| **Gérer les conditions de valeur** | Nom de la condition | Défini par l'utilisateur | Libellé interne de la condition de valeur. |
| | Valeur totale min/max du panier | Défini par l'utilisateur | Plage de valeur pour l'ensemble du panier. |
| | Groupes de clients | Tous | Applique à des segments de clients spécifiques. |
| | Message | Défini par l'utilisateur | Message client en cas d'échec de valeur. |
| | Actif | Oui | Active/désactive la condition de valeur. |

## 3. Dépannage pour le marchand et Foire aux questions (FAQ)

**Q1 : Mes conditions sont définies, mais elles ne semblent pas fonctionner sur le front office. Qu'est-ce qui ne va pas ?**
**R1 :**

- **Vérifier le statut de la condition :** Assurez-vous que l'interrupteur « Actif » pour chaque condition que vous avez définie est sur « Oui ».
- **Vider le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
- **Position du module :** Vérifiez que le module est correctement accroché. Les hooks `displayShoppingCart` et `displayPaymentTop` sont cruciaux. Si votre thème a des hooks personnalisés, vous pourriez avoir besoin de l'aide d'un développeur.
- **Groupes de clients :** Vérifiez à nouveau si les conditions sont appliquées aux bons groupes de clients, et si votre client de test appartient à ce groupe.
- **ID de produit/catégorie :** Lors de la sélection de produits ou de catégories, assurez-vous d'avoir choisi les bons. Parfois, des noms similaires peuvent prêter à confusion.

**Q2 : Le message affiché aux clients n'est pas clair ou ne s'affiche pas correctement avec mon thème.**
**R2 :**

- **Modifier le message :** Allez dans la condition spécifique (par exemple, Gérer les conditions de valeur, puis modifiez la condition) et mettez à jour le champ « Message » avec un texte plus clair et plus utile.
- **Style du thème :** L'apparence visuelle (police, couleur, taille) du message est contrôlée par le CSS de votre thème PrestaShop. Si vous devez modifier le style, vous devrez consulter un web designer ou un développeur pour ajouter des règles CSS personnalisées à votre thème. Les fichiers CSS du module (`cartcon.css`) fournissent le style de base.

**Q3 : Puis-je définir des conditions différentes pour différentes langues/pays ?**
**R3 :**

- **Conditions spécifiques au pays :** Oui, utilisez l'écran « Gérer les conditions par pays » pour définir des règles qui s'appliquent uniquement aux clients de pays spécifiques.
- **Messages multilingues :** Lors de la modification d'une condition, le champ « Message » dispose généralement d'un sélecteur de langue (une icône de drapeau). Cliquez dessus pour fournir des traductions de votre message dans toutes les langues actives de votre boutique.

**Q4 : Je veux exclure un produit spécifique de TOUTES les conditions. Comment faire ?**
**R4 :**

- Sur la page de configuration principale du module (Back Office > Modules > Configurer > Cart conditions pro), utilisez le paramètre « Exclure des produits des conditions ». Vous pouvez rechercher et sélectionner les produits spécifiques que vous souhaitez exempter.

**Q5 : Le module bloque le passage à la caisse, mais je ne trouve pas quelle condition en est la cause.**
**R5 :**

- **Examiner toutes les conditions :** Parcourez « Gérer les conditions », « Gérer les conditions par pays », « Gérer les conditions de quantité » et « Gérer les conditions de valeur » une par une. Vérifiez le statut « Actif » de chacune et examinez leurs critères.
- **Tester systématiquement :** Si vous avez de nombreuses conditions, essayez de les désactiver une par une (ou par groupes) et de tester le panier jusqu'à ce que vous identifiiez le coupable. Ensuite, réactivez-les et ajustez la condition problématique.
- **Vérifier le groupe de clients :** Assurez-vous que votre client de test ne fait pas partie d'un groupe de clients exclu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Cart conditions pro » suit le modèle MVC (Modèle-Vue-Contrôleur) standard de PrestaShop, étendant principalement `Module` pour sa configuration principale et `AdminController` pour les interfaces de gestion dédiées. Il utilise le système de hooks de PrestaShop pour injecter de la logique et afficher des messages à des points critiques du front-office (panier, paiement) et utilise `ObjectModel` implicitement pour gérer ses différentes entités de condition. Le module s'appuie sur des tables de base de données personnalisées pour stocker ses règles de condition complexes.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Le module ne semble pas avoir de contrôleurs frontaux dédiés dans l'inventaire fourni. La logique et l'affichage du front-office sont probablement gérés directement via le fichier principal du module `cartcon.php` par le biais de rappels de hooks.

#### Contrôleurs d'administration Back-Office

Tous les contrôleurs d'administration étendent `ModuleAdminController` (ou `AdminController` dans les anciennes versions de PrestaShop) et sont responsables de la gestion des différents types de conditions.

- `cartcon/controllers/admin/AdminCartAssociationsConditionController.php`

  - **Nom de la classe :** `AdminCartAssociationsConditionController`
  - **Classe parente :** `ModuleAdminController`
  - **Responsabilité :** Gère les associations (produits, catégories) liées à une condition de panier générale spécifique. Ce contrôleur fournit l'interface pour rechercher et sélectionner les produits/catégories qui font partie des critères d'une condition. Il interagit avec la table `cartcon_ass`.
- `cartcon/controllers/admin/AdminCartConditionController.php`

  - **Nom de la classe :** `AdminCartConditionController`
  - **Classe parente : `ModuleAdminController`**
  - **Responsabilité :** Gère les conditions de panier principales et générales. C'est l'interface principale pour créer, modifier et supprimer des conditions basées sur la présence de produits/catégories, la quantité ou la valeur. Il interagit avec la table `cartcon`.
- `cartcon/controllers/admin/AdminCartCountryConditionController.php`

  - **Nom de la classe :** `AdminCartCountryConditionController`
  - **Classe parente :** `ModuleAdminController`
  - **Responsabilité :** Gère les conditions de panier spécifiquement liées aux pays des clients. Il permet de définir des règles qui ne s'appliquent que lorsque le pays de livraison du client correspond à un pays spécifié. Il interagit avec la table `cartcon_country`.
- `cartcon/controllers/admin/AdminCartQuantityConditionController.php`

  - **Nom de la classe :** `AdminCartQuantityConditionController`
  - **Classe parente :** `ModuleAdminController`
  - **Responsabilité :** Gère les conditions basées sur la quantité totale d'articles dans le panier ou la quantité de produits/catégories spécifiques. Il interagit avec la table `cartcon_quantity`.
- `cartcon/controllers/admin/AdminCartValueConditionController.php`

  - **Nom de la classe :** `AdminCartValueConditionController`
  - **Classe parente :** `ModuleAdminController`
  - **Responsabilité :** Gère les conditions basées sur la valeur monétaire totale du panier. Il interagit avec la table `cartcon_value`.
- `cartcon/controllers/admin/index.php`

  - **Responsabilité :** Fichier de sécurité PrestaShop standard pour empêcher la liste des répertoires. Il redirige vers le répertoire parent.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni ne liste pas de fichiers explicites dans un répertoire `classes/`. Cela suggère que la logique principale du module et les définitions `ObjectModel` (le cas échéant) sont soit intégrées dans le fichier principal `cartcon.php`, soit dans les fichiers du contrôleur d'administration eux-mêmes, ce qui est un modèle courant pour les modules plus simples ou les anciennes versions de PrestaShop. Si des `ObjectModel` sont utilisés, leurs tableaux `$definition` se trouveraient dans le contrôleur ou la classe de module principale respective.

### 4.4 Actifs JavaScript (`views/js/`)

- `cartcon/lib/searchTool/views/js/autocomplete.js`

  - **Portée :** Back-office.
  - **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour la recherche de produits, de catégories ou de clients dans les formulaires d'administration (par exemple, lors de la configuration d'exclusions ou d'associations de conditions). Il se lie probablement à des champs de saisie, envoie des requêtes AJAX à un point de terminaison de recherche et affiche des suggestions.
- `cartcon/views/js/cartcon.js`

  - **Portée :** Front-office et potentiellement Back-office.
  - **Responsabilité :**
    - **Front-office :** Gère l'affichage dynamique des messages de condition de panier, la désactivation/activation du bouton « Passer à la caisse » en fonction des réponses AJAX du serveur concernant la validité du panier. Il peut écouter les mises à jour du panier (`prestashop.on('updateCart', ...)` ou des événements similaires) pour réévaluer les conditions.
    - **Back-office :** Pourrait contenir la logique de validation de formulaire, la visibilité dynamique des champs ou d'autres améliorations de l'interface utilisateur spécifiques aux pages de configuration du module.

### 4.5 Feuilles de style CSS (`views/css/`)

- `cartcon/lib/searchTool/views/css/autocomplete.css`

  - **Portée :** Back-office.
  - **Responsabilité :** Style les listes déroulantes de suggestions d'autocomplétion et les champs de saisie de recherche utilisés dans les formulaires d'administration, garantissant une expérience de recherche cohérente et conviviale.
- `cartcon/views/css/cartcon.css`

  - **Portée :** Front-office et Back-office.
  - **Responsabilité :**
    - **Front-office :** Style les messages de notification affichés sur la page du panier, la page de paiement ou la page du produit lorsque les conditions ne sont pas remplies. Il définit l'apparence des boîtes d'avertissement, du texte et potentiellement l'état désactivé du bouton de paiement.
    - **Back-office :** Fournit le style des formulaires de configuration du module et des tableaux de liste, garantissant leur bonne intégration avec le thème du back office de PrestaShop.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** Recherchez des classes comme `.cartcon-alert`, `.cartcon-message`, `.cartcon-disabled-button` ou similaires dans ce fichier pour cibler et personnaliser la sortie front-office du module.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

La logique d'affichage du front-office du module est probablement intégrée directement dans les méthodes de hook du fichier principal `cartcon.php`, qui rendent ensuite ces templates.

- `cartcon/views/templates/front/displayShoppingCart.tpl`

  - **Rendu dans le hook :** `displayShoppingCart`
  - **Objectif :** Affiche les messages de condition du panier et désactive potentiellement le bouton de paiement sur la page principale du panier si les conditions ne sont pas remplies. Il reçoit des variables de la méthode `hookDisplayShoppingCart` du module, indiquant la validité du panier et le message à afficher.
- `cartcon/views/templates/front/displayShoppingCartEmpty.tpl`

  - **Rendu dans le hook :** Potentiellement `displayShoppingCart` ou un hook connexe lorsque le panier est vide.
  - **Objectif :** Fournit un template spécifique pour afficher des messages ou un contenu alternatif lorsque le panier est vide, potentiellement lié aux exigences de commande minimale.
- `cartcon/views/templates/front/productActions.tpl`

  - **Rendu dans le hook :** `displayProductActions` (généralement près du bouton « Ajouter au panier » sur la page du produit).
  - **Objectif :** Peut être utilisé pour afficher des indices ou des avertissements subtils sur la page du produit elle-même si l'ajout du produit violerait une condition de panier ou si le produit nécessite l'achat d'autres articles avec lui.

#### Templates d'administration (`views/templates/admin/`)

- `cartcon/lib/searchTool/views/scripts.tpl`

  - **Objectif :** Inclut probablement des dépendances JavaScript ou initialise les scripts d'autocomplétion pour les formulaires d'administration.
- `cartcon/views/templates/admin/AdminCartAssociationsCondition.tpl`

  - **Objectif :** Le template principal pour le `AdminCartAssociationsConditionController`, affichant l'interface pour gérer les associations produit/catégorie pour une condition. Cela inclurait les champs de recherche, les listes d'éléments sélectionnés et les boutons de sauvegarde.
- `cartcon/views/templates/admin/adminSearchCustomer.tpl`

  - **Objectif :** Template pour l'interface de recherche de clients, utilisée lors de l'exclusion de clients des conditions.
- `cartcon/views/templates/admin/script.tpl`

  - **Objectif :** Template de script d'administration général, incluant potentiellement du JavaScript spécifique au module ou des variables de configuration pour le back office.
- `cartcon/views/templates/admin/search-attribute-value-result.tpl`

  - **Objectif :** Template pour afficher les résultats d'une recherche d'attribut/valeur dans le panneau d'administration, probablement utilisé conjointement avec les recherches de produits.
- `cartcon/views/templates/admin/search-attribute-value.tpl`

  - **Objectif :** Template pour le champ de saisie de recherche et les éléments d'interface utilisateur associés pour la recherche d'attributs/valeurs de produits dans l'administration.
- `cartcon/views/templates/admin/selectedProducts.tpl`

  - **Objectif :** Template pour afficher la liste des produits qui ont été sélectionnés et associés à une condition particulière dans les formulaires d'administration.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module crée des tables personnalisées pour stocker ses différentes conditions et associations. Ces tables sont généralement préfixées par `ps_cartcon_` ou `cartcon_`.

- `ps_cartcon` : Stocke les conditions générales du panier (nom, message, statut actif, etc.).
- `ps_cartcon_ass` : Stocke les associations entre les conditions et les produits/catégories spécifiques.
- `ps_cartcon_country` : Stocke les conditions spécifiques au pays.
- `ps_cartcon_quantity` : Stocke les conditions basées sur la quantité.
- `ps_cartcon_value` : Stocke les conditions basées sur la valeur.
- `ps_configuration` : Les paramètres du module comme `CARTCON_CUSTOMERS`, `ccon_visibility_rule`, `CARTCON_FUTURE`, etc., y sont stockés.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour charger les actifs CSS et JavaScript du module pour le front-office et le back-office. |
| `displayPaymentTop` | En haut de la page de sélection du paiement pendant le passage à la caisse. | Critique pour réévaluer les conditions du panier juste avant le paiement et bloquer si nécessaire. |
| `displayShoppingCart` | Sur la page principale du panier. | Hook principal pour afficher les messages de condition et désactiver le bouton de paiement. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé et que ses médias (JS/CSS) sont définis. | Utilisé pour charger des actifs JS/CSS spécifiques pour les pages de configuration du back-office du module. |
| `displayProductActions` | Généralement près du bouton « Ajouter au panier » sur la page du produit. | Peut être utilisé pour afficher des indices ou des avertissements de condition spécifiques au produit. |
| `actionCartSave` | Après l'enregistrement d'un panier (par exemple, produit ajouté/supprimé, quantité modifiée). | (Implicite/Probable) Le module utiliserait probablement un hook `actionCartSave` ou similaire pour déclencher la réévaluation des conditions du panier côté serveur, ce qui informe ensuite le JS du front-office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Cart conditions pro », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir le fonctionnement optimal du module avec votre boutique PrestaShop.
