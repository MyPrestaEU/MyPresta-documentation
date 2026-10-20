---
title: "Delete Orders Free - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Delete Orders Free par MyPresta.eu."
sidebar:
  label: "Delete Orders Free - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Delete Orders Free sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/delete-orders-free/)
>
> ---


# Delete Orders Free

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et activées par défaut sur la plupart des environnements d'hébergement.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur "Configurer" vous mènera à la page de configuration principale du module. Cette page gère principalement les notifications de mise à jour pour le module lui-même.

-   **Ce que fait ce paramètre :** Cette section gère la capacité du module à vérifier les mises à jour et à afficher des notifications.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé :* Le module vérifiera périodiquement MyPresta.eu pour des versions plus récentes. Si une mise à jour est disponible, une notification pourrait apparaître dans votre back office PrestaShop, vous invitant à télécharger et installer la dernière version. Cela garantit que vous disposez toujours de la version la plus sécurisée et la plus riche en fonctionnalités du module.
    *   *Lorsqu'il est désactivé :* Le module ne vérifiera pas les mises à jour automatiquement. Vous devrez visiter manuellement MyPresta.eu pour vérifier les nouvelles versions. Bien que cela puisse légèrement réduire les requêtes serveur, cela signifie que vous pourriez manquer des mises à jour importantes ou des corrections de bugs.
-   **Valeur recommandée :** **Activé (OUI)**. Garder cette option activée garantit que vous êtes toujours informé des dernières améliorations et correctifs de sécurité pour le module.
-   **Scénario / exemple pour le marchand :** Vous souhaitez être informé si une nouvelle version de "Delete Orders Free" est publiée, corrigeant un bug ou ajoutant une nouvelle fonctionnalité. Garder cette option activée garantit que vous verrez une notification dans votre panneau d'administration PrestaShop.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Onglet Supprimer les commandes (Back Office > Commandes > Supprimer les commandes)

C'est l'interface principale de la fonctionnalité du module.

-   **Nom de l'écran et emplacement du menu :** Vous pouvez accéder à cet écran en naviguant vers **Commandes > Supprimer les commandes** dans le menu de votre back office PrestaShop.
-   **Actions et paramètres disponibles :**
    *   En entrant dans cet onglet, vous verrez une liste de toutes les commandes de votre boutique PrestaShop, similaire à la liste standard des "Commandes".
    *   Chaque commande de la liste aura un bouton ou une icône **"Supprimer"** dédié (souvent une icône de corbeille) à côté.
    *   **Supprimer une commande :** Cliquer sur le bouton "Supprimer" à côté de n'importe quelle commande supprimera immédiatement et définitivement cette commande de votre base de données. Cette action est irréversible.
-   **Effet des modifications :**
    *   Lorsque vous cliquez sur "Supprimer" pour une commande, l'enregistrement de la commande, ainsi que toutes les données associées (telles que les détails de la commande, les messages clients liés à cette commande, les factures et potentiellement les mouvements de stock si le statut de la commande était configuré pour affecter le stock) seront supprimés de votre base de données PrestaShop.
    *   La commande n'apparaîtra plus dans votre liste "Commandes", ni ne sera incluse dans les rapports de ventes ou les statistiques.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Examinez régulièrement votre liste "Commandes" pour les commandes de test, les commandes frauduleuses ou les commandes qui ont été complètement annulées et n'ont plus besoin d'être suivies.
    2.  Naviguez vers **Commandes > Supprimer les commandes**.
    3.  Identifiez soigneusement les commandes que vous souhaitez supprimer.
    4.  Cliquez sur le bouton "Supprimer" à côté de chaque commande spécifique que vous souhaitez supprimer.
    5.  Confirmez la suppression si vous y êtes invité.
    6.  **Important :** Faites preuve d'une extrême prudence car cette action est permanente et ne peut être annulée. Il est fortement recommandé d'effectuer une sauvegarde de la base de données avant de supprimer un grand nombre de commandes.

#### 2.2.2 Index.php (deleteordersfree/controllers/admin/index.php)

Ce fichier est un contrôleur PrestaShop standard et ne présente généralement pas d'écran configurable directement au marchand. Son but est généralement de rediriger vers la configuration principale du module ou un onglet d'administration spécifique. Dans le contexte de ce module, il assure probablement que la navigation vers le chemin d'administration de base du module vous dirige correctement vers le contrôleur `deleteorderstab`.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Défaut / Recommandé | Objectif et Impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Vérification des mises à jour (mypresta\_updates) | Activé (OUI) | Contrôle si le module vérifie les nouvelles versions et vous en informe. Gardez activé pour les mises à jour. |
| **Commandes > Supprimer les commandes** | Bouton Supprimer (par commande) | N/A | Supprime définitivement une commande sélectionnée et ses données associées de la base de données. **Action irréversible.** |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai supprimé une commande par erreur ! Puis-je la récupérer ?**
R : Malheureusement, non. Le module "Delete Orders Free" effectue une suppression permanente. C'est pourquoi nous insistons sur la prudence. Ayez toujours une sauvegarde récente de votre base de données, surtout avant d'effectuer des suppressions en masse. Si vous avez une sauvegarde, vous pourriez être en mesure de restaurer l'intégralité de votre base de données à un état antérieur, mais cela annulerait également toutes les autres modifications effectuées depuis la sauvegarde.

**Q : Je ne vois pas l'onglet "Supprimer les commandes" sous le menu "Commandes".**
R :

1.  **Vérifier l'installation du module :** Allez dans **Modules > Gestionnaire de modules** et recherchez "Delete Orders Free". Assurez-vous qu'il est installé et activé.
2.  **Vider le cache :** Parfois, le cache du menu de PrestaShop doit être rafraîchi. Allez dans **Paramètres avancés > Performances**, faites défiler jusqu'à "Vider le cache" et cliquez sur "Vider le cache".
3.  **Vérifier les permissions :** Assurez-vous que votre profil utilisateur dispose des permissions nécessaires pour accéder et gérer les modules et les commandes. Allez dans **Paramètres avancés > Équipe > Profils**, sélectionnez votre profil, puis allez dans **Permissions > Modules** et **Permissions > Commandes** pour vérifier.

**Q : La suppression d'une commande remboursera-t-elle également le client ou annulera-t-elle le paiement ?**
R : Non. Ce module ne fait que supprimer l'enregistrement de la commande de votre base de données PrestaShop. Il n'interagit PAS avec les passerelles de paiement (comme PayPal, Stripe, etc.) pour émettre des remboursements ou annuler des transactions. Vous devez gérer tout remboursement ou annulation de paiement directement via l'interface de votre passerelle de paiement.

**Q : La suppression d'une commande affecte-t-elle le stock de produits ?**
R : Si la configuration de vos statuts de commande PrestaShop est définie pour décrémenter le stock lorsqu'une commande est passée, et que vous supprimez une commande, le stock ne sera PAS automatiquement ré-incrémenté. Vous devrez ajuster manuellement le stock des produits concernés si vous souhaitez les remettre en inventaire. C'est un point critique à retenir pour la gestion des stocks.

**Q : Le module est installé, mais je ne vois aucun bouton "Supprimer" sur la liste des commandes.**
R : Assurez-vous d'être sur l'onglet dédié **Commandes > Supprimer les commandes**, et non sur la liste standard **Commandes > Commandes**. La fonctionnalité de suppression est spécifiquement ajoutée à l'onglet personnalisé du module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module "Delete Orders Free" est un module PrestaShop simple, principalement axé sur l'extension de la fonctionnalité du Back Office. Il suit un modèle MVC PrestaShop standard pour son interface administrative. La logique principale réside dans le fichier principal du module pour l'installation/désinstallation et dans un AdminController dédié pour gérer le processus de suppression des commandes. Il n'introduit pas de nouvelles tables de base de données ni d'interactions complexes avec le front-office.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Ce module n'a pas de présence en front-office.
-   **Contrôleurs Admin Back-Office** :

    -   `deleteordersfree/controllers/admin/deleteorderstab.php`
        -   **Nom de la classe et classe parente** : `DeleteOrdersTabController` étend `ModuleAdminController`.
        -   **Responsabilité** : C'est le contrôleur principal de la fonctionnalité du module. Il affiche la liste des commandes dans le Back Office, fournissant l'action "Supprimer" pour chaque commande. Il gère la logique de réception de la requête de suppression (par exemple, via un paramètre GET ou une soumission POST) puis exécute la suppression de la base de données pour l'ID de commande spécifié. Ce contrôleur surcharge ou étend probablement des méthodes de `AdminController` pour afficher la liste des commandes et ajouter l'action personnalisée.
    -   `deleteordersfree/controllers/admin/index.php`
        -   **Nom de la classe et classe parente** : Il s'agit généralement d'un fichier de substitution qui assure un routage correct dans la section d'administration. Il contient généralement une simple redirection `header('Location: ...')` ou un fichier vide pour empêcher la liste des répertoires. Dans PrestaShop, les fichiers `index.php` dans les sous-répertoires de `controllers/admin` sont souvent utilisés pour définir le point d'entrée d'une section spécifique ou pour empêcher l'accès direct. Pour ce module, il assure probablement que l'accès au chemin de base `admin/deleteordersfree` dirige correctement vers le contrôleur `deleteorderstab`.

### 4.3 Classes et Modèles de base (`classes/`)

Ce module n'introduit aucune classe personnalisée ou définition d'`ObjectModel`. Il interagit directement avec les classes `Order` et les classes `ObjectModel` associées de PrestaShop (par exemple, `OrderInvoice`, `OrderPayment`, `OrderHistory`, `Message`, `Cart`, `CustomerThread`, `SpecificPrice`, `StockAvailable`) pour effectuer les suppressions.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est inclus dans ce module. L'action de suppression est probablement gérée via une soumission de formulaire standard ou une simple requête GET avec une invite de confirmation.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est inclus dans ce module. Le module s'appuie sur le style par défaut du Back Office de PrestaShop pour son interface.

### 4.6 Structure des templates Smarty (`views/templates/`)

Aucun fichier de template Smarty personnalisé n'est explicitement listé dans l'inventaire du module. Le contrôleur `deleteorderstab` utilise probablement les templates par défaut de PrestaShop `list.tpl` ou des templates similaires pour afficher la grille des commandes, en injectant l'action "Supprimer" via la logique du contrôleur (par exemple, la méthode `renderList()`).

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** : Ce module ne crée aucune nouvelle table de base de données personnalisée. Il opère directement sur les tables principales existantes de PrestaShop liées aux commandes, telles que :

    -   `ps_orders`
    -   `ps_order_detail`
    -   `ps_order_history`
    -   `ps_order_invoice`
    -   `ps_order_payment`
    -   `ps_message` (pour les messages liés à la commande)
    -   `ps_cart` (le panier associé à la commande)
    -   `ps_customer_thread` (fils de discussion du service client liés à la commande)
    -   `ps_specific_price` (si des prix spécifiques ont été appliqués via la commande)
    -   `ps_stock_available` (si le stock a été décrémenté par la commande)
    -   Et potentiellement d'autres tables connexes (par exemple, `ps_order_carrier`, `ps_order_slip`).
        Il stocke également ses paramètres de configuration (comme `mypresta_updates`) dans la table `ps_configuration`.
-   **Table des hooks enregistrés** :
    La description du module mentionne "Hooks Front-Office : Header, Columns, Product, ou Footer" mais la fonctionnalité du module est purement back-office. Cela suggère que ces hooks ne sont soit pas activement utilisés par la logique principale du module, soit qu'ils sont des vestiges d'un template de module générique. Basé sur l'objectif déclaré du module et l'inventaire des fichiers, il est hautement improbable qu'il affiche quoi que ce soit dans ces hooks front-office.

    L'utilisation principale des hooks pour ce module est probablement :

    | Nom du Hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `actionAdminControllerSetMedia` | Exécuté lorsqu'un AdminController est initialisé et avant que son contenu ne soit rendu. | Potentiellement utilisé pour ajouter du JS/CSS personnalisé (bien qu'aucun ne soit listé) ou pour enregistrer des actifs spécifiques au module pour la page d'administration. |
    | `displayBackOfficeHeader` | Exécuté dans l'en-tête de chaque page du Back Office. | Pourrait être utilisé pour les notifications de mise à jour ou pour injecter des scripts/styles mineurs spécifiques à l'administration. |
    | `actionModuleInstall` | Exécuté lors de l'installation du module. | Crée l'onglet "Supprimer les commandes" dans le menu du Back Office et définit les valeurs de configuration par défaut. |
    | `actionModuleUninstall` | Exécuté lors de la désinstallation du module. | Supprime l'onglet "Supprimer les commandes" et nettoie les valeurs de configuration. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module "Delete Orders Free", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question lié à la fonctionnalité du module.
