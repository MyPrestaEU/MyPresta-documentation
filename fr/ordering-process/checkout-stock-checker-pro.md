---
title: "Checkout stock checker PRO - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Checkout stock checker PRO par MyPresta.eu."
sidebar:
  label: "Checkout stock checker PRO"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Checkout stock checker PRO sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/checkout-stock-checker-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/checkout-stock-checker-pro/)
>
> ---


# Checkout stock checker PRO

## 1. Exigences et compatibilité

-   **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 5.6 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquer sur "Configurer" vous mènera à l'écran de configuration principal et unique du module "Checkout stock checker PRO". Cet écran vous permet d'activer ou de désactiver la fonctionnalité principale du module.

#### **Activer / Désactiver le module**
-   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité de vérification de stock.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* Le module vérifiera activement les niveaux de stock des produits juste avant qu'une commande ne soit passée. Si un article est en rupture de stock, le client sera redirigé vers le panier avec une notification.
    -   *Lorsqu'il est désactivé (NON) :* Le module sera inactif. Les vérifications de stock n'auront pas lieu, et les clients pourraient être en mesure de passer des commandes pour des articles en rupture de stock, en se fiant uniquement au comportement de gestion de stock par défaut de PrestaShop (qui ne vérifie généralement qu'au moment de l'ajout au panier, pas à la finalisation de la commande).
-   **Valeur recommandée :** **OUI**. Pour profiter pleinement de l'objectif du module, il doit toujours être activé.
-   **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez commencer à empêcher les commandes en rupture de stock. Vous le réglerez sur "OUI". Si vous devez temporairement désactiver la fonction pour la maintenance ou les tests, vous le réglerez sur "NON".

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Page de configuration du module | Activer / Désactiver le module | OUI | Contrôle si le module vérifie activement le stock avant le placement de la commande. Empêche les commandes d'articles en rupture de stock lorsqu'il est activé. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le module est activé, mais les clients passent toujours des commandes pour des articles en rupture de stock. Quel est le problème ?**
R :
1.  **Vider le cache :** Tout d'abord, essayez de vider le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" en haut à droite.
2.  **Vérifier l'état du module :** Vérifiez à nouveau que le module est bien activé dans sa page de configuration.
3.  **Conflits de thème :** Certains thèmes très personnalisés ou d'autres modules modifiant le processus de paiement peuvent interférer. Passez temporairement au thème PrestaShop par défaut (Classic) et testez à nouveau. Si cela fonctionne, le problème est probablement un conflit de thème, et vous devrez peut-être faire appel à un développeur pour enquêter.
4.  **Version de PrestaShop :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre installation PrestaShop spécifique.

**Q : Mes clients sont redirigés vers le panier, mais le message de notification n'apparaît pas ou est mal stylisé.**
R :
1.  **Vider le cache :** Comme toujours, videz le cache de votre PrestaShop.
2.  **Style du thème :** Le message de notification utilise les classes d'alerte standard de PrestaShop. Si votre thème a fortement personnalisé ou supprimé ces styles, le message pourrait être invisible ou mal formaté. Un webmaster peut inspecter le HTML et le CSS pour s'assurer que le message est présent et stylisé correctement.
3.  **Fichiers du module :** Assurez-vous que tous les fichiers du module ont été téléchargés correctement. Parfois, des téléchargements incomplets peuvent entraîner l'absence de fichiers de modèle pour les notifications.

**Q : Ce module fonctionne-t-il avec les boutiques multilingues ?**
R : Oui, le module utilise les mécanismes de traduction standard de PrestaShop. Les messages de notification affichés aux clients peuvent être traduits dans toutes les langues configurées dans votre boutique. Vous pouvez gérer ces traductions sous **International > Traductions > Traductions des modules installés**.

**Q : Ce module va-t-il ralentir mon processus de paiement ?**
R : La vérification de stock effectuée par le module est très rapide, ajoutant généralement seulement quelques millisecondes au processus de paiement. Il s'agit d'une requête de base de données directe pour les niveaux de stock, qui est hautement optimisée. L'impact sur les performances est négligeable et largement compensé par les avantages d'éviter les commandes en rupture de stock.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)
Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture
Le module "Checkout stock checker PRO" (`csc`) est conçu pour s'intégrer de manière transparente dans le flux de paiement de PrestaShop. Il fonctionne principalement en s'accrochant à l'étape finale du processus de commande, en utilisant un contrôleur frontal pour effectuer une vérification de stock basée sur AJAX. Cette approche garantit que la vérification de stock est effectuée en temps réel juste avant que la commande ne soit validée dans la base de données, évitant ainsi les conditions de concurrence où le stock pourrait changer entre la révision du panier et la confirmation finale de la commande. Le module adhère au modèle MVC de PrestaShop pour son interaction front-end et sa configuration.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office
-   `csc/controllers/front/AjaxCheck.php`
    *   **Nom de la classe et classe parente :** `CscAjaxCheckModuleFrontController` étendant `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur est le cœur de la fonctionnalité du module. Il est responsable de la gestion de la requête AJAX initiée depuis la page de paiement du front-office. Lors de la réception de la requête, il parcourt les produits du panier du client, vérifie leurs niveaux de stock actuels par rapport aux quantités demandées et renvoie une réponse JSON indiquant si tous les articles sont en stock ou quels articles sont en rupture de stock. Il ne rend pas une page complète mais fournit des données pour que le JavaScript puisse agir.
-   `csc/controllers/front/index.php`
    *   **Nom de la classe et classe parente :** Il s'agit d'un fichier `index.php` vide standard, généralement inclus dans les répertoires de modules PrestaShop pour empêcher la liste directe des répertoires. Il ne contient pas de classe ou de logique spécifique.

#### Contrôleurs d'administration Back-Office
Le module n'utilise aucun contrôleur d'administration personnalisé. Sa configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)
Le module ne définit aucune classe `ObjectModel` personnalisée ni de classes de logique métier dédiées dans le répertoire `classes/`. Toute la logique principale est encapsulée dans le fichier principal du module (`ajax_csc.php`) et le contrôleur frontal `AjaxCheck`.

### 4.4 Actifs JavaScript (`views/js/`)
-   `csc/views/js/csc.js`
    *   **Portée :** Front-office.
    *   **Détails :** Ce fichier JavaScript est responsable de l'initialisation de la vérification de stock AJAX. Il s'accroche généralement à l'événement de clic du bouton final "Passer la commande" (ou à la soumission de formulaire équivalente) sur la page de paiement. Avant de permettre la soumission du formulaire, il envoie une requête AJAX au contrôleur frontal `AjaxCheck`. En fonction de la réponse JSON, il permet soit la finalisation du paiement, soit empêche la soumission, redirige l'utilisateur vers le panier et affiche le message d'erreur approprié. Il utilise jQuery standard ou les événements JavaScript natifs de PrestaShop (`prestashop.on`) pour y parvenir.

### 4.5 Feuilles de style CSS (`views/css/`)
-   `csc/views/css/csc.css`
    *   **Portée :** Style client du front-office.
    *   **Détails :** Cette feuille de style fournit un style de base pour les messages de notification affichés sur la page du panier lorsque des produits sont en rupture de stock. Elle cible probablement des classes CSS spécifiques ajoutées aux éléments `div` de notification.
    *   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Les développeurs peuvent inspecter la sortie HTML du message de notification pour identifier les classes spécifiques (par exemple, `.alert-danger`, `.csc-notification`, etc.) et les surcharger dans le fichier `custom.css` ou `theme.css` de leur thème pour correspondre à l'image de marque de leur boutique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** : Aucun explicitement listé, ce qui suggère que l'interaction principale du module se fait via AJAX et la redirection, avec des notifications rendues directement par le contrôleur `AjaxCheck` ou le module principal.
-   **Modèles d'administration (`views/templates/admin/`)** : Aucun, car la configuration est gérée par `getContent()`.
-   **Modèles Front-office (`views/templates/front/`)** :
    *   `csc/lib/searchTool/views/scripts.tpl`
        *   **Objectif :** Ce modèle inclut probablement le fichier JavaScript `csc.js` et transmet potentiellement des variables de configuration du back-end du module au JavaScript du front-end. Il est probablement accroché à `displayHeader` ou `displayFooter` pour s'assurer que le JS est chargé sur les pages pertinentes (par exemple, le paiement).
    *   `csc/views/errors.tpl`
        *   **Objectif :** Ce modèle est rendu lorsque la vérification de stock échoue (c'est-à-dire que des articles sont en rupture de stock). Il affiche le message d'erreur et liste les produits spécifiques qui ne sont plus disponibles. C'est le modèle responsable de la notification visible sur la page du panier après la redirection.
    *   `csc/views/no-errors.tpl`
        *   **Objectif :** Ce modèle est probablement un espace réservé ou un modèle qui serait rendu s'il n'y avait pas d'erreurs, mais la fonction principale du module est d'afficher les erreurs. Il peut être utilisé pour la logique interne ou simplement être un modèle vide.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Le module ne crée aucune table de base de données personnalisée. Il s'appuie entièrement sur les tables existantes de PrestaShop `ps_product`, `ps_stock_available` et `ps_configuration`. Les paramètres de configuration (comme l'interrupteur d'activation/désactivation) sont stockés dans `ps_configuration` à l'aide de clés comme `CSC_ENABLED`.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Rend le contenu dans la section `<head>` de chaque page. | Probablement utilisé pour inclure le script `csc.js` et la feuille de style `csc.css`, garantissant qu'ils sont disponibles sur les pages de paiement. |
| `displayFooter` | Rend le contenu à la fin de la section `<body>` de chaque page. | Hook alternatif à `displayHeader` pour inclure JS/CSS, souvent préféré pour les performances. |
| `displayProductButtons` | Rend le contenu près des boutons de produit (par exemple, ajouter au panier). | *Non explicitement utilisé pour la fonctionnalité principale, mais pourrait l'être pour des fonctionnalités futures ou des éléments d'interface utilisateur mineurs.* |
| `displayRightColumn` | Rend le contenu dans la colonne de droite de la boutique. | *Non explicitement utilisé pour la fonctionnalité principale, mais pourrait l'être pour des fonctionnalités futures ou des éléments d'interface utilisateur mineurs.* |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (JS/CSS). | Un hook plus ciblé pour ajouter JS/CSS spécifiquement aux contrôleurs frontaux pertinents (par exemple, les pages de paiement). |
| `actionBeforeUpdateQuantity` | Exécuté avant la mise à jour d'une quantité de produit dans le panier. | *Non explicitement utilisé pour la fonctionnalité principale, mais pourrait l'être pour des fonctionnalités futures ou des éléments d'interface utilisateur mineurs.* |
| `actionCartSave` | Exécuté après l'enregistrement d'un panier. | *Non explicitement utilisé pour la fonctionnalité principale, mais pourrait l'être pour des fonctionnalités futures ou des éléments d'interface utilisateur mineurs.* |
| `actionValidateOrder` | Exécuté après la validation d'une commande. | *Crucial pour la logique du module.* C'est le point où le module intervient pour effectuer la vérification finale du stock *avant* que la commande ne soit entièrement validée. Le JavaScript du module empêche probablement la soumission du formulaire qui déclenche ce hook si des problèmes de stock sont détectés. |

*Note : Le mécanisme principal de vérification de stock du module passe par son contrôleur frontal `AjaxCheck`, qui est déclenché par JavaScript sur la page de paiement, plutôt que de s'appuyer uniquement sur les hooks natifs de PrestaShop pour la vérification de stock elle-même. Les hooks sont principalement utilisés pour charger des actifs et potentiellement pour afficher des notifications.*

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Checkout stock checker PRO", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
