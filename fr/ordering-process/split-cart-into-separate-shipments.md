---
title: "Diviser le panier en plusieurs expéditions - Manuel du Marchand & Guide de Configuration"
description: ""
sidebar:
  label: "Diviser le panier en plusieurs expéditions - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Split cart into separate shipments sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/split-cart-into-separate-shipments.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/split-cart-into-separate-shipments/)
>
> ---


# Diviser le panier en plusieurs expéditions

## 1. Guide de configuration complet (chaque paramètre regroupé par écran)

Le module "Diviser le panier en plusieurs expéditions" introduit plusieurs nouveaux écrans et options puissants dans votre Back Office PrestaShop.

### 1.1 Page de configuration du module (Back Office > Modules > Configurer > Diviser le panier en plusieurs expéditions)

C'est la page de configuration principale à laquelle vous accédez immédiatement après l'installation ou en cliquant sur "Configurer" depuis le Gestionnaire de modules. Elle contient les paramètres généraux du comportement du module.

-   **Activer le module :**

    -   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module dans votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module divisera activement les paniers selon vos règles pendant le processus de commande.
        -   *Lorsqu'il est désactivé :* La logique de division du module sera ignorée, et PrestaShop reviendra à son comportement par défaut d'expédition unique.
    -   **Valeur recommandée :** OUI (une fois que vous avez configuré vos règles).
    -   **Scénario / exemple de marchand :** Vous pourriez le désactiver temporairement si vous effectuez une maintenance ou si vous dépannez d'autres parties de votre processus de commande.
-   **Mode Débogage :**

    -   **Ce que fait ce paramètre :** Active un mode spécial qui peut afficher des informations techniques supplémentaires ou des journaux pour aider à identifier les problèmes.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Peut afficher des messages d'erreur ou des étapes de traitement détaillées sur le front office (visibles par les clients) ou dans la console de développement de votre navigateur. Ceci est utile pour les développeurs.
        -   *Lorsqu'il est désactivé :* Le module fonctionne silencieusement, sans afficher d'informations de débogage.
    -   **Valeur recommandée :** NON (toujours désactiver dans une boutique de production en ligne).
    -   **Scénario / exemple de marchand :** Si vous travaillez avec un développeur pour comprendre pourquoi un panier spécifique ne se divise pas comme prévu, il pourrait vous demander de l'activer temporairement.
-   **Afficher le résumé de la division sur la page de confirmation de commande :**

    -   **Ce que fait ce paramètre :** Contrôle si les clients voient un résumé de la façon dont leur commande a été divisée en différentes expéditions sur la page finale de confirmation de commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Les clients verront un récapitulatif clair des articles qui ont été inclus dans chaque groupe d'expédition et du transporteur choisi pour chacun, confirmant leurs sélections.
        -   *Lorsqu'il est désactivé :* La page de confirmation de commande affichera un résumé standard sans les informations détaillées de la division.
    -   **Valeur recommandée :** OUI.
    -   **Scénario / exemple de marchand :** L'activation de cette option améliore la transparence et rassure les clients sur le fait que leurs choix d'expédition spécifiques pour chaque colis ont été correctement appliqués.
-   **Autoriser le client à choisir des points de retrait (le cas échéant) :**

    -   **Ce que fait ce paramètre :** Si vous avez des transporteurs qui proposent la livraison en point de retrait (par exemple, Mondial Relay, Colissimo Point Relais), ce paramètre permet aux clients de sélectionner un lieu de retrait spécifique pour chaque groupe d'expédition pertinent.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Pour les transporteurs configurés avec des points de retrait, les clients verront une option pour choisir un lieu de retrait pendant le processus de commande pour l'expédition correspondante.
        -   *Lorsqu'il est désactivé :* Les clients ne pourront sélectionner que la livraison à domicile ou d'autres options d'expédition standard, même si les transporteurs prennent en charge les points de retrait.
    -   **Valeur recommandée :** OUI (si vous utilisez des transporteurs avec des points de retrait).
    -   **Scénario / exemple de marchand :** Si vous proposez Mondial Relay, l'activation de cette option permet aux clients de faire livrer un article lourd à un point de retrait pratique près de leur domicile ou de leur travail, améliorant ainsi leur expérience.

### 1.2 Écrans d'administration dédiés : Règles d'expédition (Back Office > Livraison > Règles de division des expéditions)

Cet écran est l'endroit où vous définissez la logique de la façon dont les articles de votre panier doivent être regroupés en expéditions distinctes. C'est le cœur de la fonctionnalité du module.

-   **Nom de l'écran et emplacement du menu :** **Règles de division des expéditions** (situé sous **Livraison** dans le menu de votre Back Office PrestaShop).
-   **Actions et paramètres disponibles :**
    -   **Tableau de liste des règles :** Affiche toutes vos règles de regroupement définies. Chaque règle a un nom, un statut (actif/inactif), une priorité et un résumé de ses conditions et actions.
    -   **Bouton "Ajouter une nouvelle règle" :** Cliquer sur ce bouton vous permet de créer une nouvelle règle.
    -   **Actions Modifier/Supprimer :** Pour chaque règle de la liste, vous pouvez modifier ses détails ou la supprimer.
    -   **Bascule Activer/Désactiver :** Activez ou désactivez rapidement une règle sans la supprimer.
    -   **Réorganisation par glisser-déposer :** Les règles sont traitées par ordre de priorité. Vous pouvez faire glisser et déposer des règles pour modifier leur ordre d'exécution. Les règles de priorité plus élevée sont traitées en premier.
-   **Effet des modifications :**
    -   **Ajout/Modification de règles :** Impacte directement la façon dont les paniers sont divisés pendant le processus de commande. Une règle bien définie peut garantir que des produits spécifiques sont toujours expédiés séparément ou ensemble.
    -   **Activation/Désactivation de règles :** Contrôle si la logique d'une règle est appliquée.
    -   **Modification de la priorité :** Détermine quelle règle a la priorité si plusieurs règles peuvent s'appliquer au même produit. Les règles de priorité plus élevée (apparaissant plus haut dans la liste) sont évaluées en premier.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    1.  **Identifier les besoins de regroupement :** Réfléchissez à vos produits. Avez-vous des articles surdimensionnés, fragiles, des articles provenant de différents entrepôts ou des articles nécessitant une manipulation spéciale ?
    2.  **Créer des règles :** Pour chaque besoin de regroupement, créez une nouvelle règle.
        -   **Conditions :** Définissez *quand* la règle s'applique. Cela pourrait être basé sur :
            -   **Produit :** Produits spécifiques, catégories, fabricants, fournisseurs ou caractéristiques du produit.
            -   **Panier :** Valeur totale du panier, nombre d'articles, groupes de clients spécifiques.
            -   **Expédition :** Transporteurs ou zones spécifiques.
        -   **Actions :** Définissez *ce que* la règle fait. Cela pourrait être :
            -   **Forcer l'expédition séparée :** Toujours placer les articles correspondants dans leur propre groupe d'expédition.
            -   **Forcer la même expédition :** S'assurer que les articles correspondants restent toujours ensemble dans une seule expédition.
            -   **Exclure du traitement des règles :** Empêcher d'autres règles d'affecter ces articles.
    3.  **Définir la priorité :** Organisez vos règles de la plus spécifique (par exemple, "La verrerie fragile est toujours expédiée seule") à la plus générale (par exemple, "Tous les articles surdimensionnés sont expédiés séparément").
    4.  **Tester minutieusement :** Utilisez un compte client de test pour ajouter diverses combinaisons de produits au panier et vérifiez que la division fonctionne comme prévu pendant le processus de commande.

### 1.3 Écrans d'administration dédiés : Groupes d'expédition (Back Office > Livraison > Divisions d'expédition)

Cet écran fournit un aperçu de la façon dont les commandes ont été divisées par le module après avoir été passées. C'est un outil de reporting et de gestion.

-   **Nom de l'écran et emplacement du menu :** **Divisions d'expédition** (situé sous **Livraison** dans le menu de votre Back Office PrestaShop).
-   **Actions et paramètres disponibles :**
    -   **Tableau de liste des divisions :** Affiche une liste de toutes les commandes qui ont été divisées par le module.
    -   **Référence de commande :** Liens directs vers la commande PrestaShop originale.
    -   **Détails du groupe d'expédition :** Fournit des informations sur chaque groupe d'expédition individuel au sein d'une commande, y compris les produits qu'il contient, le transporteur choisi et son statut.
    -   **Afficher les détails de la division :** Vous permet d'explorer une division spécifique pour voir des informations plus granulaires.
-   **Effet des modifications :** Cet écran est principalement destiné à la visualisation et à l'audit. Vous ne modifiez pas directement la façon dont les futurs paniers sont divisés ici. Toute modification que vous apportez (par exemple, la mise à jour d'un transporteur pour une division spécifique) serait généralement effectuée dans la vue principale de la commande PrestaShop, et ce module refléterait ces modifications.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    -   **Surveiller les commandes divisées :** Vérifiez régulièrement cet écran pour comprendre comment vos règles fonctionnent en pratique.
    -   **Dépannage :** Si un client a une question sur son expédition, cet écran peut vous aider à voir rapidement comment sa commande a été traitée en différentes expéditions.
    -   **Intégration avec la gestion des commandes :** Bien que le module crée des commandes PrestaShop standard, cet écran offre une vue consolidée de la logique de division appliquée à chaque commande.

### 1.4 Écrans d'administration dédiés : Tableau de bord (Back Office > Livraison > Tableau de bord de division des expéditions)

Cet écran fournit un aperçu rapide et des statistiques liées à l'activité du module.

-   **Nom de l'écran et emplacement du menu :** **Tableau de bord de division des expéditions** (situé sous **Livraison** dans le menu de votre Back Office PrestaShop).
-   **Actions et paramètres disponibles :**
    -   **Bandeau KPI :** Indicateurs Clés de Performance (KPI) tels que le total des commandes divisées, la moyenne des expéditions par commande ou le revenu total d'expédition des commandes divisées.
    -   **Graphiques et diagrammes :** Représentations visuelles des tendances, telles que le nombre de commandes divisées au fil du temps, les règles de division les plus courantes utilisées ou les transporteurs populaires pour les expéditions divisées.
    -   **Divisions récentes :** Une liste rapide des commandes les plus récemment divisées.
-   **Effet des modifications :** Il s'agit d'un tableau de bord de reporting. Aucune modification directe du comportement du module n'est effectuée ici. Il vous aide à comprendre l'impact et l'utilisation du module.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    -   **Surveillance des performances :** Utilisez ce tableau de bord pour évaluer l'efficacité de vos règles de division et identifier les modèles ou les anomalies.
    -   **Planification stratégique :** Les données peuvent éclairer les décisions concernant les stratégies d'expédition, les partenariats avec les transporteurs ou les ajustements du catalogue de produits.

### 1.5 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
| | Mode Débogage | NON | Affiche des informations techniques (pour les développeurs uniquement). |
| | Afficher le résumé de la division sur la page de confirmation de commande | OUI | Montre aux clients comment leur commande a été divisée. |
| | Autoriser le client à choisir des points de retrait | OUI (si applicable) | Active la sélection des points de retrait pour les transporteurs pertinents. |
| **Règles de division des expéditions** | Ajouter/Modifier une règle (Conditions) | N/A | Définit *quand* une règle s'applique (par exemple, par produit, catégorie, valeur du panier). |
| | Ajouter/Modifier une règle (Actions) | N/A | Définit *ce que* la règle fait (par exemple, forcer l'expédition séparée, forcer la même expédition). |
| | Priorité de la règle | N/A | Détermine l'ordre dans lequel les règles sont traitées (plus élevé = premier). |
| | Activer/Désactiver la règle | N/A | Active ou désactive une règle de regroupement spécifique. |
| **Divisions d'expédition** | Afficher les commandes divisées | N/A | Fournit une liste et des détails de toutes les commandes traitées par le module. |
| **Tableau de bord de division des expéditions** | KPI, Graphiques, Divisions récentes | N/A | Offre un aperçu de l'activité et des performances du module. |

## 2. Dépannage du marchand et questions fréquemment posées (FAQ)

-   **Q : Mon panier ne se divise pas, ou il se divise incorrectement. Que dois-je faire ?**

    -   **R :** Tout d'abord, vérifiez si le module est activé dans sa configuration principale. Ensuite, allez dans **Livraison > Règles de division des expéditions** et examinez vos règles. Assurez-vous qu'elles sont actives et que leurs conditions correspondent correctement aux produits de votre panier de test. Portez une attention particulière à la priorité des règles – une règle plus générale pourrait en annuler une plus spécifique. Si le "Mode Débogage" est activé dans la configuration principale du module, recherchez tout message pendant le processus de commande. Enfin, videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**).
-   **Q : Pourquoi certains transporteurs n'apparaissent-ils pas pour un groupe d'expédition spécifique ?**

    -   **R :** Le module respecte les restrictions de transporteur standard de PrestaShop. Vérifiez les points suivants :
        1.  **Zones de transporteur :** Assurez-vous que le transporteur est activé pour la zone d'expédition du client.
        2.  **Plages de poids/prix du transporteur :** Vérifiez que le poids/prix total du *groupe d'expédition individuel* (pas de l'ensemble du panier) se situe dans les plages définies par le transporteur.
        3.  **Associations de transporteur :** Assurez-vous que le transporteur est associé aux produits de ce groupe d'expédition (si vous avez configuré des restrictions de transporteur spécifiques aux produits).
        4.  **Compatibilité du module :** Certains modules d'expédition tiers peuvent avoir leur propre logique qui entre en conflit ; vérifiez les incompatibilités connues ou contactez le support.
-   **Q : Comment ce module affecte-t-il mes frais d'expédition existants et mes règles de livraison gratuite ?**

    -   **R :** Le module agrège les frais d'expédition. Si un panier est divisé en deux expéditions, et que chaque expédition a un coût de 10 €, le client verra un coût total d'expédition de 20 €. Pour la livraison gratuite, vos règles de livraison gratuite existantes (par exemple, "livraison gratuite au-delà de X €") s'appliqueront à *chaque groupe d'expédition individuel* si le module le permet, ou au *total global du panier* selon la façon dont vos règles sont configurées et comment le module s'intègre. Vous devrez peut-être ajuster vos règles de livraison gratuite pour tenir compte des expéditions divisées.
-   **Q : Puis-je traduire les textes du module dans d'autres langues ?**

    -   **R :** Oui, comme la plupart des modules PrestaShop, vous pouvez traduire ses textes front-office et back-office. Allez dans **International > Traductions**, sélectionnez "Traductions des modules installés", choisissez votre thème, sélectionnez "Diviser le panier en plusieurs expéditions", puis choisissez la langue que vous souhaitez traduire.
-   **Q : Après l'installation, je vois une page blanche ou une erreur. Qu'est-ce qui ne va pas ?**

    -   **R :** Cela indique souvent une erreur PHP.
        1.  **Vérifiez les journaux d'erreurs PHP :** Votre panneau de contrôle d'hébergement web fournit généralement un accès aux journaux d'erreurs PHP. Recherchez les entrées récentes liées à PrestaShop.
        2.  **Activez le mode débogage de PrestaShop :** Allez dans `config/defines.inc.php` dans votre installation PrestaShop, trouvez `define('_PS_MODE_DEV_', false);` et changez `false` en `true`. Cela affichera l'erreur à l'écran.
        3.  **Compatibilité du module :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre version de PrestaShop (par exemple, PS 8.x, 1.7.x).
        4.  **Contactez le support :** Si vous ne parvenez pas à le résoudre, fournissez le message d'erreur au support MyPresta.eu.

## 3. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 3.1 Aperçu de l'architecture

Le module "Diviser le panier en plusieurs expéditions" (`multishipsplit`) est construit selon le modèle MVC (Model-View-Controller) de PrestaShop, avec une utilisation significative des hooks et des overrides pour s'intégrer profondément dans le processus de commande. Il introduit un moteur robuste basé sur des règles pour la division du panier, permettant des conditions et des actions complexes. La logique principale tourne autour du découpage de l'objet `Cart` en plusieurs entités `MultishipShipmentGroup`, chacune représentant un colis distinct avec sa propre sélection de transporteur. Il utilise `ObjectModel` pour gérer les règles et les données de division, et emploie une série de classes de service pour gérer la logique complexe d'évaluation des conditions, de construction des actions et de présentation du processus de commande. Des overrides sont utilisés pour modifier le comportement des classes `Cart` et `PaymentModule` afin de prendre en charge plusieurs expéditions.

### 3.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `multishipsplit/controllers/front/groups.php`
    -   **Nom de la classe :** `MultishipsplitGroupsModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Gère les requêtes AJAX liées aux groupes d'expédition pendant le processus de commande. Cela peut inclure la mise à jour des sélections de transporteur pour un groupe spécifique, le recalcul des frais d'expédition ou la récupération des options de point de retrait. Il traite les données `POST` et renvoie des réponses JSON à la page de commande.
-   `multishipsplit/controllers/front/index.php`
    -   **Nom de la classe :** `MultishipsplitIndexModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Un contrôleur de remplacement ou de point d'entrée. Il peut être utilisé pour des actions front-office générales liées au module ou des redirections, bien que sa fonction principale puisse être minimale si la plupart des interactions sont basées sur AJAX via `groups.php`.
-   `multishipsplit/controllers/front/pickup.php`
    -   **Nom de la classe :** `MultishipsplitPickupModuleFrontController` (étend `ModuleFrontController`)
    -   **Responsabilité :** Gère les interactions AJAX spécifiquement pour la sélection des points de retrait. Il gère probablement les requêtes pour afficher les points de retrait disponibles pour un transporteur et une adresse donnés, et pour enregistrer le point de retrait sélectionné dans le panier ou la session.

#### Contrôleurs d'administration Back-Office

-   `multishipsplit/controllers/admin/AdminMultishipRules.php`
    -   **Nom de la classe :** `AdminMultishipRulesController` (étend `ModuleAdminController`)
    -   **Nom de l'onglet :** "Règles de division des expéditions"
    -   **Entité gérée :** `MultishipGroupingRule` (mappe à la table `mss_grouping_rule`)
    -   **Responsabilité :** Fournit l'interface CRUD (Créer, Lire, Mettre à jour, Supprimer) pour la gestion des règles de regroupement des expéditions. Il gère l'affichage de la liste des règles, le formulaire d'ajout/modification des règles (y compris les constructeurs de conditions et d'actions), et l'enregistrement/suppression des données des règles.
-   `multishipsplit/controllers/admin/AdminMultishipSplits.php`
    -   **Nom de la classe :** `AdminMultishipSplitsController` (étend `ModuleAdminController`)
    -   **Nom de l'onglet :** "Divisions d'expédition"
    -   **Entité gérée :** `MultishipSplitGroup` (mappe à la table `mss_split_group`)
    -   **Responsabilité :** Affiche une liste de toutes les commandes qui ont été traitées et divisées par le module. Il fournit une vue en lecture seule des groupes divisés au sein de chaque commande, renvoyant à la commande PrestaShop originale.
-   `multishipsplit/controllers/admin/index.php`
    -   **Nom de la classe :** `MultishipsplitIndexModuleAdminController` (étend `ModuleAdminController`)
    -   **Nom de l'onglet :** "Tableau de bord de division des expéditions"
    -   **Entité gérée :** N/A (vue du tableau de bord)
    -   **Responsabilité :** Sert de contrôleur de tableau de bord, affichant les KPI, les graphiques et les commandes divisées récentes. Il agrège les données des tables du module pour fournir un aperçu de son activité.

### 3.3 Classes et modèles principaux (`classes/`)

-   `multishipsplit/classes/MultishipActionBuilder.php`
    -   **Responsabilité :** Une classe de service responsable de la construction et de l'interprétation des actions définies dans une `MultishipGroupingRule`. Elle traduit la configuration d'action de la règle en logique exécutable.
-   `multishipsplit/classes/MultishipCartSlicer.php`
    -   **Responsabilité :** La classe centrale pour la logique de division du panier. Elle prend un objet `Cart` et, en utilisant les `MultishipGroupingRule`s définies, divise les produits du panier en un tableau d'objets `MultishipShipmentGroup`.
-   `multishipsplit/classes/MultishipCheckoutPresenter.php`
    -   **Responsabilité :** Prépare les données pour la page de commande du front-office. Il prend les `MultishipShipmentGroup`s et les formate pour l'affichage, y compris les transporteurs disponibles, les coûts et les options de point de retrait, pour être rendus par les templates Smarty.
-   `multishipsplit/classes/MultishipCompatibility.php`
    -   **Responsabilité :** Gère les couches de compatibilité pour différentes versions de PrestaShop ou les conflits potentiels avec d'autres modules. Il garantit que le module fonctionne correctement dans divers environnements.
-   `multishipsplit/classes/MultishipConditionBuilder.php`
    -   **Responsabilité :** Similaire à `MultishipActionBuilder`, mais pour les conditions de règle. Il construit et interprète les conditions qui déterminent quand une `MultishipGroupingRule` doit être appliquée.
-   `multishipsplit/classes/MultishipConditionEvaluator.php`
    -   **Responsabilité :** Évalue un ensemble de conditions par rapport à un contexte donné (par exemple, un produit, un panier, un client) pour déterminer si une règle doit être déclenchée.
-   `multishipsplit/classes/MultishipConditionTree.php`
    -   **Responsabilité :** Gère la structure hiérarchique des conditions (par exemple, groupes ET/OU) au sein d'une règle, permettant des expressions logiques complexes.
-   `multishipsplit/classes/MultishipConfirmationPresenter.php`
    -   **Responsabilité :** Prépare les données pour afficher le résumé de la division sur la page de confirmation de commande.
-   `multishipsplit/classes/MultishipDashboardPresenter.php`
    -   **Responsabilité :** Collecte et formate les données pour le tableau de bord du Back Office, y compris les KPI et les données de graphique.
-   `multishipsplit/classes/MultishipGroupingEngine.php`
    -   **Responsabilité :** Orchestre l'ensemble du processus de regroupement basé sur des règles. Il récupère les règles actives, les applique séquentiellement (selon la priorité) au panier et gère la création des `MultishipShipmentGroup`s.
-   `multishipsplit/classes/MultishipGroupingRule.php`
    -   **Étend :** `ObjectModel`
    -   **Table de base de données :** `mss_grouping_rule`
    -   **Champs `$definition` :** Stocke la configuration de chaque règle de division, y compris son nom, sa priorité, son statut actif et ses conditions et actions sérialisées.
    -   **Méthodes publiques clés :** Méthodes pour enregistrer, charger et gérer les données des règles.
-   `multishipsplit/classes/MultishipOrderLink.php`
    -   **Étend :** `ObjectModel`
    -   **Table de base de données :** `mss_order_link`
    -   **Champs `$definition` :** Lie une `Order` PrestaShop à ses `MultishipSplitGroup`s correspondants, permettant au module de suivre comment une commande a été divisée.
    -   **Méthodes publiques clés :** Méthodes pour créer et récupérer ces liens.
-   `multishipsplit/classes/MultishipPaymentBridge.php`
    -   **Responsabilité :** Facilite le processus de paiement lorsqu'un panier est divisé. Il garantit que le montant total dû pour tous les groupes d'expédition est correctement transmis au module de paiement et que la confirmation de paiement met correctement à jour le statut de toutes les commandes associées.
-   `multishipsplit/classes/MultishipPayPlugRefundAdapter.php`
    -   **Responsabilité :** Fournit une intégration spécifique pour le remboursement des commandes divisées lors de l'utilisation du module de paiement PayPlug. Cela suggère que le module pourrait avoir des adaptateurs similaires pour d'autres passerelles de paiement.
-   `multishipsplit/classes/MultishipPickupFactory.php`
    -   **Responsabilité :** Une classe de fabrique pour créer des instances de `MultishipPickupAdapterInterface` en fonction du transporteur ou du module utilisé (par exemple, pour Mondial Relay, Colissimo).
-   `multishipsplit/classes/MultishipRefundLog.php`
    -   **Étend :** `ObjectModel`
    -   **Table de base de données :** `mss_refund_log`
    -   **Champs `$definition` :** Enregistre les actions de remboursement liées aux commandes divisées, particulièrement important lorsque des remboursements partiels ou des remboursements sur plusieurs commandes liées sont impliqués.
-   `multishipsplit/classes/MultishipRuleContext.php`
    -   **Responsabilité :** Encapsule le contexte (par exemple, panier actuel, client, produit en cours d'évaluation) pour l'évaluation des règles, facilitant le passage des données pertinentes aux évaluateurs de conditions.
-   `multishipsplit/classes/MultishipShipmentGroup.php`
    -   **Responsabilité :** Représente une seule expédition logique au sein d'un panier divisé. Il contient une collection de `MultishipShipmentProduct`s, le transporteur sélectionné et les coûts associés.
-   `multishipsplit/classes/MultishipShipmentProduct.php`
    -   **Responsabilité :** Représente un article de produit au sein d'un `MultishipShipmentGroup`, y compris sa quantité et ses attributs spécifiques pertinents pour cette expédition.
-   `multishipsplit/classes/MultishipShippingCostAggregator.php`
    -   **Responsabilité :** Calcule le coût total d'expédition en additionnant les coûts de tous les `MultishipShipmentGroup`s individuels.
-   `multishipsplit/classes/MultishipSplitGroup.php`
    -   **Étend :** `ObjectModel`
    -   **Table de base de données :** `mss_split_group`
    -   **Champs `$definition` :** Stocke les détails d'un groupe d'expédition spécifique qui a été créé dans le cadre d'une commande divisée. Ceci est utilisé pour le suivi et le reporting dans le Back Office.
-   `multishipsplit/classes/MultishipSplitOrchestrator.php`
    -   **Responsabilité :** L'orchestrateur de haut niveau pour l'ensemble du processus de division, du découpage initial du panier à la création de la commande et à la gestion du paiement.
-   `multishipsplit/classes/Pickup/MultishipColissimoPickupAdapter.php`
    -   **Implémente :** `MultishipPickupAdapterInterface`
    -   **Responsabilité :** Fournit une logique spécifique pour l'intégration avec les points de retrait Colissimo.
-   `multishipsplit/classes/Pickup/MultishipMondialRelayPickupAdapter.php`
    -   **Implémente :** `MultishipPickupAdapterInterface`
    -   **Responsabilité :** Fournit une logique spécifique pour l'intégration avec les points de retrait Mondial Relay.
-   `multishipsplit/classes/Pickup/MultishipPickupAdapterInterface.php`
    -   **Responsabilité :** Définit le contrat pour tous les adaptateurs d'intégration de points de retrait, garantissant une interface cohérente pour différents transporteurs.
-   `multishipsplit/override/classes/Cart.php`
    -   **Responsabilité :** Remplace les méthodes principales de `Cart` pour intercepter et modifier la façon dont les produits sont ajoutés, supprimés et comment les frais d'expédition sont calculés, permettant à la logique de division du module de prendre effet. Il s'agit d'un override critique.
-   `multishipsplit/override/classes/PaymentModule.php`
    -   **Responsabilité :** Remplace les méthodes principales de `PaymentModule` pour gérer le processus de paiement pour plusieurs commandes générées à partir d'un seul panier divisé. Il garantit qu'un seul paiement couvre toutes les sous-commandes et que leurs statuts sont correctement mis à jour.

### 3.4 Actifs JavaScript (`views/js/`)

-   `multishipsplit/lib/searchTool/views/js/autocomplete.js`
    -   **Portée :** Back-office.
    -   **Détails :** Fournit une fonctionnalité d'autocomplétion pour les champs de recherche, probablement utilisée dans le constructeur de règles pour sélectionner des produits, des catégories ou d'autres entités.
-   `multishipsplit/lib/searchTool/views/views/js/autocomplete.js`
    -   **Portée :** Back-office.
    -   **Détails :** Probablement un chemin dupliqué ou alternatif pour le script d'autocomplétion, éventuellement pour la compatibilité ou des contextes de vue spécifiques.
-   `multishipsplit/views/js/adminActionBuilder.js`
    -   **Portée :** Back-office (AdminMultishipRulesController).
    -   **Détails :** Gère l'interface dynamique pour la construction des actions de règle (par exemple, "Forcer l'expédition séparée"). Il gère l'ajout/suppression des types d'action et de leurs paramètres associés.
-   `multishipsplit/views/js/adminConditionBuilder.js`
    -   **Portée :** Back-office (AdminMultishipRulesController).
    -   **Détails :** Gère l'interface dynamique pour la construction des conditions de règle. Il permet aux administrateurs d'ajouter plusieurs conditions, de les regrouper avec une logique ET/OU et de sélectionner divers critères (produit, catégorie, etc.).
-   `multishipsplit/views/js/adminMultishipSearchTool.js`
    -   **Portée :** Back-office.
    -   **Détails :** Intègre l'outil de recherche d'autocomplétion dans les formulaires d'administration du module, en particulier pour la sélection de produits, catégories ou autres entités spécifiques lors de la définition des règles.
-   `multishipsplit/views/js/admin_dashboard.js`
    -   **Portée :** Back-office (AdminMultishipIndexController).
    -   **Détails :** Gère les éléments dynamiques et le chargement des données pour le tableau de bord, y compris potentiellement le rendu des graphiques (par exemple, en utilisant Chart.js) et les mises à jour des KPI.
-   `multishipsplit/views/js/admin_rules.js`
    -   **Portée :** Back-office (AdminMultishipRulesController).
    -   **Détails :** JavaScript général pour la page de gestion des règles, y compris la réorganisation des règles par glisser-déposer, les bascules d'activation/désactivation et la gestion de la soumission des formulaires.
-   `multishipsplit/views/js/checkout.js`
    -   **Portée :** Front-office (page de commande).
    -   **Détails :** Il s'agit d'un script critique pour l'expérience front-office. Il lie les écouteurs d'événements aux changements de sélection de transporteur pour chaque groupe d'expédition, envoie des requêtes AJAX à `groups.php` ou `pickup.php` pour mettre à jour les frais d'expédition ou récupérer les points de retrait, et met à jour dynamiquement le résumé total de la commande sur la page de commande. Il utilise probablement `prestashop.on` pour les événements personnalisés.

### 3.5 Feuilles de style CSS (`views/css/`)

-   `multishipsplit/lib/searchTool/views/css/autocomplete.css`
    -   **Portée :** Back-office.
    -   **Détails :** Styles pour les listes déroulantes d'autocomplétion et les champs de saisie de recherche utilisés dans les formulaires d'administration.
-   `multishipsplit/lib/searchTool/views/views/css/autocomplete.css`
    -   **Portée :** Back-office.
    -   **Détails :** Probablement un chemin dupliqué ou alternatif pour les styles d'autocomplétion.
-   `multishipsplit/views/css/admin_condition_builder.css`
    -   **Portée :** Back-office (AdminMultishipRulesController).
    -   **Détails :** Style de l'interface dynamique pour la construction des conditions dans le formulaire de création/modification de règle, assurant une mise en page claire et organisée.
-   `multishipsplit/views/css/admin_dashboard.css`
    -   **Portée :** Back-office (AdminMultishipIndexController).
    -   **Détails :** Styles pour la mise en page du tableau de bord, les KPI, les graphiques et le tableau des divisions récentes.
-   `multishipsplit/views/css/admin_order.css`
    -   **Portée :** Back-office (page de vue de commande).
    -   **Détails :** Styles pour le widget ou les informations personnalisées affichées dans la vue de commande standard de PrestaShop, montrant comment la commande a été divisée.
-   `multishipsplit/views/css/admin_rules.css`
    -   **Portée :** Back-office (AdminMultishipRulesController).
    -   **Détails :** Styles généraux pour le tableau de liste des règles, les actions de règle (activer/désactiver) et la mise en page globale de la page de gestion des règles.
-   `multishipsplit/views/css/checkout.css`
    -   **Portée :** Front-office (page de commande).
    -   **Détails :** Style de la présentation des groupes d'expédition divisés sur la page de commande, y compris la façon dont les transporteurs sont affichés pour chaque groupe, le résumé des coûts et potentiellement les interfaces de sélection des points de retrait. Les développeurs peuvent remplacer ces classes dans le `custom.css` de leur thème ou en modifiant les templates du module.

### 3.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

-   `multishipsplit/views/templates/hook/checkout_groups.tpl`
    -   **Hook :** Probablement `displayCarrierList` ou un hook personnalisé injecté dans l'étape de livraison du processus de commande.
    -   **Sorties :** Le bloc visuel principal sur la page de commande qui affiche les produits regroupés et permet aux clients de sélectionner un transporteur pour chaque groupe d'expédition individuel. C'est là que se déroule l'interaction principale du front-office.
-   `multishipsplit/views/templates/hook/order_confirmation_split.tpl`
    -   **Hook :** `displayOrderConfirmation` ou un hook similaire sur la page de confirmation de commande.
    -   **Sorties :** Le résumé de la façon dont la commande a été divisée, montrant quels articles étaient dans chaque expédition et le transporteur choisi, tel que configuré par le paramètre "Afficher le résumé de la division sur la page de confirmation de commande".
-   `multishipsplit/views/templates/hook/payment_top.tpl`
    -   **Hook :** `displayPaymentTop`
    -   **Sorties :** Affiche potentiellement un avertissement ou un message d'information au client concernant la commande divisée avant qu'il ne procède au paiement, s'assurant qu'il comprend que le coût total inclut plusieurs frais d'expédition.

#### Templates d'administration (`views/templates/admin/`)

-   `multishipsplit/lib/searchTool/views/scripts.tpl`
    -   **Sorties :** Bloc de script Smarty pour l'outil de recherche, incluant probablement des fichiers JavaScript et CSS.
-   `multishipsplit/lib/searchTool/views/views/scripts.tpl`
    -   **Sorties :** Chemin dupliqué ou alternatif pour les scripts de l'outil de recherche.
-   `multishipsplit/views/templates/admin/actionBuilder.tpl`
    -   **Sorties :** La structure HTML pour l'interface dynamique du constructeur d'actions dans le formulaire de création/modification de règle.
-   `multishipsplit/views/templates/admin/dashboard_chart.tpl`
    -   **Sorties :** Template pour le rendu d'un graphique spécifique sur le tableau de bord, utilisant probablement une bibliothèque de graphiques JavaScript.
-   `multishipsplit/views/templates/admin/dashboard_kpi_strip.tpl`
    -   **Sorties :** Template pour la bande d'indicateurs clés de performance (KPI) en haut du tableau de bord.
-   `multishipsplit/views/templates/admin/dashboard_recent_splits.tpl`
    -   **Sorties :** Template pour l'affichage d'une liste de commandes récemment divisées sur le tableau de bord.
-   `multishipsplit/views/templates/admin/dashboard_stats.tpl`
    -   **Sorties :** Bloc de statistiques générales sur le tableau de bord.
-   `multishipsplit/views/templates/admin/menu.tpl`
    -   **Sorties :** Définit les éléments de menu personnalisés du module dans la navigation du Back Office de PrestaShop (par exemple, sous "Livraison").
-   `multishipsplit/views/templates/admin/order_split_widget.tpl`
    -   **Sorties :** Un widget ou un bloc personnalisé affiché dans la page de détails de commande standard de PrestaShop dans le Back Office, fournissant un résumé de la façon dont cette commande spécifique a été divisée.
-   `multishipsplit/views/templates/admin/policyConditionBuilder.tpl`
    -   **Sorties :** La structure HTML pour l'interface dynamique du constructeur de conditions dans le formulaire de création/modification de règle.
-   `multishipsplit/views/templates/admin/split_view.tpl`
    -   **Sorties :** Une vue détaillée pour une commande divisée spécifique, potentiellement accessible depuis la liste "Divisions d'expédition".

### 3.7 Schéma de base de données et carte des hooks

#### Tables de base de données

-   `ps_mss_grouping_rule` : Stocke les définitions de toutes les règles de regroupement d'expédition créées par l'administrateur.
    -   `id_mss_grouping_rule` (PK)
    -   `name` (VARCHAR)
    -   `priority` (INT)
    -   `active` (TINYINT)
    -   `conditions` (TEXT - tableau/JSON sérialisé des conditions)
    -   `actions` (TEXT - tableau/JSON sérialisé des actions)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_mss_split_group` : Stocke les détails de chaque groupe d'expédition individuel créé pour une commande divisée.
    -   `id_mss_split_group` (PK)
    -   `id_order` (FK vers `ps_orders`)
    -   `id_cart` (FK vers `ps_cart`)
    -   `id_carrier` (FK vers `ps_carrier`)
    -   `shipping_cost_tax_excl` (DECIMAL)
    -   `shipping_cost_tax_incl` (DECIMAL)
    -   `products` (TEXT - tableau sérialisé des produits de ce groupe)
    -   `pickup_point_data` (TEXT - données sérialisées pour le point de retrait, si sélectionné)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_mss_order_link` : Lie un seul `id_order` PrestaShop (la commande "parente") à plusieurs `id_order`s (les commandes "enfants" créées pour chaque expédition divisée).
    -   `id_mss_order_link` (PK)
    -   `id_parent_order` (FK vers `ps_orders`)
    -   `id_child_order` (FK vers `ps_orders`)
    -   `id_mss_split_group` (FK vers `ps_mss_split_group`)
    -   `date_add` (DATETIME)
-   `ps_mss_refund_log` : Enregistre les actions de remboursement liées aux commandes divisées.
    -   `id_mss_refund_log` (PK)
    -   `id_order` (FK vers `ps_orders`)
    -   `id_order_slip` (FK vers `ps_order_slip`)
    -   `amount` (DECIMAL)
    -   `reason` (TEXT)
    -   `date_add` (DATETIME)
-   `ps_configuration` : Les paramètres du module sont stockés ici avec des clés comme `MULTISHIPSPLIT_ENABLED`, `MULTISHIPSPLIT_DEBUG_MODE`, etc.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de toutes les pages du front-office. | Injection d'actifs CSS et JS pour la fonctionnalité du front-office (par exemple, `checkout.js`, `checkout.css`). |
| `displayBackOfficeHeader` | Dans la section `<head>` de toutes les pages du back-office. | Injection d'actifs CSS et JS pour les contrôleurs d'administration (par exemple, `admin_rules.js`, `admin_condition_builder.css`). |
| `displayAdminProductsExtra` | Sur la page d'édition de produit dans le Back Office. | Ajoute potentiellement un onglet ou une section pour configurer des règles de division spécifiques au produit ou des overrides. |
| `actionCartSave` | Après l'enregistrement ou la mise à jour d'un panier. | Intercepte les modifications du panier pour déclencher la logique de division et recalculer les groupes d'expédition. |
| `actionValidateOrder` | Après la validation réussie d'une commande. | Traite le panier divisé en plusieurs commandes PrestaShop, les lie et stocke les données du groupe divisé. |
| `actionOrderSlipAdd` | Lorsqu'un avoir (remboursement) est ajouté. | Gère la logique de remboursement pour les commandes divisées, enregistrant potentiellement les remboursements partiels sur les commandes liées. |
| `displayCarrierList` | À l'étape de livraison du processus de commande, où les options de transporteur sont affichées. | Remplace ou augmente la liste standard des transporteurs avec l'interface de sélection des expéditions groupées (`checkout_groups.tpl`). |
| `displayOrderConfirmation` | Sur la page finale de confirmation de commande. | Affiche le résumé de la commande divisée au client (`order_confirmation_split.tpl`). |
| `displayPaymentTop` | Avant la sélection du mode de paiement sur la page de commande. | Peut afficher des messages ou des résumés importants liés aux frais d'expédition divisés (`payment_top.tpl`). |
| `displayAdminOrder` | Sur la page de détails de commande dans le Back Office. | Injecte le `order_split_widget.tpl` pour montrer comment la commande spécifique a été divisée. |
| `actionObjectCartUpdateAfter` | Après la mise à jour d'un objet Cart. | Similaire à `actionCartSave`, garantit que la logique de division est réévaluée. |
| `actionObjectOrderAddAfter` | Après l'ajout d'un nouvel objet Order. | Utilisé pour finaliser la liaison des commandes parentes/enfants et des données du groupe divisé. |
| `actionObjectOrderUpdateAfter` | Après la mise à jour d'un objet Order. | Met potentiellement à jour les statuts des groupes divisés ou les données associées si une commande est modifiée. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende son contenu. | Garantit que les JS/CSS nécessaires sont chargés pour les pages du front-office. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende son contenu. | Garantit que les JS/CSS nécessaires sont chargés pour les pages du back-office. |
| `displayAdminStatsModules` | Sur la page Modules > Statistiques. | Ajoute potentiellement des statistiques spécifiques au module au tableau de bord de PrestaShop. |
| `displayDashboardTop` | En haut du tableau de bord de PrestaShop. | Peut afficher un résumé rapide ou une alerte du module. |
| `displayDashboardZoneOne` | Dans la première zone du tableau de bord de PrestaShop. | Peut afficher un widget spécifique au module sur le tableau de bord. |
| `displayDashboardZoneTwo` | Dans la deuxième zone du tableau de bord de PrestaShop. | Peut afficher un widget spécifique au module sur le tableau de bord. |

## 4. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur MyPresta.eu.

-   **Mises à jour du module :** Connectez-vous à [MyPresta.eu Order History & Downloads](https://mypresta.eu/my-account/orders/) pour télécharger la version la plus récente du module "Diviser le panier en plusieurs expéditions".
-   **Support technique :** Si vous rencontrez des problèmes ou avez des questions qui ne sont pas couvertes dans ce guide, veuillez ouvrir un ticket de support via votre compte client MyPresta.eu. Notre équipe est prête à vous aider.

## 5. ## Galerie

![Tableau de bord sur la page de configuration du module qui affiche les statistiques du module](https://mypresta.eu/docs/images/docs/02-shipping-multi-carrier-order-split_1791740311.webp)
"""
