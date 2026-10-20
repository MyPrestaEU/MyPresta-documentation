---
title: "Order Grid Pro - colonnes et mise en page de la liste des commandes - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Order Grid Pro - colonnes & mise en page de la liste des commandes par MyPresta.eu."
sidebar:
  label: "Order Grid Pro - colonnes et mise en page de la liste des commandes - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order Grid Pro - columns & layout of list of orders sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-pro-columns-layout-of-list-of-orders.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/order-grid-pro-columns-layout-of-list-of-orders/)
>
> ---


# Order Grid Pro - colonnes et mise en page de la liste des commandes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.7.x, 1.7.8.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale de serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur "Configurer" vous mènera à la page de configuration principale d'Order Grid Pro. C'est sur cette page que vous définissez les colonnes qui apparaissent dans votre liste de commandes et leur agencement.

La configuration est généralement divisée en plusieurs onglets ou sections, vous permettant de gérer différents aspects de la grille de commandes.

**Paramètres généraux / Visibilité et ordre des colonnes :**
C'est le cœur du module. Vous verrez généralement une liste de toutes les colonnes disponibles, à la fois les colonnes PrestaShop par défaut et les nouvelles ajoutées par Order Grid Pro.

-   **Ce que fait ce paramètre :** Cette section vous permet de choisir les colonnes visibles dans votre liste de commandes du Back Office et d'organiser leur ordre d'affichage. Vous verrez généralement deux listes : "Colonnes disponibles" et "Colonnes actives" (ou similaire).
-   **Effet de la modification de ce paramètre :**
    -   *Déplacer une colonne de "Disponible" vers "Active" :* La colonne apparaîtra dans votre liste de commandes du Back Office.
    -   *Déplacer une colonne de "Active" vers "Disponible" :* La colonne sera masquée de votre liste de commandes du Back Office.
    -   *Glisser-déposer des colonnes dans "Colonnes actives" :* Modifie l'ordre d'affichage de gauche à droite des colonnes dans votre liste de commandes.
-   **Valeur recommandée :** Cela dépend entièrement des besoins de votre équipe. Commencez par activer les colonnes que vous consultez fréquemment et masquez celles que vous n'utilisez jamais. Organisez-les dans un flux logique pour vos tâches quotidiennes.
-   **Scénario / exemple de marchand :**
    -   **Responsable d'entrepôt :** Pourrait activer "Miniature du produit", "Poids du produit", "Numéro de suivi" et "Transporteur" et les placer en évidence à gauche pour un traitement rapide des expéditions. Il pourrait masquer "E-mail du client" ou "Méthode de paiement" si cela n'est pas pertinent pour son rôle.
    -   **Agent du service client :** Prioriserait "Téléphone du client", "E-mail du client", "Extrait du fil de discussion du service client" et "Message de commande" pour répondre rapidement aux demandes sans ouvrir chaque commande.
    -   **Service financier :** Pourrait se concentrer sur "Méthode de paiement", "ISO de la devise", "Total payé" et "Règles de panier" pour vérifier les transactions et les remises.

**Options de colonnes spécifiques (Exemples de nouvelles colonnes que vous pouvez activer) :**

-   **Téléphone du client :**

    -   **Ce que fait ce paramètre :** Affiche le numéro de téléphone du client directement dans la liste des commandes.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les numéros de téléphone apparaissent, facilitant l'appel des clients sans naviguer vers les détails de leur commande.
        -   *Lorsqu'désactivé :* Les numéros de téléphone sont masqués.
    -   **Valeur recommandée :** OUI, si votre service client ou votre équipe d'expédition a fréquemment besoin de contacter les clients.
    -   **Scénario / exemple de marchand :** Un agent du service client peut rapidement appeler un client concernant un problème de livraison directement depuis la liste des commandes.
-   **Numéro de suivi :**

    -   **Ce que fait ce paramètre :** Affiche le numéro de suivi associé à la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les numéros de suivi sont visibles, permettant une copie-colle rapide pour les mises à jour de suivi.
        -   *Lorsqu'désactivé :* Les numéros de suivi sont masqués.
    -   **Valeur recommandée :** OUI, essentiel pour les équipes d'entrepôt et de service client.
    -   **Scénario / exemple de marchand :** Le personnel de l'entrepôt peut rapidement vérifier si un numéro de suivi a été ajouté avant l'expédition, ou le service client peut le fournir à un client.
-   **Miniature du premier produit :**

    -   **Ce que fait ce paramètre :** Affiche une petite image du premier produit de la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Un indice visuel du contenu de la commande apparaît, facilitant une identification rapide.
        -   *Lorsqu'désactivé :* Aucune image de produit n'est affichée.
    -   **Valeur recommandée :** OUI, très utile pour la confirmation visuelle, en particulier pour la préparation des commandes en entrepôt.
    -   **Scénario / exemple de marchand :** Le personnel de l'entrepôt peut confirmer visuellement le type de produit dans une commande sans l'ouvrir, accélérant ainsi la préparation.
-   **Poids de la commande :**

    -   **Ce que fait ce paramètre :** Affiche le poids total de la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Le poids de la commande est affiché, utile pour les calculs d'expédition ou la sélection du transporteur.
        -   *Lorsqu'désactivé :* Le poids de la commande est masqué.
    -   **Valeur recommandée :** OUI, si vous traitez des produits physiques et que le poids est un facteur d'expédition.
    -   **Scénario / exemple de marchand :** Les responsables d'expédition peuvent rapidement évaluer les tailles et les poids des colis pour les expéditions en vrac.
-   **Extrait du fil de discussion du service client :**

    -   **Ce que fait ce paramètre :** Affiche un court extrait du dernier message du service client lié à la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Fournit un contexte immédiat sur les communications client récentes.
        -   *Lorsqu'désactivé :* Aucun extrait n'est affiché.
    -   **Valeur recommandée :** OUI, inestimable pour les équipes de service client.
    -   **Scénario / exemple de marchand :** Un agent du service client peut voir si un client a récemment posé une question sur une commande sans ouvrir le fil de discussion complet.
-   **ISO de la devise :**

    -   **Ce que fait ce paramètre :** Affiche le code ISO de la devise utilisée pour la commande (par exemple, EUR, USD).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Utile pour les boutiques internationales afin d'identifier rapidement la devise.
        -   *Lorsqu'désactivé :* L'ISO de la devise est masqué.
    -   **Valeur recommandée :** OUI, si vous exploitez une boutique multi-devises.
    -   **Scénario / exemple de marchand :** Le personnel financier peut rapidement trier ou filtrer les commandes par devise pour la réconciliation.
-   **Règles de panier (réductions) appliquées :**

    -   **Ce que fait ce paramètre :** Indique si des règles de panier (réductions) ont été appliquées à la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Fournit un aperçu rapide des commandes avec réduction.
        -   *Lorsqu'désactivé :* Les informations sur les réductions appliquées sont masquées.
    -   **Valeur recommandée :** OUI, pour la finance, le marketing ou le service client afin de comprendre la tarification.
    -   **Scénario / exemple de marchand :** Le marketing peut rapidement identifier les commandes qui ont utilisé un code promotionnel spécifique.

**Enregistrement des modifications :**
N'oubliez jamais de cliquer sur le bouton "Enregistrer" ou "Mettre à jour" après avoir apporté des modifications à vos sélections de colonnes ou à leur ordre. Le module enregistre l'ordre des colonnes au format JSON, garantissant la persistance de votre mise en page personnalisée.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 AdminMyordergridproAjaxController (Back Office > Modules > Configurer > Order Grid Pro)

Ce contrôleur gère principalement les interactions dynamiques sur la page de configuration du module. Il n'a pas d'élément de menu séparé dans la navigation PrestaShop.

-   **Nom de l'écran et emplacement du menu :** Ce contrôleur est activé lorsque vous êtes sur la page "Modules > Gestionnaire de modules > Order Grid Pro > Configurer". Il traite les requêtes AJAX effectuées par le JavaScript sur cette page.
-   **Actions et paramètres disponibles :** Il gère l'enregistrement et le chargement de vos configurations de grille personnalisées (quelles colonnes sont visibles et leur ordre). Lorsque vous faites glisser et déposez des colonnes ou activez/désactivez leur visibilité sur la page de configuration du module, ce contrôleur reçoit les données et les enregistre.
-   **Effet des modifications :** Toutes les modifications que vous apportez à la mise en page des colonnes sur la page de configuration du module sont envoyées à ce contrôleur, qui met ensuite à jour les préférences stockées pour votre grille de commandes. Cela garantit que lorsque vous naviguez vers "Commandes > Commandes", votre mise en page personnalisée est appliquée.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vous interagissez indirectement avec ce contrôleur en configurant simplement le module sur sa page principale. Il n'y a pas de "vue de gestion" directe pour les marchands ici ; c'est le processeur backend de vos choix de configuration.

#### 2.2.2 index.php (myordergridpro/controllers/admin/index.php)

Ce fichier est un espace réservé standard ou un point d'entrée pour les contrôleurs d'administration au sein d'un module, garantissant que l'accès direct au répertoire est empêché et que les mécanismes de sécurité de PrestaShop sont respectés. Il ne représente pas un écran distinct et configurable pour le marchand.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | **Visibilité et ordre des colonnes** | Varie selon le rôle | Sélectionne les colonnes qui apparaissent dans la liste des commandes du Back Office et leur ordre d'affichage. Impacte directement l'efficacité de l'équipe. |
| | *Téléphone du client* | OUI | Affiche le numéro de téléphone du client pour un contact rapide. |
| | *Numéro de suivi* | OUI | Affiche le numéro de suivi de la commande pour l'expédition/le support. |
| | *Miniature du premier produit* | OUI | Indice visuel du premier produit de la commande. |
| | *Poids de la commande* | OUI (pour les biens physiques) | Affiche le poids total de la commande pour l'expédition. |
| | *Extrait du fil de discussion du service client* | OUI | Fournit un contexte sur les communications client récentes. |
| | *ISO de la devise* | OUI (pour les multi-devises) | Affiche le code de la devise pour les boutiques internationales. |
| | *Règles de panier appliquées* | OUI | Indique si des réductions ont été utilisées sur la commande. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré les colonnes, mais je ne vois pas les changements sur la page Commandes.**
R :

1.  **Vider le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" en haut à droite. Parfois, PrestaShop met en cache les configurations des modules.
2.  **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou d'ouvrir le Back Office dans une fenêtre de navigation privée pour vous assurer que vous ne voyez pas une ancienne version mise en cache de la page.
3.  **Enregistrer la configuration :** Vérifiez que vous avez bien cliqué sur le bouton "Enregistrer" ou "Mettre à jour" sur la page de configuration du module après avoir effectué vos modifications.

**Q : Certaines colonnes que j'ai activées sont vides ou affichent "N/A". Pourquoi ?**
R : Cela signifie généralement que les données pour cette colonne spécifique ne sont pas disponibles pour cette commande particulière. Par exemple :

-   "Numéro de suivi" sera vide si aucun numéro de suivi n'a été ajouté à la commande.
-   "Extrait du fil de discussion du service client" sera vide s'il n'y a pas de messages du service client pour cette commande.
-   "Poids de la commande" peut être vide si les poids des produits ne sont pas définis ou si la commande ne contient que des produits virtuels.
    C'est un comportement normal et indique des données manquantes plutôt qu'une erreur du module.

**Q : Le glisser-déposer pour réorganiser les colonnes ne fonctionne pas.**
R :

1.  **Conflit JavaScript :** Un autre module ou votre thème pourrait avoir un conflit JavaScript. Essayez de désactiver d'autres modules récemment installés un par un pour identifier le coupable.
2.  **Problème de navigateur :** Testez dans un navigateur différent (Chrome, Firefox, Edge) pour exclure un problème spécifique au navigateur.
3.  **Vider le cache :** Videz le cache de PrestaShop et du navigateur comme décrit ci-dessus.

**Q : Ce module va-t-il ralentir mon Back Office ?**
R : Le module est conçu pour utiliser les hooks officiels de la grille PrestaShop et éviter les surcharges du cœur, ce qui aide à maintenir les performances et la compatibilité. Bien que l'ajout de nombreuses nouvelles colonnes nécessite que PrestaShop récupère plus de données, l'impact est généralement minimal. Si vous remarquez des ralentissements significatifs, envisagez de réduire le nombre de colonnes personnalisées très complexes que vous avez activées.

**Q : Ce module est-il compatible avec mon thème personnalisé ?**
R : Oui, ce module fonctionne dans le Back Office de PrestaShop, qui utilise son propre thème par défaut (New Classic ou similaire). Il n'affecte pas votre thème de front-office, il ne devrait donc pas y avoir de problèmes de compatibilité avec les thèmes de front-office personnalisés.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "Order Grid Pro" étend la fonctionnalité de la liste des commandes du Back Office PrestaShop, ciblant spécifiquement le système de grille Symfony introduit dans PrestaShop 1.7.7+. Il adhère aux meilleures pratiques de développement de modules PrestaShop en utilisant des hooks officiels (`actionGet` et `actionSet` pour les définitions de grille) plutôt que des surcharges directes du cœur. Cela garantit la compatibilité des mises à niveau et la stabilité. Le module injecte principalement de nouvelles définitions de colonnes et des fournisseurs de données dans la grille de commandes existante, et stocke les préférences de l'utilisateur pour la visibilité et l'ordre des colonnes en utilisant la configuration standard de PrestaShop. Les appels AJAX gèrent les mises à jour dynamiques de ces préférences.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Ce module est purement Back-Office.
-   **Contrôleurs Admin Back-Office** :

    -   `controllers/admin/AdminMyordergridproAjaxController.php`
        -   **Nom de la classe et classe parente** : `AdminMyordergridproAjaxController` étend `ModuleAdminController`.
        -   **Responsabilité** : Ce contrôleur est responsable de la gestion des requêtes AJAX depuis la page de configuration du module. Il traite les requêtes pour enregistrer et charger la configuration personnalisée de la grille de commandes (visibilité et ordre des colonnes). Il reçoit généralement des données JSON représentant la mise en page de grille souhaitée et les stocke dans `Configuration::updateValue()`.
        -   **Routes** : Répond aux appels AJAX effectués vers `index.php?controller=AdminMyordergridproAjax&token=...&ajax=1`.
    -   `controllers/admin/index.php`
        -   **Nom de la classe et classe parente** : Pas une classe, mais un fichier de sécurité.
        -   **Responsabilité** : Il s'agit d'un fichier `index.php` vide standard placé dans les répertoires des contrôleurs pour empêcher la liste des répertoires et l'accès direct, améliorant ainsi la sécurité. Il contient généralement `<?php header('Expires: Mon, 26 Jul 1997 05:00:00 GMT'); header('Last-Modified: '.gmdate('D, d M Y H:i:s').' GMT'); header('Cache-Control: no-store, no-cache, must-revalidate'); header('Cache-Control: post-check=0, pre-check=0', false); header('Pragma: no-cache'); header('Location: ../'); exit;`.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne semble pas définir de classes `ObjectModel` personnalisées ni de tables de base de données. Il fonctionne principalement en étendant les définitions de grille PrestaShop existantes et en stockant les données de configuration dans `ps_configuration`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `views/js/grid_pro.js`

    -   **Portée** : Back-office (page Liste des commandes).
    -   **Description** : Ce script contient probablement la logique principale pour manipuler la grille Symfony de PrestaShop sur la page "Commandes > Commandes". Il serait responsable de :
        -   La lecture de la configuration des colonnes enregistrée depuis `Configuration::get()`.
        -   L'ajout/suppression dynamique de colonnes à la grille en fonction de la configuration.
        -   L'application de l'ordre personnalisé des colonnes.
        -   Potentiellement la gestion des mises à jour en direct ou de la logique de rendu de colonnes spécifiques.
        -   La liaison aux événements de grille de PrestaShop (par exemple, `prestashop.on('grid.loaded', ...)`).
-   `views/js/order_grid_admin.js`

    -   **Portée** : Back-office (page de configuration du module).
    -   **Description** : Ce script est principalement utilisé sur la page de configuration du module (`getContent()`). Il gère l'interface utilisateur pour la sélection et l'ordonnancement des colonnes. Cela inclut :
        -   L'implémentation de la fonctionnalité de glisser-déposer pour la réorganisation des colonnes.
        -   La gestion des listes "Colonnes disponibles" et "Colonnes actives".
        -   La liaison des écouteurs d'événements aux interrupteurs/cases à cocher pour la visibilité des colonnes.
        -   L'exécution d'appels AJAX vers `AdminMyordergridproAjaxController.php` pour enregistrer la configuration mise à jour.
-   `views/js/order_list_live_status.js`

    -   **Portée** : Back-office (page Liste des commandes).
    -   **Description** : Ce script fournit probablement des fonctionnalités pour les mises à jour en direct ou les éléments interactifs directement dans la liste des commandes. Cela pourrait inclure :
        -   Des mises à jour de statut basées sur AJAX pour les commandes sans rafraîchissement de page.
        -   Des info-bulles ou des popovers pour des informations supplémentaires sur des colonnes spécifiques.
        -   Potentiellement l'amélioration des listes déroulantes de changement de statut par défaut ou l'ajout d'actions rapides personnalisées.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `views/css/order_grid_admin.css`
    -   **Portée** : Back-office (page de configuration du module et potentiellement page de liste des commandes).
    -   **Description** : Cette feuille de style fournit le style visuel pour l'interface de configuration du module, garantissant que les éléments de glisser-déposer et les listes de colonnes sont présentés clairement. Elle peut également inclure des ajustements de style mineurs pour les nouvelles colonnes introduites dans la liste de commandes réelle afin d'assurer un alignement et une lisibilité corrects dans le thème du Back Office PrestaShop.
    -   **Sélecteurs de classe CSS clés** : Cible probablement des ID ou des classes spécifiques dans le modèle `getContent()` du module, et potentiellement de nouvelles classes de colonnes injectées dans la grille.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Les informations du module indiquent qu'aucun fichier `.tpl` explicite n'a été trouvé dans `views/templates/`. Cela suggère que l'interface de configuration du module est probablement rendue directement dans la méthode `getContent()` du fichier de module principal (`index.php`) en utilisant PHP pour générer le HTML, ou qu'elle injecte dynamiquement du contenu dans les modèles de grille PrestaShop existants via des hooks.

Si des modèles étaient présents, ils seraient généralement :

-   **Modèles de hook (`views/templates/hook/`)** : Pour le rendu du nouveau contenu de colonne dans les cellules de la grille.
-   **Modèles d'administration (`views/templates/admin/`)** : Pour le formulaire de configuration du module.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée pas de tables SQL personnalisées.
    -   Les paramètres de configuration (par exemple, la chaîne JSON représentant l'ordre et la visibilité des colonnes) sont stockés dans la table `ps_configuration` en utilisant des clés comme `MYORDERGRIDPRO_CONFIG` ou similaire.
-   **Table des hooks enregistrés** :
    Le module s'appuie principalement sur les hooks de la grille Symfony de PrestaShop pour sa fonctionnalité.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionGet` et `actionSet` (pour les définitions de grille) | Lorsque la grille de commandes est définie et rendue dans le Back Office. | Ce sont les hooks principaux utilisés pour injecter de nouvelles définitions de colonnes et des fournisseurs de données dans la grille de commandes PrestaShop existante. `actionGet` permet au module de récupérer la définition de grille actuelle, et `actionSet` lui permet de modifier ou d'ajouter de nouvelles colonnes avant que la grille ne soit rendue. |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` de chaque page du Back Office. | Utilisé pour inclure les ressources CSS et JavaScript (`order_grid_admin.css`, `grid_pro.js`, `order_grid_admin.js`, `order_list_live_status.js`) spécifiquement pour le Back Office, garantissant qu'elles sont chargées lorsque nécessaire. |
| `displayAdminOrderListToolbar` (ou similaire) | Rend le contenu dans la zone de la barre d'outils de la liste des commandes. | Potentiellement utilisé pour ajouter des boutons d'action rapide ou des filtres liés à la fonctionnalité du module. |
| `actionAdminOrdersListingFieldsModifier` (ou similaire) | Modifie les champs/colonnes disponibles dans la requête de liste des commandes. | Permet au module d'ajouter de nouveaux champs à la requête SQL qui récupère les données de commande, permettant l'affichage de données de colonnes personnalisées. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour "Order Grid Pro - colonnes et mise en page de la liste des commandes", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe est dédiée à assurer le fonctionnement parfait de votre module et à vous aider à maximiser l'efficacité de votre boutique PrestaShop.
"""
