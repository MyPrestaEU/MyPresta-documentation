---
title: "Attribuer des clients à un groupe par produits achetés - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Attribuer des clients à un groupe par produits achetés' par MyPresta.eu."
sidebar:
  label: "Attribuer des clients à un groupe par produits achetés - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Assign customers to group by purchased products sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/assign-customers-to-group-by-purchased-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/assign-customers-to-group-by-purchased-products/)
>
> ---


# Attribuer des clients à un groupe par produits achetés

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous gérez les paramètres essentiels du module.

-   **Ce que fait ce paramètre :** Cette section contient généralement les paramètres généraux du module, tels que l'activation/désactivation de sa fonctionnalité principale.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Le module surveillera activement les achats des clients et appliquera vos règles d'attribution de groupe définies.
    -   *Lorsqu'il est désactivé :* Le module cessera de traiter les nouvelles commandes pour les attributions de groupe. Les attributions existantes resteront, mais aucune nouvelle ne sera effectuée automatiquement.
-   **Valeur recommandée :** **OUI** (Activé) pour permettre au module de fonctionner.
-   **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois, vous voudrez l'activer immédiatement après la configuration. Si vous devez arrêter temporairement les attributions automatiques (par exemple, lors d'une migration majeure de boutique), vous pouvez le désactiver ici.

### 2.2 Écran d'administration dédié : Associations de groupes de produits

C'est la zone de gestion principale où vous définissez les règles d'attribution des clients aux groupes en fonction de leurs achats.

**Nom de l'écran et emplacement du menu :**
Vous pouvez accéder à cet écran en naviguant vers **Modules > Gestionnaire de modules**, en trouvant « Attribuer des clients à un groupe par produits achetés », et en cliquant sur « Configurer ». Dans la configuration du module, vous trouverez une section ou un onglet dédié aux « Associations de groupes de produits » ou similaire.

**Actions et paramètres disponibles :**
Sur cet écran, vous trouverez généralement une liste de règles d'attribution existantes. Vous aurez des options pour :

-   **Ajouter une nouvelle règle :** Créer une nouvelle condition pour l'attribution de groupe.
-   **Modifier la règle :** Modifier une règle existante.
-   **Supprimer la règle :** Supprimer une règle.

Lors de l'ajout ou de la modification d'une règle, vous configurerez les éléments suivants :

1.  **Sélectionner le groupe de clients :**

    -   **Ce que fait ce paramètre :** C'est le groupe cible auquel les clients seront attribués s'ils remplissent les conditions de la règle.
    -   **Effet de la modification de ce paramètre :** Lorsqu'un achat client déclenche cette règle, il sera déplacé vers (ou ajouté à) le groupe de clients sélectionné.
    -   **Valeur recommandée :** Choisissez le groupe de clients spécifique que vous souhaitez segmenter (par exemple, « Clients Grossistes », « Acheteurs VIP », « Passionnés d'Électronique »).
    -   **Scénario / exemple de marchand :** Vous souhaitez créer une règle pour attribuer des clients à votre groupe « Acheteurs VIP ».
2.  **Sélectionner les produits / catégories :**

    -   **Ce que fait ce paramètre :** Ici, vous définissez *quels* produits ou catégories de produits, une fois achetés, déclencheront l'attribution du groupe. Vous pouvez généralement sélectionner plusieurs produits ou catégories. Le module inclut probablement un outil de recherche pour trouver facilement des produits.
    -   **Effet de la modification de ce paramètre :** Seuls les achats contenant les produits spécifiés ou provenant des catégories spécifiées activeront cette règle.
    -   **Valeur recommandée :** Soyez précis. Utilisez l'outil de recherche pour sélectionner tous les produits ou catégories pertinents.
    -   **Scénario / exemple de marchand :** Pour le groupe « Acheteurs VIP », vous pourriez sélectionner des produits de grande valeur comme « Montre de Luxe X » et « Collier de Diamants Y ». Pour les « Passionnés d'Électronique », vous pourriez sélectionner toute la catégorie « Électronique ».
3.  **Quantité minimale (facultatif) :**

    -   **Ce que fait ce paramètre :** Si spécifié, le client doit acheter au moins cette quantité des produits/catégories sélectionnés dans une seule commande pour être attribué au groupe.
    -   **Effet de la modification de ce paramètre :** Si un client achète moins que la quantité minimale, la règle ne s'appliquera pas, même s'il a acheté les produits spécifiés.
    -   **Valeur recommandée :** Laissez vide pour toute quantité, ou définissez une valeur comme « 1 » pour au moins un article, ou « 5 » pour les acheteurs en gros.
    -   **Scénario / exemple de marchand :** Pour être un « Client Grossiste », il doit acheter au moins 10 unités de tout produit de la catégorie « Articles en vrac ».
4.  **Statut de commande pour déclencher l'attribution :**

    -   **Ce que fait ce paramètre :** Cela détermine à quel statut de commande l'attribution du groupe de clients doit avoir lieu. Par exemple, vous ne voudrez peut-être attribuer des groupes qu'une fois qu'une commande est « Paiement accepté » ou « Livré ».
    -   **Effet de la modification de ce paramètre :** Le module ne traitera l'attribution du groupe que lorsqu'une commande atteint le statut sélectionné. Si une commande n'atteint jamais ce statut (par exemple, « Annulée »), l'attribution n'aura pas lieu.
    -   **Valeur recommandée :** « Paiement accepté » ou « Livré » sont généralement des choix sûrs pour s'assurer que l'achat est confirmé.
    -   **Scénario / exemple de marchand :** Vous voulez vous assurer que les clients ont réellement payé avant d'être ajoutés à un groupe spécial, vous sélectionnez donc « Paiement accepté ».
5.  **Attribuer au groupe (Ajouter ou Remplacer) :**

    -   **Ce que fait ce paramètre :** Cette option cruciale détermine la manière dont l'appartenance du client au groupe est gérée.
        -   **Ajouter au groupe :** Le client sera ajouté au groupe sélectionné *en plus* de tous les groupes auxquels il appartient déjà.
        -   **Remplacer le groupe actuel :** Le groupe *principal* du client sera modifié pour le groupe sélectionné, le retirant potentiellement de son groupe principal précédent.
    -   **Effet de la modification de ce paramètre :**
        -   *Ajouter au groupe :* Les clients peuvent appartenir à plusieurs groupes, permettant une segmentation flexible.
        -   *Remplacer le groupe actuel :* Les clients n'appartiendront qu'à un seul groupe principal, simplifiant la gestion mais pouvant entraîner la perte d'autres affiliations de groupe.
    -   **Valeur recommandée :** « Ajouter au groupe » offre plus de flexibilité pour la plupart des scénarios. Utilisez « Remplacer le groupe actuel » avec prudence, surtout si d'autres modules dépendent des attributions de groupe principal.
    -   **Scénario / exemple de marchand :**
        -   *Ajouter au groupe :* Un client qui achète un produit spécifique est ajouté aux « Acheteurs VIP » mais reste dans les « Clients Généraux ».
        -   *Remplacer le groupe actuel :* Un client qui achète un produit spécifique est déplacé des « Clients Généraux » vers les « Clients Grossistes », devenant leur nouveau groupe principal.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1.  **Planifiez vos segments de clientèle :** Avant de créer des règles, décidez quels groupes de clients vous souhaitez avoir et quels critères les définissent.
2.  **Créez vos groupes de clients :** Allez dans **Clients > Groupes** dans votre Back Office PrestaShop et créez tous les nouveaux groupes dont vous avez besoin (par exemple, « Grossiste », « VIP », « Acheteurs du Produit X »).
3.  **Définissez les règles :** Pour chaque groupe de clients, créez une nouvelle règle d'association dans la configuration du module.
4.  **Testez minutieusement :** Effectuez un achat test avec un compte client test pour vous assurer que l'attribution du groupe se déroule comme prévu.
5.  **Examinez régulièrement :** Vérifiez périodiquement vos règles et les attributions de groupes de clients pour vous assurer qu'elles sont toujours pertinentes par rapport à vos objectifs commerciaux.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Module activé/désactivé | Activé | Contrôle si le module traite activement les commandes pour les attributions de groupe. |
| **Associations de groupes de produits** | Groupe de clients cible | N/A (Défini par l'utilisateur) | Le groupe auquel les clients seront attribués. |
| | Produits / Catégories | N/A (Défini par l'utilisateur) | Les produits ou catégories spécifiques dont l'achat déclenche l'attribution. |
| | Quantité minimale | Vide (Toute quantité) | Nombre minimum d'articles des produits/catégories de la règle requis dans une commande. |
| | Statut de commande pour déclencher | Paiement accepté / Livré | Le statut de commande auquel l'attribution du groupe est traitée. |
| | Type d'attribution | Ajouter au groupe | Détermine si le client est ajouté au groupe ou si son groupe principal est remplacé. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients ne sont pas attribués aux groupes après leur achat. Qu'est-ce qui ne va pas ?**
R :

1.  **Vérifier le statut du module :** Assurez-vous que le module est activé dans **Modules > Gestionnaire de modules** et sur sa page de configuration principale.
2.  **Vérifier le statut de la commande :** Vérifiez le paramètre « Statut de commande pour déclencher l'attribution » de votre règle. La commande du client a-t-elle réellement atteint ce statut spécifique (par exemple, « Paiement accepté », « Livré ») ? Les commandes en statut « En attente » ou « Annulée » ne déclencheront pas l'attribution si votre règle spécifie un statut ultérieur.
3.  **Examiner les conditions de la règle :** Vérifiez à nouveau les produits/catégories sélectionnés dans votre règle. Sont-ils exactement ce que le client a acheté ? La « Quantité minimale » est-elle respectée ?
4.  **Vider le cache :** Parfois, le cache de PrestaShop peut causer des problèmes. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».
5.  **Vérifier les conflits :** Désactivez temporairement les autres modules qui modifient les groupes de clients ou le traitement des commandes pour voir s'il y a un conflit.

**Q : Un client peut-il appartenir à plusieurs groupes ?**
R : Oui, si vous utilisez l'option « Ajouter au groupe » lors de la création de vos règles. Cela permet aux clients d'accumuler des appartenances à des groupes en fonction de divers comportements d'achat. Si vous utilisez « Remplacer le groupe actuel », ils n'appartiendront qu'à un seul groupe principal.

**Q : Que se passe-t-il si un client achète des produits qui déclenchent plusieurs règles ?**
R : Le module traitera toutes les règles applicables. Si les règles utilisent « Ajouter au groupe », le client sera ajouté à tous les groupes pertinents. Si les règles utilisent « Remplacer le groupe actuel », la dernière règle traitée (basée sur la logique interne du module ou l'ordre de création des règles) pourrait déterminer le groupe principal final, mais il est préférable d'éviter les règles de « Remplacement » conflictuelles.

**Q : J'ai modifié une règle, mais les anciennes commandes ne sont pas mises à jour. Pourquoi ?**
R : Le module traite généralement les attributions de groupe lorsqu'une commande *change* pour le statut spécifié. Il n'applique pas rétroactivement les règles aux commandes déjà terminées et traitées. Si vous devez réévaluer les anciens clients, vous devrez peut-être les attribuer manuellement ou envisager un script personnalisé (pour les développeurs) pour réexécuter la logique.

**Q : Comment traduire le texte du module ?**
R : Allez dans **International > Traductions** dans votre Back Office PrestaShop. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Attribuer des clients à un groupe par produits achetés » dans la liste des modules. Vous pourrez alors traduire toutes les chaînes visibles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Attribuer des clients à un groupe par produits achetés » (`pgroup`) suit une architecture de module PrestaShop standard, exploitant principalement le modèle MVC pour ses composants Back Office. Il s'intègre aux fonctionnalités principales de PrestaShop via des hooks, notamment en réagissant aux changements de statut de commande pour déclencher sa logique d'attribution de groupe de clients. Le module n'introduit aucun contrôleur front-office, car sa fonctionnalité est entièrement pilotée par le backend. Il utilise un `AdminController` personnalisé pour gérer les règles d'association produit-groupe et s'appuie sur l'`ObjectModel` de PrestaShop pour la persistance des données.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Toute la logique est gérée dans le Back Office ou via des hooks.
-   **Contrôleurs Admin Back-Office** :

    -   `pgroup/controllers/admin/AdminProductGroupsAssociationsController.php`
        -   **Nom de la classe :** `AdminProductGroupsAssociationsController` (étend `ModuleAdminController`)
        -   **Responsabilité :** C'est le contrôleur principal pour la gestion des règles d'association produit-groupe de clients. Il gère l'affichage de la liste des règles (en utilisant `HelperList`) et la création/modification des règles individuelles (en utilisant `HelperForm`). Il interagit avec l'`ObjectModel` `PgAssign` pour persister et récupérer les données d'association. Ce contrôleur est responsable du rendu de la grille des associations et du formulaire pour les ajouter/modifier.
    -   `pgroup/controllers/admin/index.php`
        -   **Nom de la classe :** Pas une classe, généralement un fichier vide ou une simple redirection pour empêcher l'accès direct au répertoire. Dans PrestaShop, les fichiers `index.php` dans les répertoires de contrôleurs servent généralement de marqueurs de sécurité.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le modèle de données principal pour les attributions de groupe de produits est probablement défini directement dans le fichier principal du module (`pgroup/index.php`) en tant qu'`ObjectModel` ou géré par des requêtes directes à la base de données.

-   **Modèle probable (dans `pgroup/index.php`) :**
    -   **Nom de la classe :** `PgAssign` (ou similaire, étendant `ObjectModel`)
    -   **Table de base de données :** `ps_pgassign` (ou similaire, basé sur l'`AdminProductGroupsAssociationsController` gérant l'entité `pgassign`).
    -   **Champs `$definition` :** Inclurait généralement des champs comme :
        -   `id_pgassign` (Clé primaire)
        -   `id_group` (ID du groupe de clients cible)
        -   `id_product` (ID du produit, si la règle est spécifique au produit)
        -   `id_category` (ID de la catégorie, si la règle est spécifique à la catégorie)
        -   `min_quantity` (Quantité minimale requise)
        -   `id_order_state` (Statut de commande pour déclencher l'attribution)
        -   `assignment_type` (par exemple, 'add' ou 'replace')
    -   **Méthodes publiques clés :**
        -   `add()` : Pour enregistrer une nouvelle règle d'association.
        -   `update()` : Pour modifier une règle d'association existante.
        -   `delete()` : Pour supprimer une règle d'association.
        -   `getAssociationsByProduct($id_product)` : Pour récupérer les règles basées sur un produit.
        -   `getAssociationsByCategory($id_category)` : Pour récupérer les règles basées sur une catégorie.

### 4.4 Actifs JavaScript (`views/js/`)

-   `pgroup/lib/searchTool/views/js/autocomplete.js`
    -   **Portée :** Back-office (probablement utilisé dans le formulaire `AdminProductGroupsAssociationsController`).
    -   **Fonctionnalité :** Implémente une fonction de recherche avec autocomplétion, probablement pour sélectionner des produits ou des catégories lors de la création/modification d'une règle d'attribution. Il écoute la saisie de l'utilisateur dans un champ de texte spécifique, envoie des requêtes AJAX à un point de terminaison backend (probablement un contrôleur AJAX admin dédié ou la méthode `ajaxProcess` du module principal) pour récupérer les produits/catégories correspondants, et affiche des suggestions. Il gère ensuite la sélection d'un élément, remplissant les champs de saisie cachés avec les ID.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `pgroup/css.css`
    -   **Portée :** Back-office (style général du module).
    -   **Fonctionnalité :** Contient des règles de style générales pour la page de configuration du module et potentiellement l'interface `AdminProductGroupsAssociationsController`. Cela peut inclure des styles pour les éléments de formulaire, les boutons ou les ajustements de mise en page spécifiques au module.
-   `pgroup/lib/searchTool/views/css/autocomplete.css`
    -   **Portée :** Back-office (style spécifique à l'autocomplétion).
    -   **Fonctionnalité :** Fournit le style pour le champ de saisie de recherche avec autocomplétion, la liste déroulante des suggestions et les éléments mis en surbrillance dans la liste. Les développeurs peuvent remplacer ces classes pour correspondre aux thèmes personnalisés du Back Office.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** : Aucun explicitement listé, indiquant que l'impact front-office du module est indirect et non par injection directe de contenu via des hooks.
-   **Modèles d'administration (`views/templates/admin/`)** :

    -   `pgroup/lib/searchTool/views/scripts.tpl`
        -   **Portée :** Back-office.
        -   **Fonctionnalité :** Inclut probablement des scripts d'initialisation JavaScript pour la fonctionnalité d'autocomplétion. Ce modèle serait inclus dans le formulaire de l'`AdminProductGroupsAssociationsController` pour rendre le JS nécessaire à l'outil de recherche de produits/catégories.
    -   `pgroup/views/templates/admin/orderstates.tpl`
        -   **Portée :** Back-office.
        -   **Fonctionnalité :** Ce modèle rend probablement une liste déroulante ou une liste des statuts de commande PrestaShop, permettant au marchand de sélectionner le statut qui devrait déclencher l'attribution du groupe de clients. Il ferait partie du `HelperForm` utilisé dans `AdminProductGroupsAssociationsController`.
    -   `pgroup/views/templates/admin/script.tpl`
        -   **Portée :** Back-office.
        -   **Fonctionnalité :** Pourrait contenir du JavaScript ou de la logique Smarty supplémentaire spécifique à la page de configuration du module ou aux formulaires `AdminProductGroupsAssociationsController`, tels que l'affichage conditionnel de champs ou les appels AJAX.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   `ps_pgassign` : Cette table est créée par le module lors de l'installation. Elle stocke les règles d'association produit-groupe.
        -   `id_pgassign` (INT, CLÉ PRIMAIRE, AUTO_INCREMENT)
        -   `id_group` (INT, clé étrangère vers `ps_group`)
        -   `id_product` (INT, clé étrangère vers `ps_product`, nullable si la règle est basée sur une catégorie)
        -   `id_category` (INT, clé étrangère vers `ps_category`, nullable si la règle est basée sur un produit)
        -   `min_quantity` (INT, par défaut 1)
        -   `id_order_state` (INT, clé étrangère vers `ps_order_state`)
        -   `assignment_type` (VARCHAR, par exemple, 'add', 'replace')
    -   Enregistrements de configuration dans `ps_configuration` : Le module pourrait stocker son paramètre principal `PS_PGROUP_ENABLED` (ou similaire) ici.
-   **Table des hooks enregistrés** :
    La fonctionnalité principale du module repose sur des hooks qui se déclenchent lorsqu'un statut de commande change.

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `actionOrderStatusPostUpdate` | Exécuté immédiatement après la mise à jour du statut d'une commande. | C'est le hook le plus probable utilisé par le module pour vérifier si une commande a atteint le statut configuré et ensuite appliquer les règles d'attribution de groupe basées sur les produits de cette commande. |
    | `actionObjectOrderUpdateAfter` | Exécuté après la mise à jour d'un objet Commande. | Pourrait également être utilisé, de manière similaire à `actionOrderStatusPostUpdate`, pour réagir aux changements de commande. |
    | `displayHeader` | Rend le contenu dans la section `<head>` des pages du front-office. | Non directement utilisé pour la fonctionnalité principale, mais pourrait être utilisé pour charger du JS/CSS global si le module avait des composants front-office (ce qui ne semble pas être le cas). |
    | `displayRightColumn` / `displayLeftColumn` | Rend le contenu dans les colonnes latérales des pages du front-office. | Non directement utilisé pour la fonctionnalité principale. |
    | `displayProductAdditionalInfo` / `displayProductButtons` | Rend le contenu sur la page du produit. | Non directement utilisé pour la fonctionnalité principale. |
    | `displayFooter` | Rend le contenu dans le pied de page des pages du front-office. | Non directement utilisé pour la fonctionnalité principale. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Attribuer des clients à un groupe par produits achetés », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
