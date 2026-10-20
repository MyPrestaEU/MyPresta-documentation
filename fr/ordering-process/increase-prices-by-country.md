---
title: "Augmenter les prix par pays - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Augmenter les prix par pays par MyPresta.eu."
sidebar:
  label: "Augmenter les prix par pays - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Increase prices by country sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/increase-prices-by-country.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/increase-prices-by-country/)
>
> ---


# Augmenter les prix par pays

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Le module s'appuie sur les fonctionnalités de base de PrestaShop et les configurations de serveur standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module, accessible immédiatement après l'installation ou en cliquant sur « Configurer » depuis le Gestionnaire de modules.

**Paramètres et options détectés : Paramètres de module standard**
Cet écran contient généralement les paramètres généraux du module, tels que l'activation/désactivation du module, ou les préférences globales.

-   **Ce que fait ce paramètre :** Cette section contient généralement un interrupteur global pour activer ou désactiver la fonctionnalité principale du module. Elle peut également inclure des préférences générales qui affectent la manière dont les ajustements de prix sont appliqués dans votre boutique.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé :* Le module ajustera activement les prix en fonction des règles que vous définissez dans la section dédiée « Liste des prix par pays ».
    *   *Lorsqu'il est désactivé :* Le module cessera d'ajuster les prix, et tous les clients verront les prix par défaut de vos produits, quel que soit leur pays.
-   **Valeur recommandée :** « OUI » (Activé) si vous avez l'intention d'utiliser le module pour les ajustements de prix.
-   **Scénario / exemple de marchand :** Si vous configurez le module pour la première fois, vous voudrez l'activer ici. Si vous devez suspendre temporairement tous les ajustements de prix spécifiques à un pays sans supprimer vos règles, vous pouvez le désactiver ici.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminPbcListController (Back Office > Augmenter les prix par pays > Liste des prix par pays)

C'est l'écran de gestion principal où vous définissez et gérez vos règles d'ajustement de prix spécifiques à chaque pays.

-   **Nom de l'écran et emplacement du menu :** Vous trouverez un nouvel élément de menu dans votre Back Office PrestaShop, généralement sous une section comme « Catalogue » ou « International », nommé **« Augmenter les prix par pays »** ou similaire, puis un sous-élément de menu comme **« Liste des prix par pays »**.
-   **Actions et paramètres disponibles :**
    *   **Ajouter une nouvelle règle :** Un bouton pour créer une nouvelle règle d'ajustement de prix.
    *   **Liste des règles :** Un tableau affichant toutes les règles existantes, montrant des détails tels que :
        *   **Pays :** Le pays cible de la règle.
        *   **Type d'ajustement :** S'il s'agit d'un pourcentage ou d'un montant fixe.
        *   **Valeur :** Le pourcentage ou le montant à augmenter/diminuer.
        *   **Action :** Options pour « Modifier » ou « Supprimer » les règles individuelles.
    *   **Champs de formulaire pour ajouter/modifier une règle :**
        *   **Sélecteur de pays :** Une liste déroulante ou un champ de recherche pour sélectionner le pays spécifique auquel cette règle s'applique.
            *   *Effet :* Les prix seront ajustés uniquement pour les clients identifiés comme étant dans ce pays.
            *   *Recommandé :* Sélectionnez le pays spécifique que vous souhaitez cibler.
            *   *Scénario :* Vous souhaitez augmenter les prix pour les clients aux États-Unis.
        *   **Type d'ajustement (Pourcentage / Montant) :** Un bouton radio ou une liste déroulante pour choisir comment le prix sera ajusté.
            *   *Effet :*
                *   *Pourcentage :* Le prix sera augmenté ou diminué d'un pourcentage de sa valeur originale.
                *   *Montant :* Le prix sera augmenté ou diminué d'une valeur monétaire fixe (dans la devise par défaut de votre boutique).
            *   *Recommandé :* Choisissez en fonction de votre stratégie de prix. Le pourcentage est bon pour des majorations cohérentes, le montant pour des surtaxes/réductions fixes.
            *   *Scénario :* Vous souhaitez ajouter une majoration de 10 % (Pourcentage) ou une surtaxe fixe de 5 $ (Montant).
        *   **Valeur :** Un champ de saisie pour entrer le pourcentage (par exemple, « 10 » pour 10 %) ou le montant fixe (par exemple, « 5.00 » pour 5 $).
            *   *Effet :*
                *   *Valeur positive :* Augmente le prix.
                *   *Valeur négative :* Diminue le prix (par exemple, « -5 » pour une réduction de 5 % ou « -2.50 » pour une réduction de 2,50 $).
            *   *Recommandé :* Entrez l'ajustement souhaité. Soyez prudent avec les valeurs négatives pour éviter que les prix ne tombent en dessous de zéro.
            *   *Scénario :* Entrez « 15 » pour augmenter de 15 %, ou « -2.50 » pour diminuer de 2,50 $.
-   **Effet des changements :**
    *   L'ajout d'une nouvelle règle active immédiatement l'ajustement de prix pour le pays sélectionné.
    *   La modification d'une règle met à jour l'ajustement pour ce pays.
    *   La suppression d'une règle supprime l'ajustement spécifique au pays, et les clients de ce pays verront les prix par défaut des produits.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Identifiez un pays où vous souhaitez ajuster les prix (par exemple, en raison de coûts d'expédition plus élevés, de la concurrence locale ou d'une promotion spéciale).
    2.  Accédez à l'écran « Liste des prix par pays ».
    3.  Cliquez sur « Ajouter une nouvelle règle ».
    4.  Sélectionnez le pays cible.
    5.  Choisissez d'ajuster par « Pourcentage » ou « Montant ».
    6.  Entrez la valeur positive ou négative pour l'ajustement.
    7.  Enregistrez la règle.
    8.  Testez en utilisant un VPN ou en demandant à quelqu'un de ce pays de vérifier les prix de votre boutique.

#### index.php (pbc/controllers/admin/index.php)

Ce fichier sert probablement de routage ou de marqueur de position pour les contrôleurs d'administration dans le répertoire du module `pbc`. Il ne représente pas un écran distinct et configurable, mais assure plutôt un accès et un chargement corrects des autres contrôleurs d'administration comme `AdminPbcListController`. Les marchands n'interagiront pas directement avec ce fichier.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Module activé/désactivé | Activé | Interrupteur global pour activer ou désactiver tous les ajustements de prix spécifiques à un pays. |
| **Liste des prix par pays** | Ajouter/Modifier une règle : Pays | N/A (sélectionner spécifique) | Définit le pays cible pour l'ajustement des prix. |
| | Ajouter/Modifier une règle : Type d'ajustement | Pourcentage | Choisit si le prix change par pourcentage ou par montant fixe. |
| | Ajouter/Modifier une règle : Valeur | 0 (entrer la valeur souhaitée) | Le pourcentage ou le montant positif (augmentation) ou négatif (diminution). |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes prix ne changent pas pour un pays spécifique, même après avoir configuré une règle.**
R :

1.  **Le module est-il activé globalement ?** Vérifiez la page de configuration principale du module (Modules > Gestionnaire de modules > Configurer « Augmenter les prix par pays ») pour vous assurer que le module est actif.
2.  **La règle est-elle correctement configurée ?** Allez dans « Liste des prix par pays » et vérifiez que le pays est correctement sélectionné, que le type d'ajustement (pourcentage/montant) est correct et que la valeur est saisie correctement (positive pour une augmentation, négative pour une diminution).
3.  **Vider le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » si disponible). Cela résout souvent les problèmes d'affichage.
4.  **Problèmes de géolocalisation :** Le module s'appuie sur la fonction de géolocalisation de PrestaShop. Assurez-vous que la géolocalisation de votre boutique PrestaShop est correctement configurée (Paramètres avancés > Géolocalisation). Si vous testez depuis votre propre pays, essayez d'utiliser un VPN pour simuler une visite depuis le pays cible.

**Q : Ce module affectera-t-il mon SEO ou mes flux de produits ?**
R : Le module ajuste dynamiquement les prix sur le front-office en fonction de l'adresse IP du visiteur. Il ne modifie pas le prix de base de votre produit dans la base de données. Par conséquent, il ne devrait généralement pas avoir d'impact direct sur votre SEO (les moteurs de recherche explorent généralement à partir d'un emplacement par défaut ou utilisent vos prix de base) ou sur les flux de produits (qui extraient généralement les prix de base). Cependant, si vous utilisez un service tiers qui explore votre site à partir de différents emplacements, il pourrait voir les prix ajustés.

**Q : Que se passe-t-il si un client d'un pays avec un ajustement de prix ajoute un produit au panier, puis change de pays (par exemple, via l'adresse de livraison) ?**
R : Le module ajuste les prix en fonction du *pays détecté du client* au moment de la navigation. Si le pays du client change (par exemple, il se connecte et son adresse est dans un pays différent, ou il sélectionne explicitement un pays de livraison différent lors de la commande), la logique de base de PrestaShop pour le calcul des prix (que ce module remplace) devrait réévaluer le prix. La surcharge du module garantit que le prix correct pour le *pays final* est appliqué.

**Q : Puis-je appliquer des règles différentes pour différents groupes de clients au sein du même pays ?**
R : Non, ce module ajuste les prix *uniquement en fonction du pays* déterminé par la géolocalisation. Il n'offre pas d'options pour différencier les prix en fonction des groupes de clients (par exemple, grossiste vs. détaillant) au sein d'un même pays. Pour une tarification spécifique aux groupes de clients, vous auriez besoin d'un module séparé ou des règles de prix intégrées de PrestaShop.

**Q : J'ai défini une augmentation de montant, mais elle semble différente dans d'autres devises.**
R : Lorsque vous définissez une augmentation de montant (par exemple, +5 $), le module applique ce montant dans la *devise par défaut* de votre boutique. Il convertit ensuite automatiquement ce montant supplémentaire dans d'autres devises en fonction des taux de change configurés de votre boutique. Cela garantit que la *valeur* de l'augmentation reste cohérente entre les devises. Assurez-vous que vos taux de change sont à jour dans PrestaShop (International > Devises).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Augmenter les prix par pays » (`pbc`) fonctionne principalement en surchargeant la classe `Product` de PrestaShop pour injecter des ajustements de prix spécifiques au pays lors du calcul des prix. Il utilise les fonctionnalités de géolocalisation de PrestaShop pour identifier le pays du client et applique les règles définies dans une table de base de données personnalisée. Le module suit un modèle MVC PrestaShop standard pour sa gestion Back Office, avec un contrôleur d'administration dédié à la gestion des règles de prix.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun explicitement défini dans l'archive du module. Les ajustements de prix sont gérés via la surcharge de `Product.php`, qui s'accroche à la logique de calcul des prix de base de PrestaShop.
-   **Contrôleurs d'administration Back-Office** :
    *   `pbc/controllers/admin/AdminPbcListController.php`
        *   **Nom de la classe** : `AdminPbcListController` (étend `ModuleAdminController`)
        *   **Responsabilité** : Gère les opérations CRUD pour l'entité `pricebc` (Prix par Pays). Ce contrôleur affiche la liste des règles d'ajustement de prix définies, gère l'ajout de nouvelles règles, la modification des règles existantes et leur suppression. Il utilise `HelperList` et `HelperForm` de PrestaShop pour le rendu de la liste et des formulaires d'ajout/modification, respectivement.
        *   **Nom de l'onglet** : Généralement enregistré sous un onglet personnalisé dans la navigation du Back Office, accessible via l'entrée de menu principale du module.
    *   `pbc/controllers/admin/index.php`
        *   **Nom de la classe** : N/A (il s'agit d'un fichier de substitution)
        *   **Responsabilité** : Ce fichier est une pratique courante dans le développement de modules PrestaShop pour empêcher la liste directe des répertoires et assurer un routage correct dans le répertoire `controllers/admin`. Il ne contient pas de logique exécutable pour un contrôleur spécifique.

### 4.3 Classes et modèles de base (`classes/`)

-   `pbc/classes/index.php`
    *   **Nom de la classe** : N/A
    *   **Responsabilité** : Fichier de substitution pour empêcher la liste des répertoires.
-   `pbc/classes/pricebc.php`
    *   **Nom de la classe** : `PriceBc` (étend `ObjectModel`)
    *   **Table de base de données** : `_pbc` (par exemple, `ps_pbc`)
    *   **Champs `$definition`** :
        *   `id_pbc` : Clé primaire.
        *   `id_country` : Clé étrangère vers la table `ps_country`, identifiant le pays cible.
        *   `type` : Entier, généralement 0 pour le pourcentage, 1 pour le montant.
        *   `value` : Décimal, le pourcentage ou le montant à ajuster. Peut être positif ou négatif.
    *   **Méthodes publiques clés** : Méthodes `ObjectModel` standard pour les opérations CRUD. Peut inclure des méthodes statiques pour récupérer des règles basées sur l'ID du pays.
-   `pbc/override/classes/index.php`
    *   **Nom de la classe** : N/A
    *   **Responsabilité** : Fichier de substitution pour empêcher la liste des répertoires dans le répertoire de surcharge.
-   `pbc/override/classes/Product.php`
    *   **Nom de la classe** : `Product` (étend la classe `Product` de base de PrestaShop)
    *   **Responsabilité** : C'est la partie la plus critique du module. Elle surcharge la méthode `getPriceStatic()` (ou des méthodes de calcul de prix similaires) de la classe `Product` de base.
        *   Elle récupère le pays actuel du client (via la géolocalisation ou le contexte).
        *   Elle interroge le modèle `PriceBc` pour trouver les règles d'ajustement de prix actives pour ce pays.
        *   Elle applique ensuite l'ajustement en pourcentage ou en montant au prix de base du produit avant de retourner le prix final calculé.
        *   Gère la conversion de devise pour les ajustements basés sur le montant.
    *   **Note du développeur** : Tout autre module qui surcharge également `Product.php` pourrait entraîner des conflits. Des tests minutieux sont nécessaires. La surcharge du module doit être conçue pour être compatible avec d'autres surcharges ou pour permettre le chaînage.

### 4.4 Actifs JavaScript (`views/js/`)

-   `pbc/views/admin/script.js`
    *   **Portée** : Back-office (formulaires `AdminPbcListController`).
    *   **Fonctionnalité** : Gère probablement le comportement dynamique sur le formulaire « Ajouter/Modifier une règle de prix ». Cela pourrait inclure :
        *   Afficher/masquer des champs en fonction du « Type d'ajustement » sélectionné (par exemple, si « Pourcentage » est sélectionné, s'assurer que le champ de valeur est traité comme un pourcentage).
        *   Validation ou formatage des entrées.
        *   Appels AJAX pour la sélection de pays ou d'autres éléments de formulaire dynamiques.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'a été détecté dans l'inventaire fourni. Le module s'appuie probablement sur le style par défaut du Back Office de PrestaShop pour ses formulaires et listes de configuration, et n'introduit aucun élément visuel front-office nécessitant un style personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    *   `pbc/views/displayHeader.tpl`
        *   **Hook** : `displayHeader`
        *   **Objectif** : Ce modèle est probablement utilisé pour inclure les fichiers JavaScript ou CSS nécessaires (s'il y en avait) ou pour initialiser les scripts front-office qui doivent s'exécuter tôt lors du chargement de la page. Compte tenu de la nature du module, il pourrait également contenir une logique pour détecter le pays de l'utilisateur ou définir une variable JS globale pour le débogage.
-   **Modèles d'administration (`views/templates/admin/`)** :
    *   `pbc/lib/searchTool/views/scripts.tpl`
        *   **Objectif** : Ce modèle fait probablement partie d'un composant ou d'une bibliothèque réutilisable au sein du module, éventuellement pour un outil de recherche ou de filtrage utilisé dans l'`AdminPbcListController`. Il contiendrait une logique JavaScript ou Smarty liée à cet outil.
-   **Modèles Front-office (`views/templates/front/`)** :
    *   `pbc/views/script.tpl`
        *   **Objectif** : Similaire à `displayHeader.tpl`, ce modèle pourrait être utilisé pour intégrer du JavaScript directement dans le front-office, potentiellement pour une logique côté client liée à l'affichage des prix (bien que la logique principale soit côté serveur via la surcharge de `Product`). Il pourrait également s'agir d'un point d'inclusion de script de secours ou plus générique.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   `ps_pbc` : Stocke les règles d'ajustement des prix.
        *   `id_pbc` (INT, PK, AUTO\_INCREMENT)
        *   `id_country` (INT, FK vers `ps_country.id_country`)
        *   `type` (TINYINT, 0 pour pourcentage, 1 pour montant)
        *   `value` (DECIMAL(20,6), signé, la valeur d'ajustement)
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page front-office. | Pour inclure les actifs JS/CSS du module ou initialiser les scripts front-end. |
| `actionProductPriceCalculation` | (Implicite via la surcharge de `Product.php`) | La fonctionnalité principale du module est implémentée en surchargeant la méthode `Product::getPriceStatic()`, qui est appelée chaque fois que PrestaShop calcule le prix d'un produit. Ce n'est pas un hook standard mais une surcharge de classe de base. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé. | Pour inclure les actifs JS/CSS du module pour le Back Office (par exemple, `AdminPbcListController`). |
| `actionModuleInstall` | Lors de l'installation du module. | Pour créer la table de base de données `ps_pbc` et enregistrer les hooks nécessaires. |
| `actionModuleUninstall` | Lors de la désinstallation du module. | Pour supprimer la table de base de données `ps_pbc` et désenregistrer les hooks. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support technique, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance et à garantir le fonctionnement optimal du module avec votre boutique PrestaShop.
