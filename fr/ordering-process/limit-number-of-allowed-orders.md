---
title: "Limiter le nombre de commandes autorisées - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Limiter le nombre de commandes autorisées' par MyPresta.eu."
sidebar:
  label: "Limiter le nombre de commandes autorisées - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Limit number of allowed orders sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-number-of-allowed-orders.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/limit-number-of-allowed-orders/)
>
> ---


# Limiter le nombre de commandes autorisées

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module, où vous définissez les limites globales pour vos clients.

-   **Ce que fait ce paramètre :** C'est le paramètre principal du module. Il définit le nombre maximum de commandes que *tout* client peut passer dans votre boutique avant d'être empêché d'en passer d'autres.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur un nombre spécifique (par exemple, 3) :* Tout client ayant passé 3 commandes avec succès ne pourra plus passer une 4ème commande. Il verra un message l'empêchant de finaliser le paiement.
    -   *Lorsqu'il est défini sur 0 ou laissé vide :* Le module sera effectivement désactivé pour les limites globales, ce qui signifie que les clients peuvent passer un nombre illimité de commandes (sauf si des limites spécifiques aux clients sont définies, voir la section 4.2).
-   **Valeur recommandée :** Commencez par une valeur qui correspond à votre objectif commercial (par exemple, 1 pour une promotion stricte « un par client », 5 pour une limite générale). Si vous ne souhaitez limiter que des clients spécifiques, vous pouvez laisser ce champ vide et utiliser l'écran de gestion des clients dédié.
-   **Scénario / exemple de marchand :** Vous organisez une vente flash pour un produit très recherché et souhaitez vous assurer que chaque client n'a qu'une seule chance d'acheter. Vous définirez cette valeur sur `1`.

### 2.2 Écran d'administration dédié : Limites de commande client (Back Office > Modules > Limiter le nombre de commandes autorisées > Limites de commande client)

Cet écran vous permet de gérer les limites de commande individuelles pour des clients spécifiques, en annulant la limite globale définie dans la section 4.1.

-   **Nom de l'écran et emplacement du menu :** Vous pouvez accéder à cet écran en naviguant vers **Modules > Gestionnaire de modules**, en trouvant « Limiter le nombre de commandes autorisées », en cliquant sur « Configurer », puis en recherchant un onglet ou un lien intitulé « Limites de commande client » ou similaire. Alternativement, il peut apparaître directement dans votre menu principal PrestaShop sous une nouvelle entrée créée par le module (par exemple, **Clients > Limites de commande client**).
-   **Actions et paramètres disponibles :**

    -   **Recherche/Sélection de client :** Vous trouverez généralement une barre de recherche ou une liste déroulante pour sélectionner un client existant dans votre boutique.
    -   **Définir une limite individuelle :** Une fois un client sélectionné, vous pouvez saisir un nombre spécifique de commandes autorisées pour *ce client particulier*.
    -   **Afficher/Modifier les limites existantes :** Un tableau ou une liste affichera tous les clients pour lesquels vous avez défini des limites personnalisées, ainsi que leur limite actuelle et éventuellement leur nombre de commandes actuel. Vous pouvez modifier ou supprimer ces entrées.
    -   **Affichage de la devise :** Le module peut afficher des informations sur la devise (par exemple, `PS_CURRENCY_DEFAULT`) dans le contexte des commandes client, bien que les limites elles-mêmes soient des décomptes numériques de commandes, et non des valeurs monétaires.
-   **Effet des modifications :**

    -   *Ajout d'une nouvelle limite client :* Le client sélectionné sera désormais restreint par le nombre spécifique de commandes que vous avez défini pour lui, annulant la limite globale (si elle est définie).
    -   *Modification d'une limite client existante :* Le nombre de commandes autorisées du client sera mis à jour immédiatement.
    -   *Suppression d'une limite client :* Le client sera de nouveau régi par la limite de commande globale (si elle est définie), ou n'aura aucune limite si aucune limite globale n'est active.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

    1.  **Identifier les besoins spécifiques :** Déterminez si certains clients VIP, clients problématiques ou clients participant à des programmes spéciaux nécessitent des limites de commande uniques.
    2.  **Rechercher et ajouter :** Utilisez la fonction de recherche pour trouver le client.
    3.  **Appliquer la limite :** Saisissez le nombre maximum de commandes souhaité pour ce client.
    4.  **Surveiller :** Examinez périodiquement la liste des clients à limite personnalisée pour vous assurer que les paramètres sont toujours appropriés.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Nombre maximal de commandes autorisées (Global)** | 0 (Illimité) / Votre besoin commercial | Définit un nombre maximal de commandes à l'échelle de la boutique pour *tous* les clients. Empêche le paiement si dépassé. |
| Limites de commande client | **Recherche et sélection de client** | N/A | Permet de trouver et de sélectionner des clients spécifiques pour appliquer des limites individuelles. |
| Limites de commande client | **Limite de commande client individuelle** | N/A | Annule la limite globale pour un client spécifique. Empêche le paiement pour ce client si sa limite individuelle est dépassée. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Mes clients peuvent toujours passer des commandes illimitées, même après que j'ai défini une limite globale. Qu'est-ce qui ne va pas ?**
R :

1.  **Vérifiez le paramètre :** Vérifiez à nouveau que vous avez enregistré le paramètre « Nombre maximal de commandes autorisées (Global) » sur la page de configuration principale du module.
2.  **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Cela garantit que vos nouveaux paramètres sont appliqués immédiatement.
3.  **Statut du module :** Assurez-vous que le module est activé dans **Modules > Gestionnaire de modules**.
4.  **Dérogations spécifiques aux clients :** Vérifiez l'écran « Limites de commande client ». Si un client spécifique a une limite individuelle définie sur `0` ou un nombre très élevé, cela annulera la limite globale pour lui.

**Q : Puis-je définir une limite pour un client en fonction de la *valeur* de ses commandes, et non seulement du nombre ?**
R : Ce module limite spécifiquement le *nombre* de commandes. Il ne prend pas actuellement en charge la limitation basée sur la valeur monétaire. Pour les limites basées sur la valeur, vous auriez besoin d'un type de module différent ou d'un développement personnalisé.

**Q : Que se passe-t-il lorsqu'un client atteint sa limite ? Que voit-il ?**
R : Lorsqu'un client tente de passer une commande qui dépasserait sa limite, le module empêchera la finalisation de la commande. Généralement, un message clair sera affiché sur la page de paiement ou dans le panier, l'informant qu'il a atteint son nombre maximal de commandes autorisées et ne peut pas continuer. Le libellé exact peut dépendre de votre version de PrestaShop et de votre thème.

**Q : Ce module affecte-t-il les commandes passées ?**
R : Non, ce module n'affecte que les commandes *futures*. Il compte les commandes réussies existantes pour déterminer si une nouvelle tentative de commande dépasserait la limite, mais il ne modifie ni n'annule aucune commande précédemment passée.

**Q : Je souhaite lever temporairement une limite pour un client spécifique. Comment faire ?**
R : Allez à l'écran « Limites de commande client ». Trouvez le client, modifiez sa limite individuelle et définissez-la sur `0` (pour illimité) ou un nombre très élevé. N'oubliez pas d'enregistrer vos modifications. Vous pouvez toujours réappliquer une limite plus stricte plus tard.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Limiter le nombre de commandes autorisées » suit une architecture de module PrestaShop standard, tirant parti des hooks pour l'intégration et d'un `AdminController` pour la gestion des limites de clients spécifiques. Il fonctionne principalement en vérifiant l'historique des commandes des clients par rapport aux limites configurées pendant le processus de validation de commande. Le module s'appuie sur le système de configuration de PrestaShop pour les paramètres globaux et sur une table de base de données personnalisée pour les limites de clients individuelles.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Ce module n'utilise pas de contrôleurs front-office dédiés. Sa logique de vérification des limites est intégrée directement dans le processus de commande de PrestaShop via des hooks.
-   **Contrôleurs Back-Office Admin** :
    -   `controllers/admin/AdminLimitOrdersUserController.php`
        -   **Nom de la classe** : `AdminLimitOrdersUserController` (étend `ModuleAdminController`)
        -   **Responsabilité** : Ce contrôleur gère les limites de commande personnalisées pour les clients individuels. Il fournit une interface PrestaShop standard de `list` et `form` pour ajouter, modifier et supprimer les limites de commande spécifiques aux clients. Il interagit avec l'`ObjectModel` `LimitOrdersUser` (bien qu'aucun fichier `classes/` explicite n'ait été identifié, cela est implicite par le nom et la fonction du contrôleur). Il utilise probablement `PS_CURRENCY_DEFAULT` pour afficher le contexte de la devise, bien que les limites elles-mêmes soient numériques.
        -   **Nom de l'onglet** : Probablement « Limites de commande client » ou similaire, accessible depuis la page de configuration du module ou une entrée de menu dédiée.
    -   `controllers/admin/index.php`
        -   **Nom de la classe** : (Pas une classe, généralement un fichier vide ou une redirection pour la sécurité)
        -   **Responsabilité** : Ce fichier est généralement un espace réservé ou une mesure de sécurité pour empêcher la liste directe des répertoires. Il ne contient pas de logique de contrôleur active.

### 4.3 Classes et modèles principaux (`classes/`)

Sur la base des informations fournies, aucune classe personnalisée explicite n'a été identifiée dans le répertoire `classes/`. Cependant, l'`AdminLimitOrdersUserController` implique fortement l'existence d'une classe `ObjectModel`, probablement nommée `LimitOrdersUser`, qui serait mappée à une table de base de données personnalisée (par exemple, `ps_limitorders_user`). Cet `ObjectModel` définirait des champs tels que `id_customer` et `max_orders`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Portée** : Probablement Back-office.
    -   **Objectif** : Fournit une fonctionnalité d'autocomplétion, probablement pour rechercher et sélectionner des clients dans le formulaire `AdminLimitOrdersUserController` lors de la définition de limites individuelles. Il se lierait aux champs de saisie, enverrait des requêtes AJAX à un contrôleur backend (éventuellement l'`AdminLimitOrdersUserController` lui-même ou un point de terminaison AJAX dédié), et afficherait des suggestions.
-   `views/js/limitorders.js`
    -   **Portée** : Potentiellement à la fois Front-office (pour l'affichage des messages) et Back-office (pour la fonctionnalité générale du module).
    -   **Objectif** : Ce fichier contiendrait la logique JavaScript principale du module. Dans le Back-office, il pourrait gérer les validations de formulaire ou les éléments d'interface utilisateur dynamiques sur les pages de configuration. Dans le Front-office, si des messages ou des interactions dynamiques sont nécessaires lorsqu'un client atteint sa limite (par exemple, une fenêtre modale, une mise à jour dynamique du panier), ce script gérerait cela.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Portée** : Style d'administration du Back-office.
    -   **Objectif** : Style la liste déroulante d'autocomplétion et les champs de saisie utilisés dans le panneau d'administration, garantissant une expérience de recherche cohérente et conviviale pour les clients.
-   `views/css/limitorders.css`
    -   **Portée** : À la fois Front-office et Back-office.
    -   **Objectif** : Contient le style général pour tous les éléments visibles introduits par le module. Dans le Back-office, il styliserait les formulaires et les tableaux de configuration. Dans le Front-office, il styliserait les messages affichés aux clients lorsqu'ils atteignent leur limite de commande, garantissant qu'ils s'intègrent bien au thème de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   Ce module ne liste pas explicitement les templates dans le répertoire `hook/`, mais sa fonctionnalité implique qu'il se connecterait à `displayShoppingCart` ou `displayShoppingCartFooter` pour afficher des messages.
-   **Templates d'administration (`views/templates/admin/`)** :
    -   Les templates pour l'`AdminLimitOrdersUserController` (par exemple, `list.tpl`, `form.tpl`) résideraient ici, définissant la structure de l'interface de gestion des limites client.
-   **Templates Front-office (`views/templates/front/`)** :
    -   `views/templates/front/displayShoppingCart.tpl`
        -   **Objectif** : Ce template est probablement rendu lorsque le module se connecte à `displayShoppingCart`. Il contiendrait la logique pour afficher un message au client *dans son panier* s'il a atteint sa limite de commande, l'empêchant de passer au paiement.
    -   `views/templates/front/displayShoppingCartEmpty.tpl`
        -   **Objectif** : Ce template pourrait être utilisé dans un scénario spécifique où le module doit afficher un message lié aux limites de commande même lorsque le panier est vide, ou comme affichage de message de secours/alternatif. Son cas d'utilisation exact dépendrait de la logique interne du module pour différents états.
-   `lib/searchTool/views/scripts.tpl`
    -   **Objectif** : Ce template inclut probablement les fichiers JavaScript et CSS nécessaires pour les composants `autocomplete.js` et `autocomplete.css`, garantissant qu'ils sont chargés correctement dans le Back-office.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    -   `ps_configuration` : Stocke le nombre maximal de commandes autorisées global (par exemple, `LIMITORDERS_MAX_ORDERS`).
    -   `ps_limitorders_user` : (Table personnalisée implicite) Stocke les limites de commande individuelles des clients.
        -   `id_limitorders_user` (Clé primaire)
        -   `id_customer` (Clé étrangère vers `ps_customer`)
        -   `max_orders` (INT, le nombre maximal de commandes autorisé pour ce client spécifique)
-   **Table des hooks enregistrés** :

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Potentiellement pour charger les ressources CSS/JS du front-office ou pour des vérifications précoces. |
| `displayRightColumn` / `displayLeftColumn` | Rendu dans la colonne droite/gauche des pages du front-office. | Pourrait être utilisé pour afficher un message subtil sur les limites de commande, bien que moins probable pour ce module. |
| `displayProductButtons` / `displayProductExtraContent` | Rendu sur la page produit. | Pourrait être utilisé pour afficher un message si un client a atteint sa limite et ne peut pas ajouter au panier. |
| `displayShoppingCart` | Rendu dans le résumé du panier. | **CRITIQUE :** Probablement utilisé pour afficher des messages au client s'il a atteint sa limite de commande, empêchant le paiement. |
| `displayShoppingCartFooter` | Rendu sous le résumé du panier. | Similaire à `displayShoppingCart`, pour l'affichage de messages ou d'avertissements. |
| `displayFooter` | Rendu dans le pied de page de toutes les pages du front-office. | Moins probable pour la fonctionnalité principale, éventuellement pour des informations générales sur le module ou des scripts. |
| `actionValidateOrder` | Exécuté *après* qu'une commande a été validée et enregistrée avec succès dans la base de données. | **CRITIQUE :** Ce hook est essentiel pour que le module incrémente le nombre de commandes pour un client et mette potentiellement à jour son statut s'il a atteint sa limite. |
| `actionBeforeCartUpdateQuantity` | Exécuté avant qu'une quantité de produit ne soit mise à jour dans le panier. | Pourrait être utilisé pour effectuer une vérification préliminaire des limites avant d'autoriser l'ajout/la mise à jour d'un article. |
| `actionFrontControllerSetMedia` | Permet d'ajouter du CSS/JS aux pages du front-office. | Utilisé pour charger `limitorders.js` et `limitorders.css` sur les pages pertinentes du front-office. |
| `actionAdminControllerSetMedia` | Permet d'ajouter du CSS/JS aux pages du back-office. | Utilisé pour charger le CSS/JS spécifique à l'administration pour les écrans de configuration et `AdminLimitOrdersUserController`. |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` de toutes les pages du back-office. | Pour charger le CSS/JS spécifique à l'administration ou afficher des notifications d'administration. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Limiter le nombre de commandes autorisées », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à garantir le fonctionnement parfait de votre module et à vous aider à atteindre vos objectifs e-commerce.
