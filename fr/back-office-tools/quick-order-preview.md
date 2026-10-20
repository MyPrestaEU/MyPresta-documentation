---
title: "Aperçu rapide des commandes - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Aperçu rapide des commandes par MyPresta.eu."
sidebar:
  label: "Aperçu rapide des commandes - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Quick Order Preview sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-order-preview.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/quick-order-preview/)
>
> ---


# Aperçu rapide des commandes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 9.x, 8.x, 1.7.7.x - 1.7.8.x, 1.7.0.0 - 1.7.6.x, 1.6.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Aperçu rapide des commandes ». Cela vous mènera à son écran de configuration principal.

Il n'y a pas d'options de configuration spécifiques sur cet écran pour le module « Aperçu rapide des commandes ». Le module fonctionne tel quel en améliorant la fonctionnalité existante de la page « Commandes ». Sa fonction principale est d'injecter le JavaScript et les modèles nécessaires pour activer la fonction d'aperçu rapide directement dans votre liste de commandes.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminPreviewOrderController (Back Office > Commandes > Liste des commandes)

Ce module n'ajoute pas de nouvel élément de menu à votre back office PrestaShop. Au lieu de cela, il améliore la page de liste des **« Commandes »** existante (située sous **Back Office > Commandes > Commandes**).

-   **Nom de l'écran et emplacement du menu :** Vous accédez à cette fonctionnalité améliorée en naviguant vers **Commandes > Commandes** dans votre back office PrestaShop.
-   **Actions et paramètres disponibles :**
    *   **Fonctionnalité d'aperçu rapide :** Lorsque vous êtes sur la page de liste des « Commandes », cliquez simplement sur n'importe quelle ligne de commande. Au lieu d'être redirigé vers la page complète des détails de la commande, le module développera la ligne de commande pour afficher les informations clés directement en dessous. Cela inclut :
        *   **Adresse du client :** Adresses de facturation et de livraison.
        *   **Produits commandés :** Une liste des articles achetés, y compris les quantités et les prix.
        *   **Note du client :** Si le client a laissé une note lors du paiement, elle sera visible ici.
    *   **Bouton « Voir la commande » :** Dans l'aperçu étendu, vous trouverez toujours un bouton « Voir la commande » (ou un lien similaire) qui vous permet de naviguer vers la page complète et traditionnelle des détails de la commande si vous devez effectuer des actions telles que changer le statut de la commande, ajouter des produits ou générer des factures.
    *   **Enregistrement de la note du client :** Le module inclut également une fonctionnalité pour enregistrer les notes du client directement depuis cet aperçu rapide. Ceci est géré par le script `save-customer-note.js`.
-   **Effet des changements :**
    *   Cliquer sur une ligne de commande bascule désormais l'affichage de ses informations détaillées directement sur la page de liste des commandes.
    *   Vous pouvez rapidement consulter les données essentielles de la commande sans quitter la liste principale, ce qui accélère considérablement votre flux de travail de traitement des commandes.
    *   La possibilité d'enregistrer les notes du client directement depuis l'aperçu rationalise la communication et la tenue des registres.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Allez dans **Commandes > Commandes**.
    2.  Pour vérifier rapidement ce qu'un client a commandé ou son adresse de livraison, cliquez simplement sur la ligne de commande dans la liste.
    3.  Les détails s'afficheront sous la commande. Passez en revue les informations.
    4.  Si vous devez modifier le statut de la commande, imprimer une facture ou effectuer d'autres actions avancées, cliquez sur le bouton « Voir la commande » dans l'aperçu étendu pour accéder à la page complète des détails de la commande.
    5.  Si vous devez ajouter une note rapide sur le client ou la commande, utilisez le champ de note du client dans l'aperçu et enregistrez-la.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Liste des commandes | Cliquer sur la ligne de commande | N/A | Développe les détails de la commande (produits, adresses, notes) directement sur la page de liste, ce qui permet de gagner du temps de navigation. |
| Liste des commandes | Champ Note du client | N/A | Permet d'enregistrer des notes directement depuis l'aperçu rapide. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Les détails de la commande ne s'affichent pas lorsque je clique sur une ligne de commande. Qu'est-ce qui ne va pas ?**
R :

1.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite. Parfois, d'anciens fichiers de cache empêchent le chargement des scripts de nouveaux modules.
2.  **Module activé :** Assurez-vous que le module « Aperçu rapide des commandes » est activé dans **Modules > Gestionnaire de modules**.
3.  **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, des thèmes très fortement personnalisés peuvent parfois interférer. Vérifiez la console de développement de votre navigateur (F12) pour les erreurs JavaScript. Si vous voyez des erreurs liées au module, contactez le support MyPresta.eu.
4.  **Version de PrestaShop :** Assurez-vous d'avoir téléchargé et installé la version correcte du module pour votre installation PrestaShop spécifique.

**Q : Puis-je personnaliser les informations affichées dans l'aperçu rapide ?**
R : Le module affiche des informations essentielles comme les produits et les adresses. La personnalisation des champs affichés nécessiterait une modification directe des fichiers de modèle du module (`address.tpl`, `products.tpl`). Il s'agit d'une tâche de niveau développeur.

**Q : Ce module affecte-t-il les performances de ma boutique ?**
R : Non, le module est conçu pour être léger. Il ne charge du contenu supplémentaire que lorsque vous cliquez explicitement sur une ligne de commande dans le back office. Il n'ajoute aucune surcharge à votre front office ou à la navigation générale du back office.

**Q : J'utilise une ancienne version de PrestaShop 1.6, cela fonctionnera-t-il ?**
R : Oui, le module est compatible avec PrestaShop 1.6.x. Assurez-vous de télécharger le package correct pour votre version de PrestaShop depuis votre compte MyPresta.eu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Aperçu rapide des commandes » (`qov`) est principalement un module d'amélioration du Back Office. Il tire parti du mécanisme de surcharge d'`AdminController` de PrestaShop et du templating Smarty pour injecter du contenu dynamique dans la liste des « Commandes » existante. Il utilise JavaScript pour gérer les requêtes AJAX et la manipulation du DOM pour développer/réduire les détails de la commande. Le module n'introduit pas de nouvelles tables de base de données ni de structures `ObjectModel` complexes, se concentrant plutôt sur l'augmentation des fonctionnalités PrestaShop existantes.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Ce module est purement un outil Back Office.
-   **Contrôleurs Admin Back-Office** :

    -   `qov/controllers/admin/AdminPreviewOrder.php`
        -   **Nom de la classe et classe parente** : `AdminPreviewOrderController` étend `AdminOrdersController`.
        -   **Responsabilité** : Ce contrôleur surcharge le `AdminOrdersController` par défaut pour injecter le JavaScript nécessaire et potentiellement modifier la méthode `renderList()` afin d'inclure la fonctionnalité d'aperçu rapide. Il est responsable de la gestion des requêtes AJAX qui récupèrent les détails de la commande (produits, adresses) lorsqu'une ligne de commande est cliquée, et du rendu des modèles `address.tpl` et `products.tpl` avec les données récupérées. Il gère également la clé de configuration `QOV_TRACKING_EMAIL`, bien que son utilisation directe ne soit pas évidente d'après les informations fournies.

### 4.3 Classes et modèles de base (`classes/`)

Aucun. Le module ne définit pas de classes `ObjectModel` personnalisées ni de classes de logique métier complexes. Il interagit principalement avec les classes de base PrestaShop existantes comme `Order`, `Address`, `Product`, etc., via son contrôleur.

### 4.4 Actifs JavaScript (`views/js/`)

-   `qov/views/js/177-expand-all-imm.js`

    -   **Portée** : Back-office (liste des commandes, PrestaShop 1.7.7+).
    -   **Description** : Ce script gère probablement l'expansion immédiate de tous les détails de commande sur la page de liste des commandes, éventuellement pour une vue ou une action spécifique. Il lierait les événements de clic aux lignes de commande et déclencherait des appels AJAX pour récupérer et afficher les détails de plusieurs commandes simultanément.
-   `qov/views/js/177-expand-all.js`

    -   **Portée** : Back-office (liste des commandes, PrestaShop 1.7.7+).
    -   **Description** : Similaire à `177-expand-all-imm.js`, ce script est responsable de la fonctionnalité « tout développer ». Il écouterait un déclencheur spécifique (par exemple, un clic sur un bouton) pour développer tous les détails de commande visibles sur la page actuelle, en effectuant des requêtes AJAX pour chaque commande.
-   `qov/views/js/177orders-multiple.js`

    -   **Portée** : Back-office (liste des commandes, PrestaShop 1.7.7+).
    -   **Description** : C'est le script principal qui active la fonctionnalité d'aperçu rapide. Il lie les événements de clic aux lignes de commande individuelles dans la liste `AdminOrders`. Lorsqu'une ligne de commande est cliquée, il empêche la navigation par défaut vers la page complète de la commande. Au lieu de cela, il effectue une requête AJAX vers l'`AdminPreviewOrderController` (ou un point de terminaison similaire) pour récupérer les produits, adresses et autres détails de la commande. Il injecte ensuite dynamiquement le HTML rendu (à partir de `address.tpl` et `products.tpl`) dans une nouvelle ligne ou une section étendue sous la ligne de commande cliquée. Il gère également la réduction des détails lorsque la ligne est cliquée à nouveau.
-   `qov/views/js/save-customer-note.js`

    -   **Portée** : Back-office (liste des commandes, spécifiquement dans l'aperçu rapide).
    -   **Description** : Ce script gère la fonctionnalité d'enregistrement des notes client directement depuis l'aperçu rapide des commandes. Il se lie aux champs de saisie ou aux boutons dans les détails de commande étendus. Lorsqu'une note est saisie ou mise à jour, il envoie une requête AJAX à un point de terminaison du back-office (probablement l'`AdminPreviewOrderController` ou le `AdminOrdersController` par défaut avec une action spécifique) pour persister la note dans la base de données, généralement dans la table `ps_order_note` ou similaire.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun. Le module n'inclut pas de fichiers CSS personnalisés. Il s'appuie probablement sur le style existant du back-office PrestaShop ou sur des styles en ligne pour les détails de commande étendus. Les développeurs souhaitant styliser l'aperçu doivent cibler les éléments HTML injectés dynamiquement.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `qov/views/templates/admin/address.tpl`
        -   **Description** : Ce modèle est utilisé pour afficher les détails de l'adresse de facturation et de livraison du client dans l'aperçu rapide de la commande. Il reçoit les données d'adresse de l'`AdminPreviewOrderController` et les formate pour l'affichage.
    -   `qov/views/templates/admin/products.tpl`
        -   **Description** : Ce modèle est responsable de l'affichage de la liste des produits commandés par le client dans l'aperçu rapide de la commande. Il reçoit les données des produits (nom, quantité, prix, etc.) et les affiche dans un format clair, tabulaire ou de liste.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table de base de données personnalisée. Il lit et potentiellement écrit (pour les notes client) dans les tables PrestaShop standard telles que `ps_orders`, `ps_order_detail`, `ps_address`, `ps_customer` et `ps_order_note`.
    -   Les valeurs de configuration sont stockées dans `ps_configuration`, spécifiquement `QOV_TRACKING_EMAIL`.
-   **Table des hooks enregistrés** :
    Le module n'enregistre explicitement aucun hook front-office (comme `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`) car il s'agit d'un module back-office. Sa fonctionnalité est principalement injectée en surchargeant l'`AdminOrdersController` et en ajoutant du JavaScript et des modèles à la page « Commandes » existante du Back Office.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses ressources média. | Utilisé par `AdminPreviewOrderController` pour mettre en file d'attente ses fichiers JavaScript (`177-expand-all-imm.js`, `177-expand-all.js`, `177orders-multiple.js`, `save-customer-note.js`) pour la page `AdminOrders`. |
| `displayAdminOrder` | Exécuté sur la page de commande de l'administration. | Bien que non explicitement listée comme un hook, la fonctionnalité principale du module est obtenue en surchargeant `AdminOrdersController` et en modifiant sa méthode `renderList()` ou en injectant du contenu via JavaScript dans la liste de commandes existante. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Aperçu rapide des commandes », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
