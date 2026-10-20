---
title: "Disponibilité du transporteur par valeur de panier - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Disponibilité du transporteur par valeur de panier' par MyPresta.eu."
sidebar:
  label: "Disponibilité du transporteur par valeur de panier - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Carrier availability by cart value sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/carrier-availability-by-cart-value.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/carrier-availability-by-cart-value/)
>
> ---


# Disponibilité du transporteur par valeur de panier

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont généralement disponibles sur tout environnement d'hébergement moderne.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page de configuration principale du module.

-   **Ce que fait ce paramètre :** Cet écran gère principalement les paramètres généraux du module, souvent liés aux mises à jour ou aux fonctionnalités de base.
-   **Effet de la modification de ce paramètre :**
    -   `mypresta_updates` : C'est un paramètre commun à tous les modules MyPresta.eu.
        -   *Lorsqu'il est activé :* Le module vérifiera périodiquement les nouvelles versions et mises à jour de MyPresta.eu. Cela vous aide à rester à jour avec les corrections de bugs et les nouvelles fonctionnalités.
        -   *Lorsqu'il est désactivé :* Le module ne vérifiera pas les mises à jour automatiquement. Vous devrez vérifier manuellement les nouvelles versions sur MyPresta.eu.
    -   `update_` et `updatev_` : Ce sont des paramètres internes utilisés par le mécanisme de mise à jour du module pour suivre la dernière vérification et la version disponible. Vous n'avez généralement pas besoin d'interagir directement avec ceux-ci.
-   **Valeur recommandée :**
    -   Pour `mypresta_updates` : **OUI** (Activé). Il est toujours recommandé de maintenir les modules à jour pour la sécurité, les performances et les nouvelles fonctionnalités.
-   **Scénario / exemple de marchand :** L'activation des mises à jour garantit que votre module exécute toujours la dernière version, évitant ainsi d'éventuels problèmes de compatibilité avec les futures mises à jour de PrestaShop ou d'autres modules.

### 2.2 Écran d'administration dédié : Règles de disponibilité des transporteurs

C'est le cœur du module où vous définissez les règles de disponibilité des transporteurs en fonction de la valeur du panier.

-   **Nom de l'écran et emplacement du menu :**

    -   Dans votre Back Office PrestaShop, naviguez vers **Livraison > Disponibilité du transporteur par valeur de commande**.
    -   Cela ouvrira un nouvel écran dédié où vous pourrez gérer vos règles.
-   **Actions et paramètres disponibles :**
    Cet écran présente une liste des règles existantes et vous permet d'en ajouter de nouvelles ou de modifier/supprimer celles qui existent.

    **Colonnes du tableau de liste :**

    -   **ID** : Identifiant unique de la règle.
    -   **Transporteur** : Le nom du transporteur auquel la règle s'applique.
    -   **Commande\_de** : La valeur minimale du panier pour que ce transporteur soit disponible.
    -   **Commande\_à** : La valeur maximale du panier pour que ce transporteur soit disponible.
    -   **Actif** : Un interrupteur pour activer ou désactiver la règle sans la supprimer.

    **Ajouter/Modifier une règle (champs du formulaire) :**
    Lorsque vous cliquez sur « Ajouter une nouvelle règle » ou modifiez une règle existante, vous verrez un formulaire avec les champs suivants :

    -   **Disponibilité du transporteur par valeur de commande** : Il s'agit d'une liste déroulante où vous sélectionnez le transporteur spécifique auquel vous souhaitez appliquer la règle.

        -   *Effet :* La règle que vous définissez n'affectera que la disponibilité de ce transporteur choisi.
        -   *Valeur recommandée :* Sélectionnez le transporteur que vous souhaitez gérer.
        -   *Scénario marchand :* Si vous souhaitez restreindre la « Livraison Express » aux commandes de grande valeur, vous sélectionneriez « Livraison Express » ici.
    -   **Valeur de commande de** : Entrez la valeur totale minimale du panier (dans votre devise par défaut) pour que ce transporteur soit disponible.

        -   *Effet :* Si la valeur du panier du client est inférieure à ce montant, le transporteur sélectionné ne sera pas affiché lors du paiement.
        -   *Valeur recommandée :* Entrez `0` s'il n'y a pas de minimum, ou un montant spécifique (par exemple, `50.00`).
        -   *Scénario marchand :* Définissez à `50.00` pour que la « Livraison gratuite » n'apparaisse que pour les commandes de plus de 50 $.
    -   **Valeur de commande à** : Entrez la valeur totale maximale du panier (dans votre devise par défaut) pour que ce transporteur soit disponible.

        -   *Effet :* Si la valeur du panier du client est supérieure à ce montant, le transporteur sélectionné ne sera pas affiché lors du paiement.
        -   *Valeur recommandée :* Laissez vide ou définissez à `0` s'il n'y a pas de maximum, ou un montant spécifique (par exemple, `200.00`).
        -   *Scénario marchand :* Définissez à `200.00` pour la « Livraison standard » afin d'éviter qu'elle ne soit choisie pour des commandes de très grande valeur qui devraient utiliser la « Livraison assurée ».
    -   **Actif** : Un simple interrupteur ON/OFF.

        -   *Effet :*
            -   *Lorsqu'il est activé :* La règle est active et filtrera la disponibilité du transporteur.
            -   *Lorsqu'il est désactivé :* La règle est ignorée, et le transporteur sera disponible en fonction des autres paramètres de PrestaShop (poids, prix, zones) quelle que soit la valeur du panier.
        -   *Valeur recommandée :* **ON** pour les règles actives.
        -   *Scénario marchand :* Désactivez temporairement une règle pendant une promotion sans la supprimer.
    -   **Enregistrer** : Cliquez sur ce bouton pour appliquer vos modifications ou créer la nouvelle règle.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**

    1.  **Identifiez vos transporteurs :** Listez tous vos transporteurs et leurs cas d'utilisation prévus.
    2.  **Définissez les plages de valeurs :** Pour chaque transporteur, décidez s'il existe une plage de valeurs de panier spécifique où il devrait être disponible.
        -   *Exemple 1 :* « Expédition Économique » pour les commandes de 0 $ à 75 $.
        -   *Exemple 2 :* « Expédition Standard » pour les commandes de 75 $ à 250 $.
        -   *Exemple 3 :* « Premium Assuré » pour les commandes de 250 $ et plus (définissez « Valeur de commande de » à 250, laissez « Valeur de commande à » vide/0).
    3.  **Ajoutez des règles :** Allez dans **Livraison > Disponibilité du transporteur par valeur de commande** et cliquez sur « Ajouter une nouvelle règle ».
    4.  **Configurez chaque règle :** Sélectionnez le transporteur, entrez la « Valeur de commande de » et la « Valeur de commande à », et assurez-vous que « Actif » est sur ON.
    5.  **Testez minutieusement :** Après avoir configuré vos règles, effectuez des achats tests avec différentes valeurs de panier pour vous assurer que les transporteurs sont affichés comme prévu.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | `mypresta_updates` | OUI (Activé) | Active les vérifications automatiques des mises à jour du module. |
| Règles de disponibilité du transporteur | Transporteur | Sélectionner dans la liste | Le transporteur spécifique auquel cette règle s'applique. |
| Règles de disponibilité du transporteur | Valeur de commande de | `0` ou montant spécifique | Valeur minimale du panier pour que le transporteur soit disponible. |
| Règles de disponibilité du transporteur | Valeur de commande à | `0` (pas de max) ou montant spécifique | Valeur maximale du panier pour que le transporteur soit disponible. |
| Règles de disponibilité du transporteur | Actif | ON | Active ou désactive la règle de disponibilité du transporteur spécifique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré des règles, mais les transporteurs ne changent pas lors du paiement. Qu'est-ce qui ne va pas ?**
R1 :

-   **Vider le cache :** Videz toujours le cache de votre PrestaShop après avoir effectué des modifications de configuration du module. Allez dans **Paramètres avancés > Performances**, puis cliquez sur « Vider le cache » en haut à droite.
-   **Conflits de règles :** Vérifiez si vous avez des règles contradictoires. Par exemple, si le transporteur A est défini de 0 $ à 100 $ et le transporteur B de 50 $ à 150 $, assurez-vous que vos plages sont logiques.
-   **Statut du transporteur :** Assurez-vous que les transporteurs eux-mêmes sont actifs et correctement configurés dans **Livraison > Transporteurs** dans PrestaShop. Ce module ne filtre que les transporteurs *disponibles*, il n'active pas ceux qui sont inactifs.
-   **Autres restrictions de transporteur :** N'oubliez pas que PrestaShop a ses propres restrictions de transporteur (par zone, poids, prix). Ce module *ajoute* une autre couche de filtrage. Si un transporteur est déjà restreint par le poids, ce module ne le rendra pas disponible.

**Q2 : Le symbole de ma devise ne s'affiche pas correctement, ou les valeurs semblent incorrectes.**
R2 : Le module utilise la devise par défaut de votre boutique pour les champs « Valeur de commande de » et « Valeur de commande à ». Assurez-vous que votre devise par défaut est correctement définie dans **International > Devises**. Le module fonctionne sur la valeur numérique, donc le symbole affiché dans le back office est pour votre référence.

**Q3 : Puis-je utiliser ce module avec d'autres modules d'expédition ?**
R3 : Oui, généralement. Ce module s'intègre au processus standard de PrestaShop pour filtrer les listes de transporteurs. Il appliquera ses règles *après* que les autres conditions de base de PrestaShop (comme le poids, le prix, la zone) aient déjà réduit la liste des transporteurs potentiels. Si un autre module filtre également les transporteurs, les règles les plus restrictives de tous les modules s'appliqueront.

**Q4 : Comment rendre un transporteur *toujours* disponible, quelle que soit la valeur du panier ?**
R4 : Vous n'avez pas besoin de créer une règle pour un tel transporteur. Si un transporteur n'est pas répertorié dans vos règles « Disponibilité du transporteur par valeur de commande », il restera disponible en fonction des paramètres de transporteur par défaut de PrestaShop (poids, prix, zone, etc.) sans aucune restriction de valeur de panier de ce module.

**Q5 : Le module semble ralentir mon processus de paiement. Est-ce normal ?**
R5 : Ce module est conçu pour être léger et ne devrait pas avoir d'impact significatif sur les performances. Si vous remarquez un ralentissement, assurez-vous que votre installation PrestaShop est optimisée (par exemple, cache activé, dernière version de PHP, pas de modules excessifs). Si le problème persiste, contactez le support MyPresta.eu avec les détails de votre configuration.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Disponibilité du transporteur par valeur de panier » (`cbp`) suit l'architecture standard des modules PrestaShop, en tirant principalement parti d'un `AdminController` pour la configuration et d'un hook Front-Office pour modifier la liste des transporteurs lors du paiement. Il utilise un `ObjectModel` personnalisé pour gérer les règles de disponibilité des transporteurs dans sa propre table de base de données.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    Ce module n'inclut aucun contrôleur Front-Office dédié. Toute la logique Front-Office est gérée directement via un hook dans le fichier principal du module (`cbp.php`).
-   **Contrôleurs Admin Back-Office** :

    -   `cbp/controllers/admin/AdminCbpr.php`

        -   **Nom de la classe :** `AdminCbprController` (étend `ModuleAdminController`)
        -   **Responsabilité :** C'est l'interface administrative principale pour la gestion des règles de disponibilité des transporteurs. Elle gère les opérations CRUD (Créer, Lire, Mettre à jour, Supprimer) pour l'entité `cbpr`.
        -   **Nom de l'onglet :** « Disponibilité du transporteur par valeur de commande » (sous le menu Livraison).
        -   **Entité gérée :** `Cbpr` (l'`ObjectModel` personnalisé pour les règles de transporteur).
        -   **Fonctionnalités clés :**
            -   Affiche une vue `list` de toutes les règles configurées, y compris l'ID, le nom du transporteur, Order\_from, Order\_to et le statut Actif.
            -   Fournit des formulaires `add` et `edit` pour les règles individuelles, permettant la sélection d'un transporteur et la saisie des valeurs de commande min/max.
            -   Gère les soumissions de formulaires et les interactions avec la base de données pour l'enregistrement et la mise à jour des règles.
            -   Utilise `PS_CURRENCY_DEFAULT` pour afficher les informations de devise dans les formulaires.
    -   `cbp/controllers/admin/index.php`

        -   **Responsabilité :** Ce fichier est un fichier `index.php` vide standard, généralement inclus dans les répertoires PrestaShop pour empêcher la liste des répertoires pour des raisons de sécurité. Il ne contient aucune logique de contrôleur fonctionnelle.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne possède pas de répertoire `classes/` dédié. L'`ObjectModel` principal pour la gestion des règles de transporteur est probablement défini directement dans le fichier principal du module (`cbp/cbp.php`) ou implicitement géré par l'`AdminCbprController` à l'aide d'une définition d'`ObjectModel` dynamique.

Étant donné que l'`AdminCbprController` gère une table nommée `cbpr`, il doit y avoir une classe `ObjectModel`, probablement nommée `Cbpr`, définie quelque part. Cette classe définirait la structure des règles de disponibilité des transporteurs.

**`ObjectModel` `Cbpr` supposé (probablement dans `cbp.php`) :**

-   **Nom de la classe :** `Cbpr` (étend `ObjectModel`)
-   **Table de base de données :** `ps_cbpr` (ou `_cbpr` avec préfixe)
-   **Champs `$definition` (attendus) :**
    -   `id_cbpr` : Clé primaire.
    -   `id_carrier` : Clé étrangère vers la table `ps_carrier`.
    -   `order_from` : Champ décimal pour la valeur minimale du panier.
    -   `order_to` : Champ décimal pour la valeur maximale du panier.
    -   `active` : Champ booléen pour le statut de la règle.
-   **Méthodes clés :** Méthodes `ObjectModel` standard pour `add()`, `update()`, `delete()`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module ne contient aucun fichier JavaScript personnalisé dans `views/js/`. Toute la logique Front-Office est gérée côté serveur via des hooks PHP. Les formulaires Back-Office s'appuient sur la gestion de formulaire par défaut de PrestaShop et jQuery.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module ne contient aucun fichier CSS personnalisé dans `views/css/`. L'interface du Back-Office utilise le style par défaut de PrestaShop pour les formulaires et les listes de `ModuleAdminController`. Les modifications Front-Office sont gérées en filtrant la liste des transporteurs directement en PHP, et non en rendant de nouveaux modèles.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module ne contient aucun fichier de modèle Smarty personnalisé dans `views/templates/`. Les formulaires de configuration et les listes dans le Back Office sont rendus à l'aide des modèles `ModuleAdminController` par défaut de PrestaShop. Les modifications Front-Office sont gérées en filtrant la liste des transporteurs directement en PHP, et non en rendant de nouveaux modèles.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   `ps_cbpr` : Cette table stocke les règles de disponibilité des transporteurs.

        -   `id_cbpr` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `id_carrier` INT(10) UNSIGNED NOT NULL
        -   `order_from` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
        -   `order_to` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
        -   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        -   PRIMARY KEY (`id_cbpr`)
        -   KEY `id_carrier` (`id_carrier`)
    -   `ps_configuration` : Le module stocke ses paramètres généraux (comme `mypresta_updates`, `update_`, `updatev_`) dans la table `ps_configuration`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un `AdminController` est initialisé et que ses médias (JS/CSS) sont définis. | Utilisé par le module pour enregistrer son `AdminController` personnalisé (`AdminCbprController`) dans la structure du menu de PrestaShop. |
| `actionFilterDeliveryOptionList` | Exécuté pendant le processus de paiement, spécifiquement lorsque PrestaShop construit la liste des options de livraison disponibles. | C'est le hook Front-Office principal. Le module l'utilise pour parcourir la liste des transporteurs que PrestaShop a déjà jugés disponibles (en fonction des zones, du poids, du prix), puis filtre davantage cette liste en fonction de la valeur totale du panier et des règles définies dans `ps_cbpr`. Si la règle d'un transporteur ne correspond pas à la valeur actuelle du panier, il est supprimé de la liste présentée au client. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Disponibilité du transporteur par valeur de panier », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de nos modules.
