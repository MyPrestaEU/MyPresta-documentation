---
title: "Banque Nationale Suisse - taux de change - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Banque Nationale Suisse - taux de change par MyPresta.eu."
sidebar:
  label: "Banque Nationale Suisse - taux de change"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Swiss National Bank - currency exchange rates sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/swiss-national-bank-currency-exchange-rates.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/swiss-national-bank-currency-exchange-rates/)
>
> ---


# Banque Nationale Suisse - taux de change

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la récupération de données externes. Votre environnement d'hébergement doit également prendre en charge les tâches CRON pour les mises à jour automatisées.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » pour accéder à la page des paramètres principaux du module. C'est ici que vous définirez comment le module récupère et applique les taux de change.

#### **1. URL CRON**

-   **Ce que fait ce paramètre :** Il affiche l'URL unique que vous devez configurer comme tâche CRON sur votre serveur web. Lorsque cette URL est accédée, le module récupérera automatiquement les derniers taux de change de la Banque Nationale Suisse et les mettra à jour dans votre boutique PrestaShop.
-   **Effet de la modification de ce paramètre :** Vous ne pouvez pas modifier cette URL directement. Elle est générée par le module.
    *   *Lorsqu'elle est correctement configurée comme tâche CRON :* Vos taux de change seront automatiquement mis à jour à la fréquence que vous définissez (par exemple, quotidiennement, toutes les heures).
    *   *Lorsqu'elle N'EST PAS configurée comme tâche CRON :* Vos taux de change ne seront pas automatiquement mis à jour, et vous devrez déclencher manuellement la mise à jour en visitant cette URL dans votre navigateur, ce qui annule le but de l'automatisation.
-   **Valeur recommandée :** Copiez cette URL et configurez-la comme tâche CRON sur votre serveur d'hébergement.
-   **Scénario / exemple de marchand :** Vous souhaitez que vos taux de change soient mis à jour tous les matins à 3h du matin. Vous copiez cette URL et l'ajoutez au planificateur de tâches CRON de votre panneau de contrôle d'hébergement, configuré pour s'exécuter quotidiennement à 3h du matin.

#### **2. Marge de taux de change (%)**

-   **Ce que fait ce paramètre :** Cela vous permet d'ajouter une marge en pourcentage aux taux de change récupérés auprès de la Banque Nationale Suisse. Cette marge est appliquée en plus du taux de base.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est défini sur 0 (par défaut) :* Les taux de change seront mis à jour exactement tels que fournis par la BNS.
    *   *Lorsqu'il est défini sur une valeur positive (par exemple, 2) :* Le taux de change sera augmenté de ce pourcentage. Par exemple, si le taux de la BNS est de 1 EUR = 1,10 CHF, et que vous définissez une marge de 2 %, votre boutique utilisera 1 EUR = 1,122 CHF (1,10 \* 1,02). Cela signifie que les produits dont le prix est en CHF apparaîtront légèrement plus chers lorsqu'ils seront convertis en EUR.
-   **Valeur recommandée :** Commencez par 0. N'augmentez que si vous devez tenir compte des frais de passerelle de paiement, des coûts de conversion de devises ou pour intégrer une petite marge bénéficiaire dans votre tarification internationale.
-   **Scénario / exemple de marchand :** Votre processeur de paiement facture des frais de 1,5 % pour les conversions de devises internationales. Pour couvrir ce coût, vous définissez la « Marge de taux de change » sur 1,5 %. Cela garantit que vos marges bénéficiaires ne sont pas érodées par les frais de conversion.

#### **3. Bouton Enregistrer**

-   **Ce que fait ce paramètre :** Ce bouton enregistre toutes les modifications que vous avez apportées au paramètre « Marge de taux de change ».
-   **Effet de la modification de ce paramètre :** Cliquer sur « Enregistrer » applique votre paramètre de marge. L'URL CRON est statique et ne nécessite pas d'enregistrement.
-   **Valeur recommandée :** Cliquez toujours sur « Enregistrer » après avoir ajusté la marge.
-   **Scénario / exemple de marchand :** Vous avez décidé d'ajouter une marge de 1 %. Après avoir tapé « 1 » dans le champ de marge, vous cliquez sur « Enregistrer » pour vous assurer que ce paramètre est appliqué pour les futures mises à jour de taux.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | URL CRON | Générée par le module | URL à configurer comme tâche CRON pour les mises à jour automatiques des taux de change. |
| Page de configuration du module | Marge de taux de change (%) | 0 | Ajoute un pourcentage aux taux de change récupérés pour couvrir les frais ou ajouter une marge. |
| Page de configuration du module | Bouton Enregistrer | N/A | Enregistre les modifications apportées à la marge de taux de change. |

## 3. Comment le module utilise la devise de base (CHF)

Le module « Banque Nationale Suisse - taux de change » utilise le Franc Suisse (CHF) comme devise de base pour toutes ses opérations de récupération et de calcul des taux de change. Voici comment cela fonctionne :

1.  **Récupération des données :** Le module se connecte à l'API de la Banque Nationale Suisse (SNB) pour obtenir les taux de change. La SNB fournit généralement les taux par rapport au CHF. Par exemple, elle peut indiquer que 1 EUR = X CHF, 1 USD = Y CHF, etc.
2.  **Calcul des taux de conversion :**
    *   Pour chaque devise active dans votre boutique (sauf le CHF), le module calcule le taux de conversion nécessaire pour PrestaShop.
    *   Si votre devise par défaut dans PrestaShop est le CHF, le taux de conversion pour les autres devises sera directement le taux fourni par la SNB (par exemple, si 1 EUR = 1.10 CHF, alors le taux de conversion pour EUR sera 1.10).
    *   Si votre devise par défaut dans PrestaShop N'EST PAS le CHF (par exemple, EUR), le module effectuera un calcul croisé. Par exemple, si 1 EUR = 1.10 CHF et 1 USD = 0.95 CHF, alors pour convertir de l'EUR à l'USD, il calculera (1.10 CHF / 0.95 CHF) = 1.15789 USD pour 1 EUR.
3.  **Application de la marge :** Si vous avez configuré une « Marge de taux de change (%) », cette marge est appliquée aux taux de conversion calculés avant qu'ils ne soient enregistrés dans votre base de données PrestaShop.
4.  **Mise à jour de la base de données :** Le module met à jour la colonne `conversion_rate` de la table `ps_currency` de PrestaShop pour toutes les devises actives, en utilisant les taux calculés et margés.

**Implications pour votre boutique :**

-   **Précision :** En utilisant une source officielle comme la BNS, vous garantissez la précision des taux.
-   **Flexibilité :** Le module gère les calculs complexes pour s'assurer que les taux sont corrects, quelle que soit la devise de base de votre boutique PrestaShop, tant que le CHF est une devise active et que la BNS fournit des taux pour les devises que vous utilisez.
-   **Nécessité du CHF :** Pour que le module fonctionne correctement, le Franc Suisse (CHF) doit être une devise active dans votre boutique PrestaShop, car c'est la devise de référence utilisée par la BNS.

En résumé, le module « Banque Nationale Suisse - taux de change » est un module PrestaShop qui met à jour automatiquement les taux de change dans votre boutique en récupérant les données de la Banque Nationale Suisse (BNS). Il utilise le Franc Suisse (CHF) comme devise de base pour les calculs et vous permet d'ajouter une marge personnalisée aux taux. Les mises à jour sont entièrement automatisées via une tâche CRON.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module suit une architecture de module PrestaShop minimaliste. Sa fonction principale est de récupérer périodiquement les taux de change d'une API externe (Banque Nationale Suisse) et de mettre à jour la table `currency` dans la base de données PrestaShop. La logique principale réside dans le fichier principal du module (`snbrates/cronjob.php`) et est déclenchée par un contrôleur frontal, conçu pour être appelé par une tâche CRON. Il utilise la classe `Configuration` de PrestaShop pour stocker les paramètres et l'ObjectModel `Currency` pour mettre à jour les taux.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Ces contrôleurs sont conçus pour être accessibles en externe, principalement par les tâches CRON.

    -   `controllers/front/cronjob.php`

        -   **Nom de la classe et classe parente :** `SnbratesCronjobModuleFrontController` étend `ModuleFrontController`.
        -   **Responsabilité :** C'est le point d'entrée principal pour la mise à jour automatique des taux. Lorsque l'URL de ce contrôleur est accédée (par exemple, `votreboutique.com/module/snbrates/cronjob`), il exécute la logique pour :
            1.  Récupérer les derniers taux de change depuis le point d'API SNB configuré.
            2.  Appliquer la marge configurée (le cas échéant).
            3.  Mettre à jour le `conversion_rate` pour chaque devise active dans la base de données PrestaShop, en utilisant le CHF comme base.
            4.  Il ne rend aucune sortie visuelle au navigateur, renvoyant généralement un simple message de succès/échec ou une redirection.
    -   `controllers/front/index.php`

        -   **Nom de la classe et classe parente :** `SnbratesIndexModuleFrontController` étend `ModuleFrontController`.
        -   **Responsabilité :** C'est un contrôleur de remplacement, souvent inclus dans les modules mais non directement utilisé pour la fonctionnalité principale de ce module spécifique. Il peut être utilisé pour de simples redirections ou pour empêcher l'affichage du répertoire s'il est accédé directement, mais il ne contient pas de logique métier spécifique pour les mises à jour de taux.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le module n'introduit aucune classe ou ObjectModel personnalisé dans le répertoire `classes/`. Il utilise directement l'ObjectModel `Currency` de PrestaShop pour gérer les données de devise et `Configuration` pour les paramètres du module.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun. Le module n'utilise aucun JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun. Le module n'utilise aucun CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `views/admin.tpl`
        -   **Objectif :** Ce modèle est rendu par la méthode `getContent()` du fichier principal du module (`snbrates/cronjob.php`) pour afficher le formulaire de configuration du module dans le Back Office de PrestaShop.
        -   **Contenu :** Il inclut généralement les champs de formulaire pour l'« URL CRON » (affichage uniquement) et la « Marge de taux de change (%) » (champ de saisie), ainsi que le bouton « Enregistrer ». Il utilise les fonctions d'aide standard de PrestaShop pour le rendu des formulaires.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table de base de données personnalisée.
    -   Il interagit avec la table `ps_currency` de PrestaShop, en mettant spécifiquement à jour la colonne `conversion_rate` pour les devises actives.
    -   Il stocke ses paramètres de configuration (par exemple, `SNBRATES_MARGIN`) dans la table `ps_configuration`.
-   **Table des hooks enregistrés** :
    Le module n'enregistre explicitement aucun hook d'affichage front-office (comme `displayHeader`, `displayRightColumn`, `displayFooter`, `displayProductButtons`, etc.) car sa fonction principale est le traitement des données en arrière-plan. Les « Hooks Front-Office : En-tête, Colonnes, Produit ou Pied de page » mentionnés dans l'invite peuvent faire référence à une capacité générale ou à une incompréhension, car la fonction principale du module n'implique pas le rendu de contenu dans ces zones.

    Le module utilise implicitement les éléments suivants :

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `actionModuleInstall` | Lors de l'installation du module | Définit les valeurs de configuration par défaut. |
    | `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie les valeurs de configuration. |
    | (Interne) `ModuleFrontController` dispatch | Lorsque l'URL CRON est accédée | Déclenche la logique de mise à jour des taux. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour vous assurer que vous utilisez la dernière version compatible du module « Banque Nationale Suisse - taux de change », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
