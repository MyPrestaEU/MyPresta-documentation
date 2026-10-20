---
title: "Méthodes de paiement par produit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Méthodes de paiement par produit' par MyPresta.eu."
sidebar:
  label: "Méthodes de paiement par produit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Payment methods by products sur MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/payment-methods-by-products/)
>
> ---


# Méthodes de paiement par produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

Ce module dispose de deux zones de configuration principales : la page de configuration initiale du module et un écran de gestion dédié pour la création d'associations produit-paiement.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Méthodes de paiement par produit)

En cliquant sur « Configurer » après l'installation, vous arriverez sur la page de configuration principale du module. Cette page contient généralement les paramètres généraux du module.

**Actuellement, aucun paramètre spécifique n'est détecté sur cette page de configuration principale au-delà des informations standard du module. La fonctionnalité principale est gérée via l'écran dédié « Associations Paiement - Produit ».**

Si les futures versions introduisent des paramètres ici, ils apparaîtraient sous forme de commutateurs, de champs de saisie ou de listes déroulantes. Pour l'instant, vous pouvez passer directement à l'écran de gestion dédié.

### 2.2 Écran d'administration dédié : Associations Paiement - Produit (Back Office > Modules > Méthodes de paiement par produit > Associations Paiement - Produit)

C'est le centre névralgique pour la gestion de vos restrictions produit-paiement. Vous trouverez cet écran en naviguant vers **Modules > Gestionnaire de modules**, en trouvant « Méthodes de paiement par produit », en cliquant sur « Configurer », puis en cherchant un onglet ou un lien intitulé « Associations Paiement - Produit » (ou similaire, selon la navigation du module).

**Nom de l'écran et emplacement du menu :**

- **Chemin du menu :** Back Office > Modules > Gestionnaire de modules > Méthodes de paiement par produit > Configurer > **Associations Paiement - Produit** (ou un onglet/lien similaire sur la page de configuration).
- Cet écran vous permet de visualiser, ajouter, modifier et supprimer des associations entre les produits et les méthodes de paiement.

**Actions et paramètres disponibles :**

#### 2.2.1 La vue liste « Associations Paiement - Produit »

Cette vue présente un tableau de toutes les restrictions produit-paiement existantes que vous avez configurées.

| Nom de la colonne | Objectif et impact |
| --- | --- |
| **ID** | Un identifiant unique pour chaque association. |
| **Produit** | Le nom du produit concerné par la restriction. |
| **Paiement** | Le nom de la méthode de paiement qui est restreinte ou autorisée pour ce produit. |
| **Pays** | (Le cas échéant) Le pays pour lequel cette restriction s'applique. Si laissé vide, elle s'applique globalement. |
| **Actions** | Icônes pour **Modifier** (icône crayon) ou **Supprimer** (icône poubelle) une association existante. |

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

- **Examiner les règles existantes :** Vérifiez régulièrement cette liste pour vous assurer que vos restrictions sont à jour avec votre catalogue de produits et vos besoins commerciaux.
- **Identifier les conflits :** Recherchez les règles qui se chevauchent ou qui sont en conflit, surtout si vous avez de nombreux produits et méthodes de paiement.
- **Utiliser la recherche/le filtre :** Si la liste devient longue, utilisez les options de recherche ou de filtre disponibles pour trouver rapidement des restrictions spécifiques de produit ou de paiement.

#### 2.2.2 Ajout ou modification d'une « Association Paiement - Produit »

Pour ajouter une nouvelle restriction, vous trouverez généralement un bouton « Ajouter » sur la vue liste. Lors de la modification, vous cliquez sur l'icône en forme de crayon à côté d'une entrée existante. Cela ouvrira un formulaire avec les champs suivants :

| Champ du formulaire | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **ID Produit** | Ce champ vous permet de sélectionner le produit spécifique que vous souhaitez associer à des restrictions de paiement. | Lorsque vous sélectionnez un produit, le module appliquera les restrictions de paiement choisies chaque fois que ce produit se trouve dans le panier d'un client. | Sélectionnez le produit exact de votre catalogue. Utilisez la fonction de recherche si vous avez de nombreux produits. | Vous vendez « Ebook numérique : Guide Marketing ». Vous voulez vous assurer qu'il n'est payé que via PayPal ou carte de crédit, et non en espèces à la livraison. Vous sélectionnez ce produit ici. |
| **Méthodes de paiement** | Il s'agit d'une liste de toutes les méthodes de paiement actives dans votre boutique PrestaShop. Vous sélectionnez les méthodes de paiement **autorisées** pour le produit choisi. | - *Lorsque vous sélectionnez une ou plusieurs méthodes de paiement :* Seules ces méthodes sélectionnées seront disponibles au moment du paiement si le produit associé est dans le panier. Toutes les autres méthodes de paiement seront masquées.   - *Lorsque vous ne sélectionnez AUCUNE méthode de paiement :* Cela signifie effectivement que le produit ne peut pas être acheté, ou qu'il héritera des règles d'autres produits dans le panier. Il n'est généralement pas recommandé de laisser ce champ vide, sauf si vous avez un cas d'utilisation très spécifique. | Sélectionnez toutes les méthodes de paiement acceptables pour le produit choisi. | Pour « Ebook numérique : Guide Marketing », vous cochez « PayPal » et « Carte de crédit ». Si un client achète cet ebook, seules ces deux options apparaîtront au moment du paiement. |
| **Pays** | (Facultatif) Ce champ vous permet de spécifier un pays pour lequel cette restriction produit-paiement particulière s'applique. | - *Lorsqu'un pays est sélectionné :* La restriction (produit + paiements autorisés) ne s'appliquera que si l'adresse de livraison du client se trouve dans le pays sélectionné.   - *Lorsqu'il est laissé vide :* La restriction s'applique globalement, quel que soit le pays du client. | Laissez vide pour une application globale, ou sélectionnez un pays spécifique si la restriction est géographiquement limitée. | Vous vendez une « Sculpture en verre fragile » qui ne peut être payée que par « Virement bancaire » en France en raison des exigences d'assurance d'expédition. Vous sélectionnez la sculpture, « Virement bancaire » et « France ». Pour les clients en dehors de la France, d'autres méthodes de paiement pourraient toujours être disponibles pour ce produit (si aucune autre règle globale ne s'applique). |
| **Enregistrer** | Ce bouton enregistre votre nouvelle association produit-paiement ou celle mise à jour. | Les modifications sont immédiatement appliquées au processus de paiement de votre boutique. | Cliquez toujours sur « Enregistrer » après avoir effectué des modifications. | Après avoir configuré les règles pour votre « Ebook numérique », vous cliquez sur « Enregistrer » pour les activer. |

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | (Aucun paramètre spécifique détecté) | N/A | Informations générales sur le module. |
| Associations Paiement - Produit (Liste) | ID | N/A | Identifiant unique de l'association. |
| Associations Paiement - Produit (Liste) | Produit | N/A | Nom du produit dans l'association. |
| Associations Paiement - Produit (Liste) | Paiement | N/A | Nom de la méthode de paiement dans l'association. |
| Associations Paiement - Produit (Liste) | Pays | N/A | Pays pour lequel la restriction s'applique (le cas échéant). |
| Associations Paiement - Produit (Formulaire Ajouter/Modifier) | ID Produit | Sélectionner un produit | Spécifie le produit pour lequel les méthodes de paiement seront restreintes. |
| Associations Paiement - Produit (Formulaire Ajouter/Modifier) | Méthodes de paiement | Sélectionner toutes les méthodes acceptables | Définit les méthodes de paiement **autorisées** pour le produit sélectionné. |
| Associations Paiement - Produit (Formulaire Ajouter/Modifier) | Pays | Laisser vide pour global, ou sélectionner spécifique | Limite la restriction à un pays spécifique. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : J'ai configuré une restriction, mais toutes les méthodes de paiement s'affichent toujours au moment du paiement. Qu'est-ce qui ne va pas ?**
R :

1.  **Cache :** Videz toujours le cache de votre PrestaShop après avoir effectué des modifications. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
2.  **Produit dans le panier :** Assurez-vous que le produit spécifique que vous avez restreint se trouve réellement dans le panier du client lors du test. Le module n'applique les règles que si le produit est présent.
3.  **Méthode de paiement activée :** Vérifiez que les méthodes de paiement que vous *vous attendez* à voir sont réellement activées dans **Modules > Paiement > Méthodes de paiement**. Ce module filtre les méthodes *activées*, il ne les active pas lui-même.
4.  **Règles conflictuelles :** Si vous avez plusieurs produits dans le panier, et que chacun a des restrictions, le module n'affichera que les méthodes de paiement autorisées par *tous* les produits restreints. S'il n'y a pas de méthode autorisée commune, il peut sembler qu'aucune méthode ne s'affiche. Examinez attentivement vos associations.

**Q : J'ai configuré une restriction, et maintenant AUCUNE méthode de paiement ne s'affiche au moment du paiement !**
R : Cela se produit généralement si :

1.  **Aucune méthode commune :** Vous avez plusieurs produits restreints dans le panier, et il n'y a aucune méthode de paiement autorisée par *tous* ces produits. Par exemple, le produit A autorise PayPal, le produit B autorise la carte de crédit. Si les deux sont dans le panier, aucun ne s'affichera. Vous devez vous assurer qu'il y a au moins une méthode autorisée commune.
2.  **Liste autorisée vide :** Vous avez créé une association pour un produit mais n'avez sélectionné *aucune* méthode de paiement comme autorisée. Le module masquera alors toutes les méthodes pour ce produit. Modifiez l'association et sélectionnez les méthodes de paiement appropriées.

**Q : Ce module affecte-t-il les méthodes de paiement pour les produits qui ne font partie d'aucune association ?**
R : Non. Si un produit ne fait partie d'aucune « Association Paiement - Produit », il n'impose aucune restriction. Le module n'agit que sur les produits pour lesquels vous avez explicitement défini des règles. Si un panier ne contient que des produits non restreints, toutes les méthodes de paiement standard activées de votre boutique seront affichées.

**Q : Comment ce module interagit-il avec d'autres modules de restriction de paiement (par exemple, par groupe de clients, par montant total) ?**
R : Ce module fonctionne généralement en surchargeant la classe `PaymentOptionsFinder` de PrestaShop (comme on le voit dans le dossier `override`). Cela signifie qu'il a la priorité ou s'intègre à un niveau fondamental. Généralement, la règle la plus restrictive s'appliquera. Si un autre module restreint une méthode de paiement, et que ce module l'autorise pour un produit, la méthode de paiement sera probablement toujours restreinte par l'autre module. Il est crucial de tester minutieusement si vous utilisez plusieurs modules de restriction.

**Q : Puis-je restreindre les méthodes de paiement par pays sans restreindre par produit ?**
R : La fonction principale de ce module est la restriction basée sur les produits. Bien qu'il dispose d'un champ « Pays », il s'applique *à l'association produit-paiement*. Si vous avez besoin de restrictions de paiement purement basées sur le pays (indépendamment du produit), vous pourriez avoir besoin d'un module distinct conçu à cet effet, ou vérifier si vos passerelles de paiement offrent des restrictions par pays directement.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse technique approfondie du module « Méthodes de paiement par produit » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module étend principalement le mécanisme de découverte des options de paiement de PrestaShop. Il utilise un `override` pour modifier la classe `PaymentOptionsFinder`, qui est responsable de la détermination des méthodes de paiement disponibles lors du paiement. Cela permet au module d'injecter sa logique de filtrage basée sur les produits directement dans le processus de récupération des options de paiement, assurant une intégration transparente avec le flux de paiement de PrestaShop.
Le module suit un modèle MVC PrestaShop standard pour sa gestion Back Office, utilisant un `AdminController` pour gérer l'entité `pobp` (Association Produit-Paiement).

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. La fonctionnalité front-office du module est gérée via une surcharge d'une classe principale, et non un contrôleur frontal dédié.
-   **Contrôleurs d'administration Back-Office** :

    -   `pobp/controllers/admin/AdminPobpController.php`
        -   **Nom de la classe et classe parente** : `AdminPobpController` étend `ModuleAdminController`.
        -   **Nom de l'onglet** : Ce contrôleur gère l'entité « Associations Paiement - Produit ». Il est probablement enregistré comme un sous-onglet sous la configuration principale du module.
        -   **Responsabilité** : C'est le contrôleur CRUD (Créer, Lire, Mettre à jour, Supprimer) principal pour les associations produit-paiement. Il gère :
            -   L'affichage de la liste des associations existantes (ID, Produit, Paiement, Pays).
            -   La fourniture du formulaire pour ajouter de nouvelles associations ou modifier celles existantes.
            -   Le traitement des soumissions de formulaire pour enregistrer de nouvelles associations ou des associations mises à jour dans la base de données.
            -   La gestion de la suppression des associations.
            -   Les champs du formulaire « ID Produit », « Méthodes de paiement » et « Pays » sont gérés ici.
    -   `pobp/controllers/admin/index.php`
        -   Ce fichier est généralement un espace réservé vide ou contient des mesures de sécurité de base (par exemple, `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;`). Il ne représente pas une vue de contrôleur fonctionnelle en soi, mais garantit que l'accès direct au répertoire `controllers/admin` est redirigé.

### 4.3 Classes et modèles principaux (`classes/`)

-   `pobp/override/classes/checkout/PaymentOptionsFinder.php`
    -   **Objectif** : Il s'agit d'un fichier de surcharge critique. Il modifie la classe principale de PrestaShop responsable de la recherche et du retour des options de paiement disponibles lors du paiement.
    -   **Nom de la classe et classe parente** : `PaymentOptionsFinder` (surcharge la classe `PaymentOptionsFinder` originale).
    -   **Logique clé** : La méthode `getPaymentOptions()` surchargée (ou une méthode similaire) contiendra la logique principale du module.
        -   Elle récupère les produits actuellement dans le panier du client.
        -   Pour chaque produit, elle vérifie s'il existe des « Associations Paiement - Produit » définies dans la base de données du module.
        -   Elle filtre ensuite les options de paiement initialement disponibles (retournées par la méthode `getPaymentOptions()` parente) en fonction de ces associations.
        -   La logique de filtrage garantit que seules les méthodes de paiement explicitement autorisées pour *tous* les produits restreints dans le panier sont retournées. Si un produit n'a pas d'association, il ne restreint rien. Si plusieurs produits ont des associations, l'intersection des méthodes de paiement autorisées est utilisée.
    -   **Interaction avec la base de données** : Cette classe interrogera la table de base de données personnalisée du module (probablement `ps_pobp` ou similaire) pour récupérer les associations produit-paiement.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript spécifique n'a été détecté dans l'inventaire fourni. Tout comportement dynamique dans le Back Office (comme la recherche de produits dans le formulaire d'association) est probablement géré par le JS principal de PrestaShop ou un script en ligne minimal.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS spécifique n'a été détecté dans l'inventaire fourni. Le style des formulaires et des listes du Back Office est probablement hérité du thème d'administration par défaut de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** : Aucun explicitement listé, car le module fonctionne via une surcharge plutôt que par un rendu direct de hook dans le front office.
-   **Templates d'administration (`views/templates/admin/`)** :
    -   `pobp/lib/searchTool/views/scripts.tpl`
        -   **Objectif** : Ce template contient probablement du JavaScript ou de la logique Smarty liée à un outil de recherche utilisé dans le Back Office, éventuellement pour rechercher des produits lors de la création ou de la modification d'une association. Il pourrait inclure des appels AJAX ou un filtrage dynamique pour la sélection de produits.
-   **Templates Front-office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module créera au moins une table personnalisée lors de sa méthode `install()` (définie dans `pobp/index.php`).
    -   **`ps_pobp` (ou nom similaire, par exemple, `ps_payment_by_product_association`)** :
        -   Cette table stocke les associations produit-paiement réelles.
        -   Colonnes attendues :
            -   `id_pobp` (Clé primaire, INT)
            -   `id_product` (INT, clé étrangère vers `ps_product`)
            -   `id_payment_module` (INT, clé étrangère vers `ps_module` ou `ps_payment_module` si une telle table existe, ou stocke simplement le nom/ID du module)
            -   `id_country` (INT, clé étrangère vers `ps_country`, nullable pour les règles globales)
            -   Autres colonnes potentielles pour les paramètres ou les horodatages.
    -   Les valeurs de configuration (si elles étaient présentes dans `getContent()`) seraient stockées dans `ps_configuration`.
-   **Table des hooks enregistrés** :
    La fonctionnalité principale du module repose sur le mécanisme `override` plutôt que sur l'exécution directe de hooks pour son filtrage principal. Cependant, pour son intégration Back Office et potentiellement pour de futures fonctionnalités, il pourrait enregistrer des hooks standard.

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `displayAdminProductsExtra` | Sur la page d'édition de produit dans le Back Office. | Pourrait être utilisé pour afficher un lien rapide ou un résumé des restrictions de paiement pour le produit actuel. (Non explicitement détecté mais un point d'intégration courant). |
    | `actionPaymentOptionsModifier` | Pendant le processus de récupération des options de paiement. | Ce hook est spécifiquement conçu pour que les modules modifient la liste des options de paiement. La surcharge de `PaymentOptionsFinder` atteint effectivement un résultat similaire à un niveau inférieur. |
    | `actionModuleInstall` | Lors de l'installation du module. | Pour créer des tables de base de données et enregistrer les hooks nécessaires. |
    | `actionModuleUninstall` | Lors de la désinstallation du module. | Pour nettoyer les tables de base de données et désenregistrer les hooks. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour vous assurer d'avoir la dernière version compatible du module « Méthodes de paiement par produit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toute question ou problème concernant la fonctionnalité et l'intégration du module.
---
