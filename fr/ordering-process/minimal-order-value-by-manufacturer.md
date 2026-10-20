---
title: "Valeur de commande minimale par fabricant - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Valeur de commande minimale par fabricant' de MyPresta.eu."
sidebar:
  label: "Valeur de commande minimale par fabricant - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Minimal order value by manufacturer sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimal-order-value-by-manufacturer.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/minimal-order-value-by-manufacturer/)
>
> ---


# Valeur de commande minimale par fabricant

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal du module, accessible directement après l'installation ou en cliquant sur « Configurer » à côté du module dans le Gestionnaire de modules.

- **Ce que fait cet écran :** Cette page vous permet d'activer/désactiver le module et de gérer les paramètres principaux qui contrôlent son comportement.

#### Paramètres et options

- **Activer / Désactiver le module :**

  - **Ce que fait ce paramètre :** Il s'agit d'un interrupteur global pour activer ou désactiver l'ensemble des fonctionnalités du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module vérifiera activement les valeurs de commande minimales par fabricant dans les paniers des clients et appliquera des restrictions si les conditions ne sont pas remplies.
    - *Lorsqu'il est désactivé :* Le module cessera de fonctionner. Aucune vérification de valeur de commande minimale ne sera effectuée, et les clients pourront commander n'importe quel montant auprès de n'importe quel fabricant.
  - **Valeur recommandée :** **OUI** (pour activer la fonction principale du module).
  - **Scénario/exemple pour le marchand :** Si vous testez le module ou souhaitez temporairement désactiver toutes les règles de commande minimale sans les supprimer, vous pouvez le désactiver.
- **Afficher le message sur la page du panier :**

  - **Ce que fait ce paramètre :** Contrôle si un message d'avertissement est affiché au client sur la page du panier si la valeur de commande minimale d'un fabricant n'est pas atteinte.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront un message clair et informatif sur leur page de panier, indiquant quel minimum de fabricant n'est pas atteint et combien ils doivent ajouter.
    - *Lorsqu'il est désactivé :* Aucun message n'apparaîtra sur la page du panier. La restriction s'appliquera toujours, mais le client pourrait ne la découvrir que plus tard lors du paiement, ce qui pourrait entraîner de la frustration.
  - **Valeur recommandée :** **OUI**.
  - **Scénario/exemple pour le marchand :** L'activation de cette option offre une meilleure expérience utilisateur, guidant les clients à résoudre le problème tôt plutôt que de les surprendre au moment du paiement.
- **Afficher le message sur la page de paiement :**

  - **Ce que fait ce paramètre :** Contrôle si un message d'avertissement est affiché au client sur la page de paiement si la valeur de commande minimale d'un fabricant n'est pas atteinte.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront un message sur la page de paiement, les empêchant de finaliser la commande tant que le minimum n'est pas atteint.
    - *Lorsqu'il est désactivé :* Le processus de paiement pourrait simplement s'arrêter sans explication claire, ou le module pourrait empêcher la progression sans message spécifique, ce qui peut dérouter les clients.
  - **Valeur recommandée :** **OUI**.
  - **Scénario/exemple pour le marchand :** C'est crucial pour empêcher les commandes qui ne répondent pas à vos critères et pour communiquer clairement la raison au client.
- **Message à afficher (pour les pages du panier et de paiement) :**

  - **Ce que fait ce paramètre :** Vous permet de personnaliser le texte du message d'avertissement affiché aux clients lorsqu'une valeur de commande minimale n'est pas atteinte. Vous pouvez utiliser des espaces réservés comme `{manufacturer_name}` et `{missing_amount}`.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est modifié :* Le message personnalisé apparaîtra sur le front office.
    - *Lorsqu'il est laissé par défaut :* Un message standard sera utilisé.
  - **Valeur recommandée :** Personnalisez-le pour qu'il soit clair et utile. Exemple : « Pour finaliser votre commande, vous devez ajouter {missing\_amount} de plus de produits {manufacturer\_name}. »
  - **Scénario/exemple pour le marchand :** Vous pourriez vouloir rendre le message plus convivial, inclure un appel à l'action ou l'aligner sur le ton de votre marque.

### 2.2 Écrans d'administration dédiés : Règles de valeur de commande minimale par fabricant (Back Office > Catalogue > Valeur de commande minimale par fabricant)

Cet écran est l'endroit où vous définissez et gérez les règles de valeur de commande minimale pour chaque fabricant.

- **Nom de l'écran et emplacement du menu :** « Valeur de commande minimale par fabricant » sous le menu **Catalogue**.
- **Ce que fait cet écran :** Il s'agit d'une zone de gestion dédiée pour ajouter, modifier et supprimer des règles de valeur de commande minimale par fabricant. Il présente une liste de toutes les règles actuellement configurées.

#### Actions et paramètres disponibles

- **Liste des règles :**

  - **Ce que cela fait :** Affiche un tableau de toutes les règles de valeur de commande minimale existantes. Chaque ligne affiche généralement le nom du fabricant, la valeur minimale définie et les options pour modifier ou supprimer la règle.
  - **Effet des modifications :** Ce tableau fournit un aperçu de toutes les règles actives.
  - **Flux de travail recommandé :** Examinez régulièrement cette liste pour vous assurer que vos règles sont à jour avec vos besoins commerciaux.
- **Bouton « Ajouter une nouvelle règle » :**

  - **Ce que cela fait :** Cliquer sur ce bouton vous amène à un formulaire où vous pouvez créer une nouvelle règle de valeur de commande minimale.
  - **Effet des modifications :** Ouvre un nouveau formulaire.
  - **Flux de travail recommandé :** Utilisez-le lorsque vous devez définir un nouveau minimum pour un fabricant qui n'est pas encore dans la liste.
- **Bouton « Modifier » (pour chaque règle) :**

  - **Ce que cela fait :** Vous permet de modifier les paramètres d'une règle existante.
  - **Effet des modifications :** Ouvre le formulaire de la règle avec des données pré-remplies, vous permettant de modifier le fabricant ou la valeur minimale.
  - **Flux de travail recommandé :** Utilisez-le pour ajuster les minimums en fonction de nouveaux accords avec les fournisseurs ou de stratégies de vente.
- **Bouton « Supprimer » (pour chaque règle) :**

  - **Ce que cela fait :** Supprime une règle de valeur de commande minimale spécifique.
  - **Effet des modifications :** La règle est immédiatement supprimée, et le fabricant associé n'aura plus d'exigence de valeur de commande minimale.
  - **Flux de travail recommandé :** Utilisez-le lorsqu'un fabricant n'exige plus de commande minimale, ou si vous abandonnez une marque.

#### Formulaire Ajouter/Modifier une règle

Lorsque vous ajoutez une nouvelle règle ou modifiez une règle existante, vous verrez généralement les champs suivants :

- **Fabricant :**

  - **Ce que fait ce paramètre :** Ce champ vous permet de sélectionner le fabricant spécifique auquel cette règle de valeur de commande minimale s'appliquera. Il dispose généralement d'une recherche avec autocomplétion pour vous aider à trouver facilement les fabricants.
  - **Effet de la modification de ce paramètre :** Lie la règle à un fabricant particulier.
  - **Valeur recommandée :** Sélectionnez le fabricant exact auquel vous avez l'intention d'appliquer la règle.
  - **Scénario/exemple pour le marchand :** Vous pourriez sélectionner « Apple » pour définir un minimum pour tous les produits Apple, ou « Samsung » pour les produits Samsung.
- **Valeur de commande minimale :**

  - **Ce que fait ce paramètre :** C'est ici que vous entrez la valeur numérique (dans la devise par défaut de votre boutique, par exemple, EUR, USD) qui représente le montant total minimum requis pour les produits du fabricant sélectionné.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une valeur est définie (par exemple, 50.00) :* Les clients doivent avoir au moins 50.00 de produits du fabricant sélectionné dans leur panier pour continuer.
    - *Lorsqu'il est défini sur 0 ou laissé vide :* Cela désactive effectivement le minimum pour ce fabricant (bien qu'il soit préférable de supprimer la règle si aucun minimum n'est nécessaire).
  - **Valeur recommandée :** Une valeur numérique positive reflétant vos exigences commerciales.
  - **Scénario/exemple pour le marchand :** Si votre fournisseur pour « MarqueX » vous demande de commander au moins 100 € de ses produits, vous définirez ce champ à « 100.00 » pour « MarqueX ».

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer / Désactiver le module | OUI | Interrupteur global pour la fonctionnalité du module. |
| Configuration du module | Afficher le message sur la page du panier | OUI | Affiche un avertissement sur le panier si le minimum n'est pas atteint. |
| Configuration du module | Afficher le message sur la page de paiement | OUI | Affiche un avertissement sur la page de paiement si le minimum n'est pas atteint. |
| Configuration du module | Message à afficher | Personnalisable | Personnalise le texte du message d'avertissement. |
| `AdminMobmController` | Fabricant (Ajouter/Modifier une règle) | Sélectionner dans la liste | Lie la règle à un fabricant spécifique. |
| `AdminMobmController` | Valeur de commande minimale (Ajouter/Modifier une règle) | Valeur numérique | Définit la valeur totale minimale pour les produits du fabricant sélectionné. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai défini un minimum, mais cela ne fonctionne pas sur le front office. Que dois-je vérifier ?**
R1 :

-   **Le module est-il activé ?** Allez dans `Modules > Gestionnaire de modules` et assurez-vous que « Valeur de commande minimale par fabricant » est actif.
-   **La règle spécifique est-elle activée ?** Vérifiez `Catalogue > Valeur de commande minimale par fabricant` pour vous assurer que la règle pour le fabricant en question est correctement configurée avec une valeur positive.
-   **Vider le cache :** Allez dans `Paramètres avancés > Performances` et cliquez sur « Vider le cache » (pour tous les caches). Parfois, le cache de PrestaShop peut empêcher les modifications d'apparaître immédiatement.
-   **Vérifier les conflits :** Désactivez temporairement les autres modules qui modifient le panier ou le processus de commande pour voir s'il y a un conflit.

**Q2 : Le message sur la page du panier/de paiement n'apparaît pas.**
R2 :

-   **Vérifiez la configuration du module :** Allez dans `Modules > Gestionnaire de modules > Configurer` pour « Valeur de commande minimale par fabricant ». Assurez-vous que « Afficher le message sur la page du panier » et « Afficher le message sur la page de paiement » sont tous deux réglés sur **OUI**.
-   **Le minimum est-il réellement non atteint ?** Vérifiez à nouveau que les produits dans le panier du fabricant spécifique sont réellement inférieurs au minimum défini.

**Q3 : Puis-je définir des minimums différents pour différents groupes de clients ?**
R3 : Ce module, dans sa forme standard, applique une valeur minimale unique par fabricant à tous les clients. Si vous avez besoin de minimums spécifiques à des groupes de clients, cela nécessiterait un développement personnalisé ou un module différent.

**Q4 : Comment le module gère-t-il les boutiques multi-devises ?**
R4 : Le module utilise la devise par défaut de votre boutique (telle que définie dans `Localisation > Devises` et `Localisation > Localisation`) pour la « Valeur de commande minimale » que vous définissez. Il convertira automatiquement le total du panier du client dans la devise par défaut pour la comparaison, assurant la cohérence.

**Q5 : Le module semble ralentir mon site. Que puis-je faire ?**
R5 :

-   **Vider le cache :** Assurez-vous que tous les caches sont régulièrement vidés (`Paramètres avancés > Performances`).
-   **Ressources du serveur :** Vérifiez les ressources de votre environnement d'hébergement (CPU, RAM). Si votre boutique a un très grand nombre de fabricants ou de produits, assurez-vous que votre serveur peut gérer la charge.
-   **Mises à jour du module :** Utilisez toujours la dernière version du module de MyPresta.eu, car les mises à jour incluent souvent des améliorations de performances.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Valeur de commande minimale par fabricant » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard. Il étend principalement `Module` pour sa fonctionnalité et sa configuration de base, utilise `AdminController` pour la gestion des règles en back-office, et `ModuleFrontController` pour les interactions AJAX en front-office liées à la validation du panier. Il ne semble pas utiliser de classes `ObjectModel` personnalisées, s'appuyant plutôt sur `Configuration` pour les paramètres généraux et l'interaction directe avec la base de données (ou potentiellement une structure de tableau simple) pour les règles spécifiques aux fabricants. Les hooks sont largement utilisés pour s'intégrer dans le flux du panier et de la commande.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/ajax.php`
    *   **Nom de la classe :** `MobmAjaxModuleFrontController` (probable, basé sur la convention de nommage des fichiers) étendant `ModuleFrontController`.
    *   **Responsabilité :** Ce contrôleur est probablement responsable de la gestion des requêtes AJAX depuis le front-office, en particulier celles liées aux mises à jour du panier ou à la progression de la commande. Il recevrait les données du panier, effectuerait les vérifications de la valeur de commande minimale et renverrait une réponse JSON indiquant si les conditions sont remplies et quels messages doivent être affichés. C'est crucial pour les mises à jour dynamiques sans rechargement complet de la page.
-   `controllers/front/index.php`
    *   **Nom de la classe :** `MobmIndexModuleFrontController` (probable) étendant `ModuleFrontController`.
    *   **Responsabilité :** Ce fichier pourrait être un espace réservé ou utilisé pour une simple page front-office si le module en avait une. Compte tenu de l'objectif du module, il est moins probable qu'il rende une page complète et plus probable qu'il s'agisse d'un fallback ou d'une partie d'une chaîne de redirection si `ajax.php` est le point d'interaction principal.

#### Contrôleurs d'administration Back-Office

-   `controllers/admin/AdminMobm.php`
    *   **Nom de la classe :** `AdminMobmController` étendant `ModuleAdminController`.
    *   **Nom de l'onglet :** « Valeur de commande minimale par fabricant » (sous Catalogue).
    *   **Entité gérée :** Gère l'entité `mobm`, qui représente les règles individuelles de valeur de commande minimale pour les fabricants.
    *   **Responsabilité :** C'est le contrôleur principal pour la gestion de la liste des règles de commande minimale des fabricants. Il gère :
        *   L'affichage de la liste des règles existantes (en utilisant `renderList()`).
        *   L'ajout de nouvelles règles (en utilisant `renderForm()` pour le formulaire d'ajout).
        *   La modification des règles existantes (en utilisant `renderForm()` pour le formulaire de modification).
        *   La suppression des règles.
        *   La validation du formulaire et la sauvegarde des données.
        *   Il interagit probablement avec la table `ps_configuration` ou une table personnalisée pour stocker l'ID du fabricant et sa valeur minimale associée.
-   `controllers/admin/index.php`
    *   **Nom de la classe :** `AdminMobmIndexModuleAdminController` (probable) étendant `ModuleAdminController`.
    *   **Responsabilité :** Similaire au `index.php` du front-office, cela pourrait être un espace réservé ou un point d'entrée par défaut. Dans PrestaShop, les fichiers `index.php` dans les répertoires de contrôleurs servent souvent de mesures de sécurité de base (par exemple, `die('Access Denied');`) ou de routage simple s'ils ne sont pas explicitement gérés par un contrôleur plus spécifique.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module :

1.  Stocke ses règles de fabricant directement dans la table `ps_configuration` (par exemple, sous forme de tableau sérialisé).
2.  Utilise des requêtes de base de données directes dans le fichier de module principal ou le contrôleur d'administration pour gérer une table personnalisée.
3.  Gère les données sous forme de tableau simple dans le contexte du module sans `ObjectModel` formel.

Étant donné que l'`AdminMobmController` gère une entité `mobm`, il est fort probable qu'une table personnalisée (par exemple, `ps_mobm`) soit créée lors de l'installation, et l'`AdminMobmController` gère implicitement les opérations CRUD pour cette table sans classe `ObjectModel` dédiée dans `classes/`. La `$definition` de cette entité serait alors définie directement dans l'`AdminMobmController` ou le fichier de module principal.

### 4.4 Assets JavaScript (`views/js/`)

-   `mobm/lib/searchTool/views/js/autocomplete.js`
    *   **Portée :** Back-office (probablement pour le formulaire `AdminMobmController`).
    *   **Responsabilité :** Fournit une fonctionnalité d'autocomplétion pour la sélection des fabricants dans le formulaire « Ajouter/Modifier une règle ». Il écoute la saisie de l'utilisateur dans un champ de texte, envoie des requêtes AJAX à un contrôleur de back-office (par exemple, `AdminManufacturers` ou une méthode `AdminMobm` personnalisée) pour récupérer les noms de fabricants correspondants et affiche des suggestions.
-   `mobm/views/js/mobm.js`
    *   **Portée :** Front-office.
    *   **Responsabilité :** C'est le JavaScript principal du front-office pour le module. Il est probable qu'il :
        *   Se lie aux événements sur la page du panier (par exemple, changements de quantité, ajout/suppression de produits).
        *   Se lie aux événements sur la page de paiement (par exemple, clics sur le bouton « Procéder au paiement »).
        *   Envoie des requêtes AJAX à `controllers/front/ajax.php` pour valider le panier par rapport aux minimums du fabricant.
        *   Reçoit des réponses JSON et met à jour dynamiquement l'interface utilisateur avec des messages d'avertissement ou empêche la progression si les minimums ne sont pas atteints.
        *   Pourrait gérer les pop-ups modaux ou les repères visuels pour le client.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `mobm/lib/searchTool/views/css/autocomplete.css`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Style la liste déroulante d'autocomplétion et le champ de saisie utilisés pour la sélection du fabricant dans le formulaire d'administration.
    *   **Sélecteurs de classes CSS clés :** Cible probablement des classes comme `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`, etc.
-   `mobm/views/css/mobm.css`
    *   **Portée :** Front-office.
    *   **Responsabilité :** Style les messages d'avertissement affichés sur les pages du panier et de paiement. S'assure que ces messages sont visuellement distincts et s'intègrent bien au thème.
    *   **Sélecteurs de classes CSS clés :** Cible probablement des classes personnalisées ajoutées par le module aux conteneurs de messages d'avertissement, par exemple, `.mobm-warning-message`, `.mobm-error-block`.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   `mobm/lib/searchTool/views/scripts.tpl`
    *   **Portée :** Back-office.
    *   **Responsabilité :** Ce template inclut probablement le JavaScript nécessaire pour la fonctionnalité d'autocomplétion (à partir de `autocomplete.js`) et potentiellement un script ou une configuration en ligne pour celui-ci. Il serait rendu dans la méthode `renderForm()` de l'`AdminMobmController`.
-   `mobm/views/templates/front/displayShoppingCart.tpl`
    *   **Portée :** Front-office.
    *   **Hook :** Ce template est conçu pour être rendu dans un hook qui affiche du contenu sur la page du panier, tel que `displayShoppingCartFooter` ou `displayBeforeShoppingCartBlock`.
    *   **Responsabilité :** Affiche le message d'avertissement au client si la valeur de commande minimale d'un fabricant n'est pas atteinte. Il contiendra la logique pour afficher le message uniquement lorsque `{$mobm_warning_message}` (ou une variable similaire passée depuis le module) n'est pas vide.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

-   **`ps_configuration`** : Stocke les paramètres généraux du module (par exemple, `PS_MOVB_ENABLED`, `PS_MOVB_CART_MSG_ENABLED`, `PS_MOVB_CHECKOUT_MSG_ENABLED`, `PS_MOVB_CUSTOM_MESSAGE`).
-   **`ps_mobm` (Table personnalisée probable)** : Cette table est hautement probable étant donné que l'`AdminMobmController` gère une entité `mobm`.
    *   **Colonnes (Hypothétiques) :**
        *   `id_mobm` (Clé primaire, INT)
        *   `id_manufacturer` (INT, Clé étrangère vers `ps_manufacturer`)
        *   `min_value` (DECIMAL(20,6), stocke le montant minimum de la commande)
        *   `date_add` (DATETIME)
        *   `date_upd` (DATETIME)

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de toutes les pages du front-office. | Pour inclure les assets CSS (`mobm.css`) et JavaScript (`mobm.js`) du front-office. |
| `actionCartSave` | Après la sauvegarde d'un panier (par exemple, changement de quantité, ajout/suppression de produit). | Pour effectuer une validation en temps réel des minimums du fabricant et potentiellement stocker le statut de validation. |
| `actionValidateOrder` | Avant qu'une commande ne soit officiellement validée. | Pour empêcher la validation de la commande si les minimums du fabricant ne sont pas atteints. |
| `displayShoppingCartFooter` (ou similaire) | En bas de la page du panier. | Pour afficher le message d'avertissement (`displayShoppingCart.tpl`) si les minimums ne sont pas atteints. |
| `displayPaymentTop` (ou hook de paiement similaire) | En haut de l'étape de sélection du paiement lors du processus de commande. | Pour afficher le message d'avertissement et empêcher la progression si les minimums ne sont pas atteints. |
| `displayAdminProductsExtra` (ou similaire) | Sur la page d'édition de produit dans le back-office. | Potentiellement pour afficher des informations sur la valeur minimale du fabricant directement sur les pages de produits (moins probable mais possible). |
| `displayBackOfficeHeader` | Dans la section `<head>` de toutes les pages du back-office. | Pour inclure les assets CSS (`autocomplete.css`) et JavaScript (`autocomplete.js`) du back-office pour le formulaire `AdminMobmController`. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour vous assurer que vous utilisez la version la plus récente et la plus compatible du module « Valeur de commande minimale par fabricant », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
